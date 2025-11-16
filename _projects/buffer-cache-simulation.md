---
layout: project
title:  "Buffer Cache Simulation"
bannerDescription: "A Simple Buffer Cache implementation to simulate getblk and brelse algorithms. A menu based step simulation has been implemented to provide fine grained control over the various cases of getblk algorithm."
techUsed: C++, makefile, shell script
githubRepo: rohitshakya
comments: true
priority: 9
date: 2019-04-09
---

# Buffer Cache Simulation

A simple buffer cache implementation for simulation of `getblk` and `brelse` algorithms.

## Overview

In this implementation, the main program act as `kernel` and manipulates the buffer cache, while user input acts as coming and going `processes`. User controls which block to get and release. User can also manipulate buffer status. This gives us complete control over the simulation.  Also we can view the buffer cache, freelist, buffer list, and sleeping processes at all times.

This is a single-process synchronous program, so there is no added complexity of managing threads.

## How to Run

- Compile using `make`
- Then you can simply run the executable `./bufcache`
- Alternatively, use `make run` 

## How to test

- Run tests and see scenarios by executing test script `./test.sh`
- Alternatively, use `make test`

## Problem Statement

Buffer cache simulation. The idea was to simulate `getblk` and `brelse` algorithms 
that handle the allocation and release of buffers to processes. 
The key requirement was to be able to visualize all 5 scenarios of `getblk` and 
clearly identify the working of `getblk` in all of those scenarios.

## Suggested Solution

We want a simulation slow enough to analyse the working details of `getblk`.
Several implementations are possible. Let us glance over them.

### threads

Threads over processes because all of the children (processes) need to work on the same data structure instance (buffer cache).

Because threads can easily run into race conditions when writing to the data structure, locks need to be implemented.

Once threads and locks are in place we can think about `getblk` implementation.

We now need to show all 5 cases of `getblk` so we need to control how different threads are scheduled.
For this we need a scheduler. Either we can implement our own (which is overkill for just a simulation),
or choose the system scheduler, and forcing it to choose certain process by `sleep`ing others.

This results in an intricate mechanism of all the threads working with system scheduler. 
We have little control over the actual buffers and their status.
If we want to manipulate some buffers to test something, 
we will need to spin up another thread at runtime to handle the buffer status.

Preliminary tests show unreliability in threads and their execution order because we cannot exactly predict how the system scheduler will schedule them.

### client server architecture

Server acts as kernel, and only server manipulates the buffer cache directly.

Clients (`processes`) can ask server (`kernel`) to allocate them a buffer (`getblk`) and 
inform them when they relinquish the buffer, so kernel can release the buffer (`brelse`).

Server controls how these client requests are scheduled. 
The actual buffer cache implementation will reside with the server. 
Because, server (`kernel`) needs to be able to accept requests from multiple clients (`processses`), 
it'll spin up a new handler process for each new client.

This brings us back to our original problem. 
Now these multiple processes need to communicate and somehow share the memory region 
for manipulating buffer cache. 
Implementation complexity will be no better than the previous `threads` approach.

### User driven simulation

Let the main program act as `kernel` and manipulate the buffer cache, while user input acts as coming and going `processes`. User controls which block to get and release. User can also manipulate buffer status.

This gives us complete control over the simulation. 
Also we can view the buffer cache, freelist, buffer list, and sleeping processes at all times.

Because this will be a single-process synchronous program, there is no added complexity of managing threads. We can focus on `getblk` and `buffer cache`.

This is the chosen approach for this project.

## Programming Language Used

`C` is the chosen language. 
Because we are implementing buffer cache, which is a lower level algorithm, it needs to be fast and
`C` provides the fastest system calls. 
Also the fact that actual unix system is written in `C` made it an easy choice.

## AOS Concepts Implemented

The chosen implementation type is kept simple. So it does not use any complex constructs of AOS.

1. Forks/Threads - not required
2. Locking unlocking mechanism - not required
3. Signals - not required

## Getblk cases Handled

All 5 cases of `getblk` have been handled.

### How the request for a block is being captured

User input determines which block to `get` and `release`

### Delayed write

User manually sets a `block status` to `delayed write`.
Then when the `getblk` algorithm sees this `delayed write` marked buffer, it starts a dummy async write to disk, and moves on the next free list buffer.

## Supported Commands

Directly from the help section of the program.

```
help


buf 
	Display the status of all the buffers.
hash
	Display all the Hash Queues.
free
	Display free list
wait
	Display waiting Queue
exit
	To exit the simulation

getblk <blockNumber>

	Take the blockNumber from the user, execute getblk(n)

brelse <blockNumber>

	Take the blockNumber from the user, execute brelse() 

set <blockNumber> <statusCode> 

	Set the status of the buffer to status code

	B : Buffer Busy
	V : Buffer Data is Valid
	D : Buffer is marked delayed write
	K : Kernet is reading/writing buffer to disk
	W : Buffer is awaited by some other process
	O : Buffer Data is OLD

reset <blockNumber> <statusCode> 

	Reset the status of the buffer to status code

	B : Buffer Busy
	V : Buffer Data is Valid
	D : Buffer is marked delayed write
	K : Kernet is reading/writing buffer to disk
	W : Buffer is awaited by some other process
	O : Buffer Data is OLD

```

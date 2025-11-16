---
layout: homepage
title: Home
permalink: /
---

<div class="col-md-2"></div>
<div class="col-md-8">
    <header class="post-header text-center">
    <img style="width: 15em; height: 15em; border-radius: 50%;"
                src="{{site.baseurl}}/images/profile.jpeg">
            <h1 style="font-size: 3em; font-family: Raleway;">Rohit Shakya</h1>
       
       {% if site.github %}
        <a target="_blank" href="{{site.github}}">
            <li class="social github"><i class="fa fa-github-square"></i></li>
        </a>
        {% endif %}

        {% if site.linkedin %}
        <a target="_blank" href="{{site.linkedin}}">
            <li class="social linkedin"><i class="fa fa-linkedin-square"></i></li>
        </a>
        {% endif %}

        {% if site.leetcode %}
        <a target="_blank" href="{{site.leetcode}}">
            <li class="social leetcode"><i class="fa fa-code"></i></li>
        </a>
        {% endif %}

        {% if site.instagram %}
        <a target="_blank" href="{{site.instagram}}">
            <li class="social instagram"><i class="fa fa-instagram"></i></li>
        </a>
        {% endif %}

        {% if site.email %}
        <a target="_blank" href="mailto:{{site.email}}">
            <li class="social email"><i class="fa fa-envelope"></i></li>
        </a>
        {% endif %}
    </header>
    <div style="margin: 2em 0; text-align: left; font-family: 'Raleway', sans-serif;">
    <p>
        <strong>Hello!</strong> I'm <strong>Rohit Shakya</strong>, a <strong>Senior Backend Engineer</strong> with over 
        <strong>5 years of experience</strong> designing and scaling 
        <strong>cloud-native, low-latency systems</strong> using <strong>Java</strong>, 
        <strong>Kotlin</strong>, and <strong>Spring Boot</strong>.
    </p>
    <p>
        I specialize in <strong>system design</strong>, <strong>distributed systems</strong>, and 
        <strong>event-driven architectures</strong> — building <strong>scalable microservices</strong> 
        and optimizing <strong>real-time data pipelines</strong> with <strong>Kafka</strong>. 
        I'm proficient in <strong>AWS</strong>, <strong>Docker</strong>, <strong>Kubernetes</strong>, 
        <strong>caching strategies</strong>, and <strong>CI/CD pipelines</strong>.
    </p>
    <p>
        I hold an <strong>M.Sc.</strong> and <strong>B.Sc. (Hons.)</strong> in 
        <strong>Computer Science</strong> from the <strong>University of Delhi</strong>.  
        <br>Explore my work under <a href="/projects">Projects</a> or check out my code on 
        <a href="https://github.com/rohitshakya" target="_blank">GitHub</a> 🚀
    </p>
</div>

<div class="col-md-2"></div>



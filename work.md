---
layout: page
title: <span style="color:blue";>My Work</span>
permalink: 
feature-img: "img/color.png"
---

<div class="work">
    {% for project in site.portfolio limit:5 %}
    <div class="project">
      <div class="project-description">
        <a href="{{ project.url | prepend: site.baseurl }}"><strong>{{ project.title }}</strong></a>
        <p>{{ project.short-description }}</p>
      </div>
      <div class="project-thumb">
        <div class="boxed" style="width:120%; margin-left:-10%; text-align:center;">
          <a href="{{ project.url | prepend: site.baseurl }}">
            <img src="{{ project.thumbnail-path }}" alt="{{ project.title }}" align="middle">
          </a>
        </div>
      </div>
    </div>
    {% endfor %}
  </div>

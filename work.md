---
layout: page
title: Work
permalink: 
feature-img: "img/color.png"
---

<div class="work">
    {% for project in site.portfolio limit:4 %}
    <div class="project">
      <div class="project-description">
        <a href="{{ project.url | prepend: site.baseurl }}"><strong>{{ project.title }}</strong></a>
        <p>{{ project.short-description }}</p>
      </div>
      <div class="project-thumb">
        <div class="boxed" style="width: 100%;margin-left: auto; margin-right: auto; border: 1px solid blue;text-align: center;">
          <a href="{{ project.url | prepend: site.baseurl }}">
            <img src="{{ project.thumbnail-path }}" alt="{{ project.title }}"/>
          </a>
        </div>
      </div>
    </div>
    {% endfor %}
  </div>

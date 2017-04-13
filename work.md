---
layout: page
title: My Work
permalink: 
feature-img: "img/color.png"
---

<div class="work">
    {% for project in site.portfolio limit:5 %}
    <div class="project" style="text-align:center;" ><strong>{{ project.title }}</strong>
			<div class="project-path">
			  <a href="{{ project.url | prepend: site.baseurl }}" style="color:#191970"><strong>Click here to goto Case Study</strong></a>
      </div>
			<div class="github-path">
			  <a href="{{ project.github-path }}">
				<p style="color:#800000"><strong>Click here to check code on github</strong></p></a>
      </div>
			
			
      <div class="project-description">
        <a href="{{ project.url | prepend: site.baseurl }}"></a>
        <p>{{ project.short-description }}</p>
      </div>
			<br><br>
      <div class="project-thumb">
          <a href="{{ project.url | prepend: site.baseurl }}">
            <img src="{{ project.thumbnail-path }}" alt="{{ project.title }}" align="middle">
          </a>
       </div>
    </div>
    {% endfor %}
  </div>

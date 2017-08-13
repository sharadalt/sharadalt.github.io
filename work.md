---
layout: page
title: <h5>My Work</h5>
permalink: 
feature-img: "img/color.png"
---

<div class="work">
  {% for project in site.portfolio limit:5 %}
    <div class="project" style="text-align:center;" >
		  <a href="{{ project.url | prepend: site.baseurl }}"><strong>{{ project.title }}</strong></a>
		<div class="project-path">
		  <a href="{{ project.url | prepend: site.baseurl }}" style="color:#191970"><strong>Case Study</strong></a>
    </div>
		<div class="github-path">
		  <a href="{{ project.github-path }}">
			<p style="color:#800000"><strong>Code on github</strong></p></a>
    </div>	
    <div class="project-description">
      <a href="{{ project.url | prepend: site.baseurl }}"></a>
      <p>{{ project.short-description }}</p>
    </div>
	  <br><br>
    <div class="project-thumb">
      <a href="{{ project.url | prepend: site.baseurl }}">
        <img src="{{ project.thumbnail-path }}" alt="{{ project.title }}">
      </a>
    </div>
    </div>
  {% endfor %}
</div>

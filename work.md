---
layout: page
title: My Work
permalink: 
feature-img: "img/color.png"
---

<div class="work">
    {% for project in site.portfolio limit:5 %}
    <div class="project" style="text-align:center;">
<!--		 <div class="boxed" style="text-align:center;"> -->
    <a href="{{ project.url | prepend: site.baseurl }}" style="color:#00bfff"><strong>{{ project.title }}</strong></a>
			<div class="github-path">
			<a href="{{ project.github-path }}" style="color:#ac5353"><strong>{{ project.github-path }}</strong></a>
      </div>
			
      <div class="project-description">
        <a href="{{ project.url | prepend: site.baseurl }}"></a>
        <p>{{ project.short-description }}</p>
      </div>
			<br><br>
      <div class="project-thumb">
          <a href="{{ project.url | prepend: site.baseurl }}">
					  <p style="color:#00bfff"><strong>Click Here to goto Case Study</strong></p>
            <img src="{{ project.thumbnail-path }}" alt="{{ project.title }}" align="middle">
          </a>
       </div>
     <!-- </div>  -->
    </div>
    {% endfor %}
  </div>

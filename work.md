---
layout: page
title: My Work
permalink: 
feature-img: "img/color.png"
---

<div class="work">
    {% for project in site.portfolio limit:5 %}
    <div class="project" style="text-align:center;">
		<a href="{{ project.url | prepend: site.baseurl }}"><strong>{{ project.title }}</strong></a>
<!--		 <div class="boxed" style="text-align:center;"> -->
      <div class="project-description">
        <a href="{{ project.url | prepend: site.baseurl }}"></a>
        <p>{{ project.short-description }}</p>
      </div>
			<div class="github-path">
        <a href="{{ project.github-path }}"><strong>{{ project.github-path }}</strong></a>
      </div>
			<br><br>
      <div class="project-thumb">
          <a href="{{ project.url | prepend: site.baseurl }}">
            <img src="{{ project.thumbnail-path }}" alt="{{ project.title }}" align="middle">
          </a>
       </div>
     <!-- </div>  -->
    </div>
    {% endfor %}
  </div>

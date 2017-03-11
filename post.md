---
layout: page
title: <span style="color:blue"> My Posts</span>
permalink: 
feature-img: "img/color.png"
---

<div class="posts">
    <ul>
      {% for post in site.posts limit:3 %}
			 <div container-fluid>
			  <div class="row">
          <div class="col-xs-6 col-sm-3">
            <li class="post-teaser">
              <h3>
                <a style="color:blue" class="post-link" href="{{ post.url | prepend: site.baseurl }}">
                {{ post.title }}
                </a>
              </h3>
              <p class="meta">
                {{ post.date | date: "%B %-d, %Y" }}
              </p>
              <div class="excerpt">
                {{ post.excerpt | | strip_html | strip_newlines | truncate: 120 }}
              </div>
              <a style="color:blue" href="{{ post.url | prepend: site.baseurl }}">
                {{ site.theme_settings.str_continue_reading }}
              </a>
            </li>
			    </div>
			  </div>
				</div>
      {% endfor %}
    </ul>
  </div>
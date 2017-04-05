---
layout: post
title: Blocmetrics
thumbnail-path: "img/blocmetrics_main.PNG"
short-description: An analytics service and reporting tool that you can use with web apps to track user activity.
github-path: "https://github.com/sharadalt/blocmetrics"
---

##### Explanation
There are plenty of good analytic services, but that doesn't mean you can't build a better one. 

##### Problem
Though there are multiple analytic services, there is always a need for better one.

##### Solution

<a href="https://github.com/sharadalt/blocmetrics" style="font-family:Times New Roman;"><strong>Click here for Blocmetrics source code on Github</strong></a>

Blocmetrics provides the solution for you with good set of features. Once you register your applications with Blocmetrics you can track the events to the registered application.

Once you are registered, with your name, you can register the applications to be tracked. Blocmetrics provides wiki CRUD operations as well. 

Blocmetrics is built in Ruby on Rails framework with MVC architecture. It uses html, CSS and bootstrap-sass to stylize. It uses ruby gems to achieve some of it's tasks. It uses postgreSQL for it's database needs.

Now comes the fun part! How is the look and feel of Blocmetrics. Come on in, Let us explore it!

You have seen the welcome page of Blocmetrics in the Work page of this portfolio.


Like in any web application, you need to register first in order to use Blocmetrics. Question is how do you do that?

Here is the screen, like any web application, provide your name, email and password and click the Signup button, That's it.

<div class="boxed" style="width:100%;text-align: center;">
  <a href="{{ project.url | prepend: site.baseurl }}">
    <img src="/img/blocmetrics_signup.PNG"/>
  </a>
</div>
<br />

Wait a minute, That's not it!
At Blocmetrics, like in Blocipedia when you signup, you get a confirmation email and instructions to signin.
Once instructions followed, you are a registered user.

Once registered, I assume, You want to signin into Blocmetrics.

<div class="boxed" style="width: 100%;text-align: center;">
  <a href="{{ project.url | prepend: site.baseurl }}">
    <img src="/img/blocmetrics_login.PNG"/>
  </a>
</div>
<br />

Here also, like in Blocipedia, If you forget the password, no worries. Relax.. You can recover it.
By the way, Blocmetrics also has user authentication implemented using 'Devise' gem, if you care about that. 

Once signed, You can get started with Blocmetrics through the screen below:

<div class="boxed" style="width: 100%;text-align: left;">
  <a href="{{ project.url | prepend: site.baseurl }}">
    <img src="/img/blocmetrics_getgoing.PNG"/>
  </a>
</div>
<br />


Once you click on that magic button get going, that's it! you are inside  Blocmetrics ! 

Not only you can register applications, wikis but also edit, show and delete your registered applications.

<div class="boxed" style="width: 100%; text-align: left;">
  <a href="{{ project.url | prepend: site.baseurl }}">
    <img src="/img/blocmetrics_index.PNG"/>
  </a>
</div>
<br />

This is how your edit page looks like.

<div class="boxed" style="width: 100%;text-align: left;">
  <a href="{{ project.url | prepend: site.baseurl }}">
    <img src="/img/blocmetrics_edit_regapplication.PNG"/>
  </a>
</div>
<br />


If you just want to have a look at your events registered, clicking that show button will do the trick.

<div class="boxed" style="width: 100%;text-align:left ;">
  <a href="{{ project.url | prepend: site.baseurl }}">
    <img src="/img/blocmetrics_showpage.PNG"/>
  </a>
</div>
<br />

Here you can see the name of the registered application, the name of the event and the number of times the event has occurred.


##### Results
With Blocmetrics, you can track the application.

##### Conclusion
Blocmetrics is the way togo for tracking the events for an application.


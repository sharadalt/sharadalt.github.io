---
layout: post
title: Blocipedia
thumbnail-path: "img/blocipedia_final.PNG"
short-description: A production quality SaaS application implemented using Ruby on Rails that allows users to create their own wikis.

---

##### Explanation

Wikis are a great way to collaborate on community-sourced content. Whether the wiki is for a hobby or work-related project it is good to have a wiki. Experience has shown us the importance of the public wikis. The idea of having private wikis is/was new to some, including me. After thinking about the need, I realized how valuable private wikis are. 

##### Problem

There is a need for an app that not only lets us create our own wikis and share them in public but also create wikis and share them in private with other collaborators. It does not matter even if  minimal cost is involved to have a private wiki. 

##### Solution

Blocipedia application gives you the solution. Once you are registered, You can create free Markdown wikis using Blocipedia. You can pay minimal money and have your own private wikis/documents collaborate with colleagues. Bocipedia provides wiki CRUD operations.

Blocipedia is built in Ruby on Rails framework with MVC architecture. It uses html and CSS to stylize. It uses ruby gems to achieve some of it's tasks. It uses postgreSQL for it's database needs.

Now comes the fun part! Like in any web application, you need to register first in order to use Blocipedia. Question is how do you do that?

Here is the screen, like any web application, provide your name, email and password and click the Signup button, That's it.

<div class="boxed" style="width:50%;border: 1px solid brown;text-align: center;">
  Sign up page
  <a href="{{ project.url | prepend: site.baseurl }}">
    <img src="/img/blocipedia_2.PNG"/>
  </a>
</div>
<br />

Wait a minute, That's not it!
At Blocipedia, when you signup, you get a confirmation email and instructions to signin.
Once instructions followed, you are a registered user.

Once registered, what do you want to do next? It's no brainer, You want to signin into Blocipedia.

<div class="boxed" style="width: 50%;border: 1px solid brown;text-align: center;">
  Sign in page
  <a href="{{ project.url | prepend: site.baseurl }}">
    <img src="/img/blocipedia_3.PNG"/>
  </a>
</div>
<br />

If you forget the password, no worries. Relax.. You can recover it.
By the way, Blocipedia has user authentication implemented using Devise gem, if you care about that. 

Once logged in, not only you can create public wikis but also can edit and delete your own creation. 
Now you are a standard user in Blocipedia roles.

<div class="boxed" style="width: 50%;border: 1px solid brown;text-align: center;">
  Standard User page
  <a href="{{ project.url | prepend: site.baseurl }}">
    <img src="/img/blocipedia_4.PNG"/>
  </a>
</div>
<br />

If you wish to have own private wikis, just click on the button which says, upgrade account to premium by paying. Boooom...

<div class="boxed" style="width: 50%;border: 1px solid brown;text-align: center;">
  Payment window page
  <a href="{{ project.url | prepend: site.baseurl }}">
    <img src="/img/blocipedia_5.PNG"/>
  </a>
</div>
<br />

Blocipedia has used services of stripe for payment processing, again if you care to know it.

Now after paying, Tat tada .... You become a premium user!!! That is the role, Blocipedia assigns you.

<div class="boxed" style="width: 50%;border: 1px solid brown;text-align: center;">
  Premium User page
  <a href="{{ project.url | prepend: site.baseurl }}">
    <img src="/img/blocipedia_7.PNG"/>
  </a>
</div>
<br />

There is one more role called admin role in Blocipedia. This roles thingy is implemented using pundit gem.
Premium users like you and admin users are able to create new private wikis and make public wikis private. If you did not figure it out already, you can edit a wiki with Markdown syntax. You can add and remove collaborators for your private wikis.

Important note, If you decide to go back to standard user role, that is a piece of cake!  At the bottom of premier user screen select to become one. That is it.

##### Results
With Blocipedia, you can create both public and private wikis.

##### Conclusion
Blocipedia is the way togo for creating public and private wikis.

<a href="https://github.com/sharadalt/blocipedea" style="font-family:Times New Roman;"><strong>Click Here to see Blocipedia source code on Github</strong></a>

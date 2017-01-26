---
layout: post
title: Blocipedia
thumbnail-path: "img/blocipedia_main.PNG"
short-description: A production quality SaaS application implemented using Ruby on Rails that allows users to create their own wikis.

---

##### Explanation

Wikis are a great way to collaborate on community-sourced content. Whether the wiki is for a hobby or work-related project it is good to have a wiki. What if we want to have a private wiki? Interesting right? Actually I did not even think we could have private wikis. But later I thought why not? 

##### Problem

There is a need for an app that not only lets us create our own wikis and share them in public but also create wikis and share them in private with other collaborators. With this feature, you don't mind spending some minimal amount of money right? 

##### Solution

Blocipedia gives you the solution. If you register with Blocipedia you will be able to create your own public wiki at no cost to you. Is n't that nice?

<div class="boxed" style="width: 100%;margin-left: auto; margin-right: auto; border: 1px solid blue;text-align: center;">
  Main page
  <a href="{{ project.url | prepend: site.baseurl }}">
    <img src="/img/blocipedia_1.PNG"/>
  </a>
</div>
<br />

Now comes the question how do you register? 
Here is the screen, like any web application, provide your name, email and password and press the Signup button, That's it.

<div class="boxed" style="width: 100%;margin-left: auto; margin-right: auto; border: 1px solid blue;text-align: center;">
  Sign up page
  <a href="{{ project.url | prepend: site.baseurl }}">
    <img src="/img/blocipedia_2.PNG"/>
  </a>
</div>
<br />

Wait a minute, That's not it!
At Blocipedia, when you signup, Guess what? you get a confirmation email and instructions to signin.
Once instructions followed, you are a registered user.

Once registered, what do you want to do next? It's no brainer, You want to signin into Blocipedia.

<div class="boxed" style="width: 100%;margin-left: auto; margin-right: auto; border: 1px solid blue;text-align: center;">
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

<div class="boxed" style="width: 100%;margin-left: auto; margin-right: auto; border: 1px solid blue;text-align: center;">
  Standard User page
  <a href="{{ project.url | prepend: site.baseurl }}">
    <img src="/img/blocipedia_4.PNG"/>
  </a>
</div>
<br />

If you wish to have own private wikis, just click on the button which says, upgrade account to premium by paying. Boooom...

<div class="boxed" style="width: 100%;margin-left: auto; margin-right: auto; border: 1px solid blue;text-align: center;">
  Payment window page
  <a href="{{ project.url | prepend: site.baseurl }}">
    <img src="/img/blocipedia_5.PNG"/>
  </a>
</div>
<br />

Blocipedia has used services of stripe for payment processing, again if you care to know it.

Now after paying, Tat tada .... You become a premium user!!! That is the role, Blocipedia assigns you.

<div class="boxed" style="width: 100%;margin-left: auto; margin-right: auto; border: 1px solid blue;text-align: center;">
  Premium User page
  <a href="{{ project.url | prepend: site.baseurl }}">
    <img src="/img/blocipedia_7.PNG"/>
  </a>
</div>
<br />

There is one more role called admin role in Blocipedia. This roles thingy is implemented using pundit gem .
Premium users like you and admin users are able to create new private wikis and make public wikis private. If you did not figure it out already, you can edit a wiki with Markdown syntax. You can add and remove collaborators for your private wikis.

Important note, If you decide to go back to standard user role, that is a piece of cake!  At the bottom of premier user screen select to become one. That is it.

##### Results
With Blocipedia, you can create both public and private wikis.

##### Conclusion
Blocipedia is the way togo for creating public and private wikis.

<a href="https://github.com/sharadalt/blocipedea" style="font-family:Times New Roman;"><strong>Click Here to see Blocipedia source code on Github</strong></a>

---
layout: post
title: Blocitoff
thumbnail-path: "img/blocitoff_main.PNG"
short-description: A self-destructing to-do lists application. It is an Utility Application in Ruby on Rails with Rake Automation 
---

##### Explanation
We all will have to-dos all the time. Sometimes I will have bunch of to-dos, but will not get to them and will not even know how many to-dos I have. Suddenly, I become panicky thinking about my to-dos. Making a to-do list is the only savior for me in that kind of situation. I can track my to-dos with the to-do list. Another usage is a  Project Manager, to keep track of a project's tasks wants to created to-dos.

##### Problem
Sometimes, we make a list on a piece of paper and it gets lost, that is such a bummer! 
We need a to-do list organizer application to prevent this disaster. To-do lists are notorious for collecting junk: to-do items that you want to remember, but are not very important and thus get consistently put off. The application has to address the problem of to-do list clutter also.

##### Solution
Blocitoff will not only help in achieving your goal but will also aim to keep to-do lists manageable by automatically deleting to-do items that have not been completed after seven days. The hypothesis is that if the to-do item is not important enough to be completed in seven days, it doesn't belong on your to-do list.

How does Blocitoff look like to start with? Here you go...

<div class="boxed" style="width: 100%;margin-left: auto; margin-right: auto; border: 1px solid blue;text-align: center;">
  Main page
  <a href="{{ project.url | prepend: site.baseurl }}">
    <img src="/img/blocitoff_1.PNG"/>
  </a>
</div>
<br />

As you can see, To get access to Blocitoff, First thing you do is Signup.

<div class="boxed" style="width: 100%;margin-left: auto; margin-right: auto; border: 1px solid blue;text-align: center;">
  Signup page
  <a href="{{ project.url | prepend: site.baseurl }}">
    <img src="/img/blocitoff_2.PNG"/>
  </a>
</div>
<br />

Then ofcourse next thing you do is Signin. Your Sign in opens up the door to Blocitoff. 

<div class="boxed" style="width: 100%;margin-left: auto; margin-right: auto; border: 1px solid blue;text-align: center;">
  Sign in page
  <a href="{{ project.url | prepend: site.baseurl }}">
    <img src="/img/blocitoff_3.PNG"/>
  </a>
</div>
<br />

Blocitoff has user authentication implemented from scratch. Isn't that neat?

Signed In user can create multiple to-do items, see how old a to-do item is edit them, mark to-do items as complete and delete them. Also, to-do items are automatically deleted seven days after their creation date.

<div class="boxed" style="width: 100%;margin-left: auto; margin-right: auto; border: 1px solid blue;text-align: center;">
  Profile page
  <a href="{{ project.url | prepend: site.baseurl }}">
    <img src="/img/blocitoff_4.PNG"/>
  </a>
</div>
<br />

##### Results
With Blocitoff, you can see your progress in your to-do list and don't have to worry about the maintainance of your to-do list.

##### Conclusion
Blocitoff is the way togo for your to-do lists.

<a href="https://github.com/sharadalt/blocitoff" style="font-family:Times New Roman;"><strong>Click Here to see Blocitoff source code on Github</strong></a>

---
layout: post
<span title: style="font-size:12px">What is a Closure ?</span>
---
<h3>Introduction</h3>
<p>
When I was facing the first interview in web development, my mentor specifically told me to be prepared with 'Closures'. According to, “Master the JavaScript Interview”,  you can’t get very far with JavaScript without learning about 'closures'. If you ask anyone in Front end development for interview tips, they invariably touch upon 'Closures'. 
</p>

<p><h5>What is a Closure?</h5>
Closure is one when the function remembers the surrounding context in which it was declared.</p>


Now let us see the code below:


{% highlight js %}

var globalVar = 50;

function a (){
var asLocalVar = 75;
console.log(globalVar);
console.log(asLocalVar);
	
function b(){
  var bsLocalVar = 100;
  console.log(globalVar);
  console.log(asLocalVar);
  console.log(bsLocalVar);	
}
b();
}

console.log(globalVar); // prints 50
a(); // prints 50, 75, 50, 75, 100 on separate lines
{% endhighlight %}


<p>
The global scope has access to global scope. The global scope does not have access to the scope of either a() or b().
Function a() can access the global scope and it's local scope, but not the scope of function b(). 
Function b() can access the global scope, the scope of function a(), and it's own local scope. 
</p>


<p>In other words, The innermost function of nested functions scope chain has access to all the variables that exist both within and outside it. Any outer function, however, cannot access the scope of any inner function.</p>

<p>A closure gives you access to an outer function’s scope from an inner function.</p>


In JavaScript, closures are created every time a function is created, at function creation time.






<h3>References</h3>
(1)Inputs from Jeff Lau, Bloc Mentor <br>
(2)Bloc Tutorial Material <br>
(3)"Master the JavaScript Interview” from medium.com
---
layout: post
title: TDD with Ruby Using Rspec
---

<h3>Introduction</h3>
<p>
<b>TDD</b> stands for Test Driven Development. What is Test Driven Development?
When tests are written to specify future code's behavior, it's called "Test-Driven Development", or TDD.</p>
<p>
Rails makes it easy to write your tests. It starts by producing skeleton test code while you are creating your models and controllers.By simply running your Rails tests you can ensure your code adheres to the desired functionality even after some major code refactoring.
</p>
<p>
One of the most popular testing frameworks in Ruby on Rails community, for TDD is RSpec.
</p>
<h3>TDD Explanation</h3>

{% highlight ruby %}
def mult(a,b)
  a+b
end

p mult(5,4) # prints 9

{% endhighlight %}

Above code prints 9 when run, though expected result is 20. As can be seen it is not giving error. So we need to have tests created to make sure the code behaves as expected.

The following Test code, should test the above function, mult.

{% highlight ruby %}
describe "mult" do
  it "multiplies its two arguments" do
    product = mult(4, 3)
    expect(product).to eq(12)
  end
end
{% endhighlight %}

Now if we modify the function, as below, The above test code will pass.

{% highlight ruby %}
def mult(a,b)
  12
end
{% endhighlight %}

But the above implementation will fail, if the test code is as below:

{% highlight ruby %}
describe "mult" do
  it "multiplies its two arguments" do
    product = mult(5, 6)
    expect(product).to eq(30)
  end
end
{% endhighlight %}

The mult function has to be as below, for it to produce correct result for all arguments:
{% highlight ruby %}
def mult(a,b)
  a * b
end
{% endhighlight %}

<h3>TDD Using RSpec</h3>
First thing we will do is, install the RSpec gem.

{% highlight ruby %}
sharadalt:~/workspace (example_ruby_app) $ gem install rspec
Fetching: rspec-support-3.5.0.gem (100%)
Successfully installed rspec-support-3.5.0
Fetching: rspec-core-3.5.4.gem (100%)
Successfully installed rspec-core-3.5.4
Fetching: diff-lcs-1.3.gem (100%)
Successfully installed diff-lcs-1.3
Fetching: rspec-expectations-3.5.0.gem (100%)
Successfully installed rspec-expectations-3.5.0
Fetching: rspec-mocks-3.5.0.gem (100%)
Successfully installed rspec-mocks-3.5.0
Fetching: rspec-3.5.0.gem (100%)
Successfully installed rspec-3.5.0
6 gems installed
sharadalt:~/workspace (example_ruby_app) $ 
{% endhighlight %}

















<h3>References</h3>
(1)Bloc Tutorial Material <br>
(2)rubyonrails.org <br>
(3)rspec.info

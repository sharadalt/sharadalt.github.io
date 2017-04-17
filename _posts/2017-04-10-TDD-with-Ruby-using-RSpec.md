---
layout: post
title: TDD with Ruby Using Rspec
---

<h3>Introduction</h3>
<p> Nowadays we hear a lot about TDD. All hiring managers want development engineers to know TDD and use TDD. <b>TDD</b> stands for Test Driven Development. 

<p>What is Test Driven Development? </p>
<p>When tests are written to specify future code's behavior, it's called "Test-Driven Development" or TDD.</p>
<p>

When we follow our code development based on TDD, the advantages are many.
The main one being production of quality code in optimal amount of time, reducing the time-to-market (TTM).

Rails makes it easy to write tests. It starts by producing skeleton test code while we are creating our models and controllers. By simply running our Rails tests we can ensure our code adheres to the desired functionality even after some major code refactoring.</p>
<p>
TDD is three step process. Red, Green , Refactor.
First write a test for a functionality which does not exist. Make sure the test fails(Red). Create the functionality so that the test passes(Green). Then refactor the code to make it cleaner , maintainable and robust. 
</p>
<p>
Narrow the scope of the test to be as small and self-contained as possible. When you are testing the method,  only assess what the code returns. Write DRY(Do not Repeat Yourself) test.
</p>
<p>
One of the most popular testing frameworks in Ruby on Rails community, for TDD is RSpec.
</p>
<p>
<b>rspec-rails:</b> Supports using RSpec to test Ruby on Rails applications in place of Rails' built-in test framework.
</p>

<h3>Reading RSpec Tests</h3>
RSpec, like most testing frameworks, runs our code in particular conditions and with particular arguments. It sets expectations for the outcome of this process, and the test passes if those expectations are met.

Consider the following code in file example1_spec.rb,

{% highlight ruby %}
RSpec.describe Example1 do
  describe "#hello" do
    it "says hello to someone" do
      example1 = Example1.new()
      expect(example1.hello("Mary", "Craig")).to eq("Hello Mary Craig.")
    end
  end
end
{% endhighlight %}

<p>The strings following 'describe' and 'it' are for human read. We can put whatever we want there — though it should actually describe the method and its behavior. Changing the contents of those strings will not change the test behavior.</p>

<p>Following a typical RSpec pattern, The text to the right of describe ("hello") is a description of the method we will be testing. The string "says hello to someone" following it is similarly explanatory, and gives a basic human-readable description of the behavior we intend to test.</p>

<p>If we analyze what the above code is doing:</p>

<p>We declare what we're testing (the hello method), in between describe and  do.
We declare our expected behavior in English (for humans), in between the it and the do.
We write the actual test, creating the object which contains the method hello and invoking the function on that object and checking the return value of this method to equal to an expected string. If that expectation is fulfilled, the test will pass; otherwise, it will fail. We "close" the describe and it "blocks" with the keyword end.</p>

<p>RSpec assesses the return value.</p>

<p>To make this test pass, we would implement the hello method as it's written below in example1.rb:<p>

{% highlight ruby %}
class Example1
  def hello(first, last)
    "Hello #{first} #{last}."
  end
end
{% endhighlight %}

The following is the result of running the RSpec test.

{% highlight ruby %}
sharadalt:~/workspace/example_app (example_ruby_app) $ rspec spec/example1_spec.rb
.

Finished in 0.00177 seconds (files took 0.12874 seconds to load)
1 example, 0 failures
{% endhighlight %}

The code below prints 9 when run, though expected result is 20. As can be seen it is not giving error. So we need to have tests created to make sure the code behaves as expected.

{% highlight ruby %}
def mult(a,b)
  a+b
end

p mult(5,4) # prints 9

{% endhighlight %}

The following Test code, should test the above function, mult (example2_spec.rb).

{% highlight ruby %}
require_relative '../example2'
describe "mult" do
  it "multiplies its two arguments" do
    example2 = Example2.new()
    expect(example2.mult(5,4)).to eq(20)
  end
end
{% endhighlight %}

Now if we modify the function, as below, The above test code will pass.

{% highlight ruby %}
def mult(a,b)
  20
end
{% endhighlight %}

But the above implementation will fail, if the test code is as below:

{% highlight ruby %}
describe "mult" do
  it "multiplies its two arguments" do
    example2 = Example2.new()
    expect(example2.mult(5,6)).to eq(30)
  end
end
{% endhighlight %}

The mult function has to be as below, (example2.rb) for it to produce correct result for all arguments and pass the tests.
{% highlight ruby %}
class Example2
  def mult(a,b)
    a * b
  end
end
{% endhighlight %}

Now when we run RSpec tests on this, they will pass as below:

{% highlight ruby %}
sharadalt:~/workspace/example_app (example_ruby_app) $ rspec spec/example2_spec.rb
.

Finished in 0.00139 seconds (files took 0.10101 seconds to load)
1 example, 0 failures
{% endhighlight %}

Narrow implementations of methods can pass single specific tests. We need tests to test code from a variety of angles. We need to read the test specs to make sure we understand exactly what is expected of our code, and what is needed to pass. 

<h3>Testing Models Using RSpec</h3>
First thing we will do is, install the RSpec gem for rspec-core, rspec-expectations and rspec-mocks.

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

<p>
We can create a directory to run our tests. Then we can have two directories, models and spec(RSpec directory). Create two files, entry.rb and entry_spec.rb in models and spec directory respectively.

{% highlight ruby %}
sharadalt:~/workspace/example_app (example_ruby_app) $ pwd
/home/ubuntu/workspace/example_app
sharadalt:~/workspace/example_app (example_ruby_app) $ ls
example_app.rb  models/  spec/
sharadalt:~/workspace/example_app (example_ruby_app) $ cd models
sharadalt:~/workspace/example_app/models (example_ruby_app) $ ls
entry.rb
sharadalt:~/workspace/example_app/models (example_ruby_app) $ cd ..
sharadalt:~/workspace/example_app (example_ruby_app) $ cd spec
sharadalt:~/workspace/example_app/spec (example_ruby_app) $ ls
entry_spec.rb
sharadalt:~/workspace/example_app/spec (example_ruby_app) $ 
{% endhighlight %}
</p>

Let us have the contents of entry_spec.rb as below and contents of the model file, entry.rb empty:

{% highlight ruby %}
require_relative '../models/entry'
RSpec.describe Entry do
end
{% endhighlight %}

entry_spec.rb uses require_relative to load our entry model for testing. Now when we run rspec command on it, we get the following output:

{% highlight ruby %}
sharadalt:~/workspace/example_app (example_ruby_app) $ rspec spec/entry_spec.rb
/home/ubuntu/workspace/example_app/spec/entry_spec.rb:3:in `<top (required)>': uninitialized constant Entry (NameError)
        from /usr/local/rvm/gems/ruby-2.3.0/gems/rspec-core-3.5.4/lib/rspec/core/configuration.rb:1435:in `load'

{% endhighlight %}

<p>
The '(NameError)' says  that the spec failed when we executed it. This is because we reference Entry in the spec, but Entry is not defined anywhere in the current directory. Let's define Entry in models/entry.rb by creating a stub of the class.
</p>

{% highlight ruby %}
class Entry
 
end
{% endhighlight %}

<p> Now if we run the rspec test again, we see the following:

{% highlight ruby %}
sharadalt:~/workspace/example_app (example_ruby_app) $ rspec spec/entry_spec.rb
No examples found.


Finished in 0.00032 seconds (files took 0.18004 seconds to load)
0 examples, 0 failures

sharadalt:~/workspace/example_app (example_ruby_app) $ 

{% endhighlight %}

As we have not added any test to entry_spec.rb, rspec is telling us 'No examples found'.
Add some tests to test file.

Let us add tests to test the attributes, name, phone_number and email.

{% highlight ruby %}
require_relative '../models/entry'

RSpec.describe Entry do # ------------------------> The file tests the object Entry
  describe "attributes" do #----------------------> Test the attributes of Entry
    it "responds to name" do # -------------------> This test tests name attribute
      entry = Entry.new      # -------------------> Create a new entry
      expect(entry).to respond_to(:name) #--------> Set expectation for pass or fail
    end
		
    it "responds to phone number" do
      entry = Entry.new
      expect(entry).to respond_to(:phone_number)
    end
 
    it "responds to email" do
      entry = Entry.new
      expect(entry).to respond_to(:email)
    end
  end
end
{% endhighlight %}

RSpec provides methods, expect , to and respond_to etc. This is called Domain Specific Language(DSL). Now when we run the tests we see 3 failures, as we have not provided the attributes in entry.rb as yet.

{% highlight ruby %}
sharadalt:~/workspace/example_app (example_ruby_app) $ rspec spec/entry_spec.rb
FFF

Failures:

  1) Entry attributes responds to name
     Failure/Error: expect(entry).to respond_to(:name) #--------> Set expectation for pass or fail
       expected #<Entry:0x000000027bce68> to respond to :name
     # ./spec/entry_spec.rb:6:in `block (3 levels) in <top (required)>'

    ...
Finished in 0.03004 seconds (files took 0.11946 seconds to load)
3 examples, 3 failures

Failed examples:

rspec ./spec/entry_spec.rb:4 # Entry attributes responds to name
rspec ./spec/entry_spec.rb:9 # Entry attributes responds to phone number
rspec ./spec/entry_spec.rb:14 # Entry attributes responds to email

sharadalt:~/workspace/example_app (example_ruby_app) $ 

{% endhighlight %}

Now add the attributes to entry.rb as below:
{% highlight ruby %}
# The attributes 
attr_accessor :name, :phone_number, :email
{% endhighlight %}

Now we run the tests again, to see no failures.
{% highlight ruby %}
sharadalt:~/workspace/example_app (example_ruby_app) $ rspec spec/entry_spec.rb
...

Finished in 0.00207 seconds (files took 0.11044 seconds to load)
3 examples, 0 failures

{% endhighlight %}

Create the tests for the entries with values.
{% highlight ruby %}
require_relative '../models/entry'

# Entry.new is changed to take values in all the 3 tests
RSpec.describe Entry do
  describe "attributes" do #----------------------> Test the attributes of Entry
    it "responds to name" do # -------------------> This test tests name attribute
      entry = Entry.new('Linda Williams', '010.012.1915', 'linda.williams@love.com') 
      expect(entry).to respond_to(:name) #--------> Set expectation for pass or fail
    end

    it "responds to phone number" do
      entry = Entry.new('Linda Williams', '010.012.1915', 'linda.williams@love.com')
      expect(entry).to respond_to(:phone_number)
    end
 
    it "responds to email" do
      entry = Entry.new('Linda Williams', '010.012.1915', 'linda.williams@love.com')
      expect(entry).to respond_to(:email)
    end
  end
end
{% endhighlight %}

When we run the tests again, we get failures:

{% highlight ruby %}

sharadalt:~/workspace/example_app (example_ruby_app) $ rspec spec/entry_spec.rb
FFF

Failures:

  1) Entry attributes responds to name
     Failure/Error: entry = Entry.new('Ada Lovelace', '010.012.1815', 'augusta.king@lovelace.com')

     ArgumentError:
       wrong number of arguments (given 3, expected 0)
     # ./spec/entry_spec.rb:5:in `initialize'
     # ./spec/entry_spec.rb:5:in `new'
     # ./spec/entry_spec.rb:5:in `block (3 levels) in <top (required)>'

     ...

Finished in 0.00117 seconds (files took 0.11804 seconds to load)
3 examples, 3 failures

Failed examples:

rspec ./spec/entry_spec.rb:4 # Entry attributes responds to name
rspec ./spec/entry_spec.rb:9 # Entry attributes responds to phone number
rspec ./spec/entry_spec.rb:14 # Entry attributes responds to email

{% endhighlight %}

The failures are because we haven't added intialize method that takes three arguments.
Now add the initialize method with three arguments.

{% highlight ruby %}
class Entry
  # The attributes 
  attr_accessor :name, :phone_number, :email
   
  def initialize(name, phone_number, email)
  end
end
{% endhighlight %}

When you run the tests again, the tests pass.

{% highlight ruby %}
sharadalt:~/workspace/example_app (example_ruby_app) $ rspec spec/entry_spec.rb...

Finished in 0.00695 seconds (files took 0.10593 seconds to load)
3 examples, 0 failures

sharadalt:~/workspace/example_app (example_ruby_app) $ 

{% endhighlight %}

<p>
<b>Testing the attributes</b>
We will add tests to read the attribute values. An entry method is used using let helper method, instead of having an entry local variable for each test. The following is the code snippet for entry_spec.rb:
</p>
{% highlight ruby %}
require_relative '../models/entry'
RSpec.describe Entry do
  describe "attributes" do #----------------------> Test the attributes of Entry
    let(:entry) { Entry.new('Linda Williams', '010.012.1915', 'linda.williams@love.com') }
    it "responds to name" do # -------------------> This test tests name attribute
      expect(entry).to respond_to(:name) #--------> Set expectation for pass or fail
    end
     
    it "reports its name" do
      expect(entry.name).to eq('Linda Williams')
    end

    it "responds to phone number" do
      expect(entry).to respond_to(:phone_number)
    end
     
    it "reports its phone_number" do
      expect(entry.phone_number).to eq('010.012.1915')
    end
 
    it "responds to email" do
      expect(entry).to respond_to(:email)
    end
     
      it "reports its email" do
        expect(entry.email).to eq('linda.williams@love.com')
      end
    end
   
    describe "#to_s" do
      it "prints an entry as a string" do
        entry = Entry.new('Linda Williams', '010.012.1915', 'linda.williams@love.com')
        expected_string = "Name: Linda Williams\nPhone Number: 010.012.1915\nEmail: linda.williams@love.com"
   # #6
        expect(entry.to_s).to eq(expected_string)
      end
    end
end
{% endhighlight %}

code for entry.rb:

{% highlight ruby %}
class Entry
  # The attributes 
   attr_accessor :name, :phone_number, :email
   
   def initialize(name, phone_number, email)
     @name = name
     @phone_number = phone_number
     @email = email
   end
   
   def to_s
     "Name: #{name}\nPhone Number: #{phone_number}\nEmail: #{email}"
   end
end

{% endhighlight %}

Now when we run the tests again the output will be as below:

{% highlight ruby %}
sharadalt:~/workspace/example_app (example_ruby_app) $ rspec spec/entry_spec.rb
.......

Finished in 0.00385 seconds (files took 0.10242 seconds to load)
7 examples, 0 failures

sharadalt:~/workspace/example_app (example_ruby_app) $ 
{% endhighlight %}

<p>
RSpec empties the Test database before running each spec. Each test must create the data it needs.
</p>


<h3>Conclusion</h3>
<p>
We have seen RSpec test implementation for simple hello method and multiplication methods. We have also seen how to test models using RSpec. We have seen how the tests are written step by step and how the code to be tested is modified accordingly.
Writing TDD code is not that complicated in Ruby on Rails as we have seen right? We can practice to implement it in all our sofware designs to save our companies big money.
</p>

<h3>References</h3>
(1)Bloc Tutorial Material <br>
(2)rubyonrails.org <br>
(3)rspec.info<br>
(4)https://relishapp.com/rspec
(5)https://bparanj.wistia.com/projects/azxn2s3fnq

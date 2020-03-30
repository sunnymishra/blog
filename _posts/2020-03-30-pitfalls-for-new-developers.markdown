---
layout: post
title:  "Pitfalls for new Developers!"
date:   2020-03-30 01:01:35 +0530
feature_image: images/developer-code-review.jpg
tags: [worktips]
---

In the last few years while doing code review of junior developers I have noticed several recurring programming pitfalls. Goes on to say, if unchecked such sub-par coding will lead to buggy production releases and also cause Performance SLA breaches. In this post I will be sharing these points which may help junior developers to put them to use in their own code. 

<!--more-->

Reflecting at past few years of my own coding experience, I have been lucky to get few bugs in my code. I always thought I was lucky as I didn't do anything special in my code. But recently I scoured through the internet and found a couple of programming best practices. I realized unknowingly I had been following these practices all along. 

So here's the list. Also I have tried to reword some points so they sound funny and make it a less boring list to consume:


&bull; Between Code-Optimization & Code-Readability, choose Code Readability. Always.

&bull; Kids write huge monolithic function. Legends keep it simple: One method – one task.

&bull; Modular code is our mantra. We always write Modular code. Wait, what is “Modular code” again?

&bull; Writing Single line fancy code is cool. But then, verbose code gets fewer bugs in production.

&bull; Avoid Fancy code 101: Choose Switch-case instead of Ternary operator or huge single line if block.

&bull; Avoid Fancy code 101: Always use Curly braces {} around if-else, switch-case and for loops

&bull; I promise to maintain my written Code for the next 10 years. So I will not write Comments in my code. Would you promise the same?

&bull; I have the sharpest Memory in my entire team. I remember all my code. So I will not write Comments in my code. What about you?

&bull; Loosely coupled code, Modular code & Refactored code are the same thing. Google them today.

&bull; Your b.ful Code has right to get reviewed. Remember your rights. Ask for code review and feedback every time.

&bull; Move repetitive code into a generic utility function. At least try once, you will thank me later.

&bull; Write a sufficient amount of debug logs in your code. Remember overconfidence killed the cat.

&bull; Feel proud if you could write 5 Unit test cases for just 1 new Function you wrote.

&bull; Unit-test and Code-coverage are different things. Google “Code coverage” today.

&bull; Global variables are your enemy. Avoid them in your code, if you can.

&bull; Integration testing and Unit-testing are not the same. What are you testing?

&bull; ‘My test-case is my test-case, none of your test-case’ :) Well, all I am sayin’ is: Don’t share your test-cases with your Tester teammate.

&bull; Add documentation for each function you write. You will forget in 6 months what your own Function does.

&bull; Adopt Functional programming constructs like Map, reduce, Filters in your code. Declarative code is fun to write and more readable.

&bull; Immutable variables have saved many lives. Try final or const(whichever keyword your Language supports) variables today in your code.

&bull; NullPointer exception misses you a lot. Let it miss you more, put the Null check in your code.

&bull; Your function has dozens of if-else blocks? Smells like data handling in the name of business logic. Move data out of the code into separate file eg. .json/.yaml/.xml

&bull; It is tempting to catch the Parent/Generic exception, isn’t it? It’s sinful, don’t do that, catch and handle particular exception.

&bull; Did you forget to Close the Resources your Code consumed, such as IO connection, DB connection?

&bull; Always let your Function Handle the Exception, don’t wait for your calling/parent function to handle it. Don’t be lazy.

&bull; Updating a List/Map while iterating over it is Bad programming. Use functional programming concept of Map-Reduce instead.

&bull; 80% of the time you are working on someone else’s legacy code. Respect others, Write simpler readable code.

&bull; Cover edge cases in your code. Don't wait for the tester to find them and log a bug in your name

&bull; Write functions that work on Immutable variables. You will thank me later in a Multithreaded environment.

&bull; Don't write code logic in Exception Catch block. High-schoolers do that. Wait, are you a high-schooler?

&bull; Design patterns are god-sent tools. Google and use them in your code today



Happy coding fellas!!



Image credit: <cite>Photo by Mimi Thian on Unsplash</cite>

{% comment %}

Where `YEAR` is a four-digit number, `MONTH` and `DAY` are both two-digit numbers
{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/

{% endcomment %}
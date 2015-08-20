---
title: Sublime Text 3 Snippets
date: 2015-08-20 14:40
excerpt: Snippets are shortcuts for blocks of text you might want to use often. Instead of writing some common block of code, simply define it as a snippet to insert it in a snap!
layout: post
featured_image: /assets/img/sublime-text.png
---

# Sublime Text 3 Snippets #

Often as you're working with code or markup, you'll find yourself writing the same sorts of things over and over again. One of the principles of software development is DRY, Don't Repeat Yourself. While this is usually used to refer to not repeating code by breaking reusable pieces into methods, the same principle can be used when writing boilerplate.

I was watching the Laravel 5 Fundamentals series on Laracasts and the narrator recommended learning Snippets because it can make your work faster. I realized that I already had been using some Snippets that I had installed or that came by default with Sublime Text. So I decided it was worth it to see how to make one.

## Writing a Snippet ##

Sublime Text 3 and many other modern text/code editors allow users to define snippets. Snippets are a way to predefine some text and insert it by another name. As an example, I was regularly creating new form text input fields that all followed the same pattern and had the same classes. I wanted a faster way to create these instead of having to copy and paste a block each time or, even worse, re-type it all out. With snippets, I could write the template for the form text input fields then define a shorthand to paste the snippet in place.

Here's a real example of a snippet I created.

{% highlight xml linenos %}
<snippet>
  <content><![CDATA[
<div class="form-group">
  {!! Form::label('$1', '${1/(^.)/\u\1/}:') !!}
  {!! Form::text('$1', null, ['class' => 'form-control']) !!}
</div> <!-- .form-group -->
]]></content>
  <!-- Optional: Set a tabTrigger to define how to trigger the snippet -->
  <tabTrigger>textfield</tabTrigger>
  <!-- Optional: Set a scope to limit where the snippet will trigger -->
  <scope>text.html.laravel-blade</scope>
  <description>
    Creates a Bootstrap form-group with a label and text field.Will fill in
    all three fields as you type with the name you give the field and the
    label will have the first letter capitalized.
  </description>
</snippet>
{% endhighlight %}

Line 2 defines what the snippet will paste. Here I want to create a Bootstrap form-group then add a Laravel Blade label and text field.

Lines 4 and 5 have $1. What will happen is, the cursor goes to $1 (then $2, $3, and so on if I'd defined those) so you can start typing right away. I put the cursor in the first argument to Form::label() and Form::text() because those have to match eachother for the label to be associated with the text input.

Furthermore, there is this exotic bit on Line 4.
`${1/(^.)/\u\1/}:`

This is a regular expression that will take the first character of whatever I'm typing, replace it with itself capitalized, and once it's done with the regular expression, it adds a semicolon to the end just for nice formatting of the label.

Line 9 says that when I type the word textfield then press tab, the snippet defined in `<content>` will be pasted.

Line 11 says this snippet will only work in certain types of files. Honestly, I'm not sure how it figures that you're in a blade.php file. I copied this scope from a Blade snippet I found on the web and it works so that was good enough for me.

Finally, Line 12 is simply a description of what the snippet does.

It took a bit to get the snippet working, but it wasn't that hard to do. In Sublime Text 3, you go to Tools > New Snippet and it opens a new file with snippet boilerplate. Also, there are a ton of Snippets you can download for free. I recommend at least giving them a try as they can make your work much faster.
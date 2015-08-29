---
title: Grunt Task Runner
date: 2015-08-29 18:00
excerpt: Tired of having to redo a bunch of small tasks every time you rebuild your website? About to rip your keyboard in half if you have to minify one more file? Learn a task runner framework and automate the boring stuff!
layout: post
featured_image: /assets/img/grunt-task-runner.png
---

# Grunt Task Runner #

## Automate the boring stuff ##

I just started a short term contract as a front end dev working with HTML, CSS, and Javascript. The task was to help build about a dozen webpages. My first task was to implement a [Masonry](http://masonry.desandro.com/ "Masonry") style layout. I'd heard about Masonry before because an image gallery I'd added to my brother's website used Masonry. However, I'd not actually played around with Masonry to see how it worked. So I was coming at this from a trial and error perspective. Lots of trial and error.

In the course of writing new features, one often needs to reload a webpage or app. If you have anything more complex than a very simple static page, there are probably several steps involved in reloading a page. For example, here's what my workflow looks like when I make a change to the stylesheet:

1. Make a change to a SCSS file
2. Run the SCSS files through the Sass preprocessor to generate a CSS file
3. Run the CSS file through Autoprefixer to add vendor specific prefixes
4. Reload all browsers (Chrome, Firefox, and IE)

![Broken keyboard]({{ site.url }}{{ site.baseurl }}/assets/img/broken-keyboard.jpg "Broken keyboard")

As you can imagine, this would become terribly tedious and annoying after just a few times. For larger projects this can become quite time consuming as you may need to minify CSS and JavaScript files, concatenate said files, compress images, run unit tests, run linters to check for syntax errors, etc. Fortunately, there are several task runners that can automate these processes and let you focus on actually writing code.

## Task runners ##

There are two popular Javascript-based task runners right now. [Grunt](http://gruntjs.com/ "Grunt") and [Gulp](http://gulpjs.com/ "Gulp"). Both task runners have large user communities. I forget why I picked Grunt now. Recently I read some arguments on Reddit for choosing Gulp instead because the config files are smaller, but I had already gotten set up with Grunt so meh.

I suppose one argument to be made for Grunt is that it seemingly has a larger number of available plugins. Grunt has 4,403 plugins listed on their site compared to Gulp's 1,780.

## Verdict ##

So far I am glad I got set up with Grunt. It took less than 4 hours for me to get everything set up. There was lots of documentation and forums that had tips for using Grunt. I would like to add a few more tasks to my Gruntfile just to get more practice with the tool. I think for my next project I will try out Gulp to see how it compares and if it's really that much easier to use.

Either way, I highly recommend just picking one and trying it out for yourself. It takes a little bit of set up, but there's lots of community support and it should save you time once it's up and running.
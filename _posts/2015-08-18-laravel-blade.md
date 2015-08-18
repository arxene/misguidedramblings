---
title: Up and Running with Laravel
date: 2015-08-18 17:20
excerpt: Where I experience the joys and sorrows of setting up Laravel and Homestead on Windows. Introduction to routing, controllers, views, Blade, and database migrations.
layout: post
featured_image: /images/cover.jpg
---

# Up and Running with Laravel #

## Homestead Setup Pains ##

It took me a day or two to get Laravel and Homestead set up, but it's finally working. One of the problems I ran into was trying to install Homestead with Composer as shown in the Laracast, Laravel 5 Fundamentals. I ended up with two installed locations of Homestead and I'm pretty sure I stil have some incorrectly configured paths because I run Homestead from one directory, but the Homestead.yaml file being used is in the other directory where Homestead is installed. I should probably clean that up, but I just want to go ahead and start playing with Laravel.

One of the other problems I had was editing the hosts file on my Windows 10 machine. I wasn't able to edit it, which seemed strange because I thought I could edit it in the past. I tried opening Notepad and running it as an administrator, but it sitll wouldn't let me save over the hosts file. After turning off Avira antivirus, I could edit and save the hosts file.

## Routing, Controllers, and Views oh my ##

Laravel has routing built in so that you can specify what controller is used when a given URL is visited. There's a file used just for routing and you specify which controller gets called for a given route. The controller then specifices which view to use, passing it any data the view needs. In this way, MVC architecture is accomplished. Keeping the application code and data in the controller makes it so the business logic stays in the controller and the presentation logic stays in the view.

## Blade ##

Blade is Laravel's templating language. It's like Liquid for Jekyll. It provides a nicer way to read and write PHP. It uses mustache braces like AngularJS to echo variables.

It allows you to create Blade layouts which serve as a template for views. Blade layouts let you create the common page elements and styling.

Blade also has control structures and loop constructs.

So far I'm really enjoying Blade and it's been easy to pick up.

## Migrations ##

Migrations are like source control for your database. They help keep team members current with the latest database schema. Honestly, I'm not sure exactly how it keeps people up to date because they still have to run a command to update their database, but whatever, I'll roll with it.

## Takeaways ##

So far, now that Laravel and Homestead is set up, everything else has been painfree. Routing, controllers, views, and Blade all came easily. I'm looking forward to learning more so I can actually build something with Laravel.

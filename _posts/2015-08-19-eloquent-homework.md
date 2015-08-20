---
title: Eloquent Homework
date: 2015-08-19 15:00
excerpt: Practicing Laravel's ORM, Eloquent
layout: post
featured_image: /images/cover.jpg
---

# Eloquent Homework #

At the end of the [Eloquent 101](https://laracasts.com/series/laravel-5-fundamentals/episodes/8 "Eloqent 101") video of the Learning Laravel 5 series, the teacher asks the viewer to practice using Eloquent.

The tasks he asks the viewer to complete on their own are:

- Create migration to make a dummy table
- Open file, set fields
- Migrate database
- Create model
- Play around with things using php artisan tinker
	- Create
	- Update
	- Fetch all records
	- Fetch specific records

The steps I took to do this:

1. `php artisan make:migration create_tasks_table --create="tasks"`
2. Open database/migrations/`<date>`-create_tasks_table.php
3. Added some fields to Tasks table in the file
4. php artisan migrate
5. php artisan make:model Tasks
6. Set $fillable property of Tasks model so mass assignment creates and updates work
7. php artisan tinker
	- Create
		1. $task = new App\Tasks;
		2. Set $task fields
			- Set date using `$task->due_date = '2015-09-01';`
		3. $task->save();
	- Create by Mass Assignment
		1. $task = App\Tasks::create(<associative array>);
	- Update
		1. Set $task to a specific record
		2. Set $task fields
		3. $task->save();
	- Update by Mass Assignment
		1. Set $task to a specific record
		2. `$task->update(<associative array>)`;
	- Fetch all
		1. App\Tasks::all();
	- Fetch specific records
		- `App\Tasks::find(<id number>);`
		- `App\Tasks::where('<field>', '<value>')->get();`	// get all Tasks where field == value, return as Collection
		- `App\Tasks::where('<field>', '<value>')->first();` // get first Tasks record where field == value
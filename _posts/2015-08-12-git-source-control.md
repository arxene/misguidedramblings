---
title: Git Source Control
layout: post
---

# Learning Git Source Control #

## Why use source control ##

Source control (also called version control or revision control) is a must for any modern software developer. If I were to find out in a job interview that a shop was not using source control, that would raise a red flag and I'd be hesitant about joining.

Here are some of the benefits and uses of source control:

-	Keeps a history of your file changes so you can revert back to a previous version of a file.
-	Having that history of changes makes it easier to find what change caused a bug and who made the change.
-	You can have multiple slightly or majorly different versions of your project. This is carried out through "branching" and "forking".
	-	Branching is what you do when you want to work on some new feature or fix a defect. You can work on your branch in isolation from the master production branch then merge it back later.
	- Forking is when you split off a copy from the master branch to work on it and don't merge it back to the master. This is often used to handle supporting different software versions.
-	Acts as a central copy of the files so more than one person can work on the project. Modern VCS (version control systems) make coordination easier.
	-	Compare with not using a VCS. A team could just have files on a shared drive. The problem is if two or more people need to work on the same file at the same time. One person makes their changes and saves it. In the meantime another person has been working on the original file and now saves their changed copy over the first person's changes which overwrites it. A VCS would prompt you to "merge" the other person's changes into your file before checking it in. This ensures you only check in the latest copy.

The reason I've chosen Git specifically to learn is that it is probably the most popular VCS for web development. Github is the sort of gold standard online repository for web projects.

I have some experience with VCS systems in the past, most notably using Team Foundation Server at my last job. However, I never really learned how to use it in depth. Just enough to do what was necessary for my job, mostly checking out, checking in, merging, and looking at the diffs between versions to find when a change was introduced and who committed it.

## Git workflow ##

Here's a basic workflow for contributing to a project that already exists.

1.	Get a copy of the master branch. The master branch is the main branch and should only have code that is shippable/deployable.
2.	Create a branch to work on
3.	Make changes and commit them to your branch
4.	Issue a pull request when you're ready to have your changes accepted to the master branch or just want a review of your code so far
5.	Unless it's a trivial change, you should hopefully receive some foodback on how to make your code better. Make whatever recommended changes you need to on your branch
6. Once everything looks good, it's time to merge your changes to the master branch. This means you get any changes that have happened to the code while you were working on your own copy. You want to make sure these changes don't break your code and that vice versa your code doesn't break any of the new or old stuff
7. The master branch gets deployed to production whether that is a web server, an executable, a zip, or however the team distributes the product

## A few final notes ##

Although Git does make collaborating with others and keeping track of changes easier, there are a few simple things you can do to make it really sing.

-	Use descriptive commit messages
	-	If your commit messages are unclear, it will be difficult for someone down the road to look through the commits and figure out what changed because now they have to look through the diff to try to determine what changed and why. Make sure to describe **why** a change was made as that's more important. Anyone can see *what* has changed by looking through the diff, but it still may not be apparent why the change was made in the first place.
-	Use the GitHub Pull Request feature to get feedback from other people or a code review. You can call someone to the Pull Request by name using the at symbol @ then their name.
-	This can be part of a continuous integration system that builds and deploy everything with one click. In fact, I may write about that next time.

## Helpful Links ##

[Learn Git Branching](http://pcottle.github.io/learnGitBranching/): An interactive Git tutorial  
[Understanding the GitHub Flow](https://guides.github.com/introduction/flow/): From GitHub Guides, a simple visual explanation
[Github Flow](http://scottchacon.com/2011/08/31/github-flow.html): by Scott Chacon on August 31, 2011. Goes into more detail about the link above.
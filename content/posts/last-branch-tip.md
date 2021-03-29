---
title: "More branches, more problems"
date: 2021-02-27T17:19:53-05:00
draft: false
published: false
---

Often I find myself hopping around git branches. Between PR review and having multiple branches in flight, I often forget the name of the branch I was working on. This isn't helped when branch names are prefixed with JIRA story codes and the team I'm working on. 

One of the best git tricks I learned when I first started working as a professional software engineer was the use of `-`. `-` is evaluated as the last branch you have checked out. So for example if you were on `branch1`, and checked out `main`. you could simply type:
```shell
{branch1} $ git checkout main 
{main} $ git checkout - 
{branch1} $ 
```

This command has been great for quickly accessing the last branch I was on, but my trouble has come when my HEAD is located more than one branch from the branch that I want. 

For example, let's say I start on `branch1`, and change branches twice.

```shell
{branch1} $ git checkout branch2 
{branch2} $ ...
# Time elapses...
{branch2} $ git checkout main 
{main} $ ...
# More time elapses...
{main} $ git checkout - 
{branch2} $ 
```

Now I've lost access to branch1, as running `git checkout -` would return to master. At this point you're probably thinking, "But Jerry, you can just remember the name of the branch". Sadly this is not the case when my branch names at work are commonly written in the following format:
```
teamname-JRT-2594--update_search_patterns_to_reflec_new_designs
```

It doesn't exactly roll off the tongue. Last week I took it upon myself to try and remedy this. After quite a bit of searching, this was the closest thing I could come up with as a solution. 

This command will show your local branches in descending order by most recent commits. Neat!

```shell
# Recent branches sorted desc 
$ git branch --sort=-committerdate
```
Which results in:
```shell
* main
branch1
branch3
branch2
```

Now I can easily see the last local branches that I've been working on. 

I have this assigned as an alias, `branches`.

If you'd like to add this to your own setup, you can run:
```shell
$ echo 'alias branches="git branch --sort=-committerdate"' >> ~/.profile
$ source ~/.profile
```

Feel free to change `.profile` to your dotfile of choice (`.bash_profile`, `.bashrc`,`.zsh`, etc).

Until next time!
 -Jerry

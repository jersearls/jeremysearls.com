---
title: "The Reflog is a Dev's Best Friend"
date: 2021-03-20T19:15:09-04:00
draft: false 
published: false
---
Often I have encountered developers who use source control as a part of their daily workflow that are intimidated by git. This seems especially true when a rebase goes south, or really anything occurs that deviates from the normal git behavior.

I recognize this intimidation, because it is one that I myself suffered from. However, one of the greatest gifts I received when I first started working as a software professional was a crash course from a senior developer on the use of the [reflog](https://git-scm.com/docs/git-reflog). What's the [reflog](https://git-scm.com/docs/git-reflog) you may be asking? Or you may have seen it and "noped" out of it immediately due to its confusing syntax and wall of text. If this is the case, then I'm here to say that the [reflog](https://git-scm.com/docs/git-reflog) is the Delorean of your dreams, and I'd love to be your Doc Brown. 

So whats the [reflog](https://git-scm.com/docs/git-reflog)?? Simply put, it is a "reference log" of every git command you've run. As the references are updated they are stored as a value of `HEAD@<number of moves ago>`. To see your reflog, simply type:
```
git reflog
``

Here's what my reflog looks like for this blog:
```bash
631f939 (HEAD -> master, origin/master) HEAD@{0}: commit (amend): update title
1723c1f HEAD@{1}: commit (amend): update title
eba4121 HEAD@{2}: commit: update title
2b4a617 HEAD@{3}: commit: add screenshot
17aa64b HEAD@{4}: commit: world of color post
42b4286 HEAD@{5}: commit: increase post number
```

I can now travel back in time to any point. Let's say I liked my original title, and don't want that updated title? I can simply move my pointer to `HEAD` at the commit prior to my title update commit.
```bash
$ git reset HEAD@{3} --hard
```

Which now points my `HEAD` to the commit before I changed the titles. 
```
2b4a617 (HEAD -> master, origin/master) HEAD@{0}: commit : add screenshot
```

Where I've found the reflog to be especially handy is when performing a rebase and something goes awry. When I first started using git, this is when I would delete my branch and fetch it from github, trying again from scratch and possibly losing my work if I hadn't recently pushed a commit. With the reflog I no longer have that problem. Simply view your reflog, and find the number `HEAD` was at when you started the rebase, and reset head to the reference one number greater. Or simply, the next entry that doesn't start with 'rebase'. For example:
```
skj34kj HEAD@{0}: rebase: a commit
29sksds HEAD@{1}: rebase: one more commit
alkj4sj HEAD@{2}: checkout: moving from master to my-local-branch

$ git reset HEAD@{2} --hard
```
Now you're back to before the rebase started!

Hopefully this post helps give some confidence to the git users out in the world that need it. 

Stay classy! -Jer

---
title: "Vim + Vscode = 😁"
date: 2021-03-06T20:36:25-05:00
draft: false
---

I love Elixir. This isn't a big secret if you talk to me about software for more than a minute. I also love VSCode and I'm not ashamed to say it. I suppose that's the developer equivalent of saying that starbucks is my favorite coffee. Just like starbucks, VSCode provides me the value of a consistent experience.  

When I first started writing software it felt like every senior developer I spoke with would espouse the merits of their personal setup. I decided early on to try as many different tools and settings as I could and see what I liked. This meant using Sublime, Atom, TextWrangler, Vim with Tmux and Tmate and a plethora of dot files with all kinds of shortcuts and tricks.

While the process of re-learning shortcuts and editors and setups was kind of a pain, I did gain a lot of insight into what I valued, and what wasn't important to me. 

For example, I am obsessed with Vim bindings. Not having to touch a mouse while coding is a massive benefit to me and I know it has directly contributed to my productivity. However, I was not a fan of Vim packages and package managers. This combined with a complex `.vimrc` and `.tmux.conf` resulted in a Jenga like setup that I seemed to spend more time tuning than actually using to code.  

When I started writing Elixir full-time professionally in 2018, I decided I still wanted to use the vim bindings I had painstakingly learned, but I wanted to try a different editor. I had played with VSCode in the past, but it hadn't felt "ready for prime time" yet. Upon download and adding a few extensions, I could instantly tell that this was no longer the case. 

Being able to quickly add and remove extensions and easily browse for new ones is a huge advantage to VSCode. Simply installing the [Vim](https://marketplace.visualstudio.com/items?itemName=vscodevim.vim) extension means that I'm interacting with VSCode using the Vim bindings I'm familiar with.

What makes this really stand out from other editors I've used, is custom bindings combined with the [Live Share](https://marketplace.visualstudio.com/items?itemName=MS-vsliveshare.vsliveshare) extension. Live Share enables you to collaboratively edit and debug with others in real time. The clincher being that each participant gets to use their own bindings and have their own cursor. Unlike sharing options like [TMate](https://tmate.io), I can use my Vim binding and all my personal extensions, without forcing them upon my pairs.  

While it may still have some kinks that need to be worked out, I can still definitively say that Live Share alters the paradigm of pair programming. It is the best solution to truly concurrent multi-participant programming.

More posts about Elixir VSCode, and Live Share to come. 

Happy hacking friends!

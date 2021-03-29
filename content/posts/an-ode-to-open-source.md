---
title: "An Ode to Open Source"
date: 2021-03-28T17:04:03-04:00
draft: false
tags: elixir, open source 
canonical_url: https://jeremysearls.com/posts/an-ode-to-open-source/
---

There are a lot of things that I love about my job. As a software engineer for Cars.com, I get to work on cool problems with great people on an awesome tech stack. One of the best parts of our tech stack is our heavy reliance on open source software. We rely on a myriad of different technologies that leverage software that is written to be shared, free of charge, with the outside world. We're even utilizing an open-source package [that I wrote](https://hex.pm/packages/attrition) and had the pleasure of speaking about at the [2020 ElixirConf](https://youtu.be/zTHCEZVL4Kw).

My work at Cars.com often deals with...you guessed it! Cars! Specifically, the makes (sometimes referred to as the manufacturer) and models that we use to identify cars (ex. a Ford Escape). In order to test our code we utilize an awesome Elixir package called [faker](https://hex.pm/packages/faker). There are many flavors of faker in multiple programming language, but the core tenants remain the same. They "fake" data. Say you need an example of an email address? Faker can generate one for you. This is a great way to strengthen your automated tests, as the generated data may not always conform to your code, and can identify possible bugs before they become issues in production applications.

Recently while writing a parser that will extract a vehicle's make and model from a string, I utilized [faker's Vehicle module](https://github.com/elixirs/faker/tree/master/lib/faker/vehicle) to generate a "make" and a "model" for testing. However, as someone that has worked in the automotive business for two years, I noticed that the generated makes and models only had a single word, however in the real world, we have makes like "Aston Martin" and complex models like a "AMG GLB 35".

Why is this important? Well it means that we're testing parsing a make-model of "Ford Escape" when in reality the data we could encounter could be a make-model of "Aston Martin DB AR1 Zagato". This is significantly more complex data, and would undoubtedly break a naive parsing implementation that relied on the simple supplied data. 

What can you do? Well, as the title suggests, this is indeed where I wax poetically about the benefits of not only utilizing open source software, but becoming an active participant. Instead of simply updating our own tests to create more robust generated data, I instead chose to open a [pull request](https://github.com/elixirs/faker/pull/408) to the faker module itself. Now anyone using this module will benefit from having their data conform to more realistic examples, and hopefully avert errors in production. 

I've heard time and again from developers that they either "don't have time" for contributing to open source, or more commonly don't feel comfortable doing so. I guarantee, you ARE good enough, smart enough and have the time. When more people contribute and give back, the tools we all use get better, and the software we create ultimately benefits. So here are my tips for first time contributors:
1. Start looking at source code of packages/libraries you regularly use. This is especially true when you notice a bug, or an area that can be improved upon.
2. Create a fork of the library. This can easily be done in the github UI.
3. Git clone your fork onto your local machine and start playing around on a new branch. See if you can add something useful, make a meaningful refactor or fix a bug.
4. Look at the contributing guidelines for pull requests. This will often be found at the root of the project in a file called `CONTRIBUTING.md`.
5. Push up your forked repo's new branch to github. Github will automagically create a pr template for your branch to be merged into the default branch of the original repo you forked from.
6. Ensure that you're following the maintainers guidelines and open your PR! Worst case, they reject it, and that's ok! Perhaps the author is working on a similar feature or fix, or they'll request changes.

If your code is merged, your work is now part of the public good! Giving back feels great, especially with all the "taking" we do as open source software developers. 

That's it for this week. Bye friends!


---
title: "The Capture Operator"
date: 2021-04-07T19:37:27-04:00
draft: false
---

If you have written Elixir with me, or have been subjected to one of my pull request reviews, you'll know that one of my favorite ways to refactor code is by adding the capture operator when an anonymous function is required. 

What is the capture operator? Well, you may know it as the ampersand or "&" character, but when writing Elixir it takes on a special meaning.

The capture operator ("&") gives us the ability to create an anonymous function with shorthand syntactic sugar. 

The example below is a familiar sight for Elixir users. 
We call `Enum.map/2` and pass an anonymous function to perform addition
on each iterable that is passed from a given list. 

```elixir
iex> Enum.map([1,2,3], fn number -> number + 3 end)
[4, 5, 6]
```

Now we implement the capture operator ("&"); capturing each iterable of the list of numbers ([1,2,3]) and assign each iterable to the variable &1 as it is passed through the mapping function.

```elixir
iex> Enum.map([1,2,3], &(&1 + 3))
[4, 5, 6]
```

This is one quick example of how powerful this syntax can be and, once mastered, is cleaner and easier to read than the original. 

Want to learn more about the capture operator? You're in luck!

I had the pleasure of contributing to [Elixir School](https://elixirschool.com/) a few months ago. Specifically, a lesson about...you guessed it! [The capture operator](https://elixirschool.com/en/lessons/basics/enum/#enum-using-the-capture-operator-). 

And if YOU have something to teach, or add to my lesson, Elixir School is an [open source repository](https://github.com/elixirschool/elixirschool), please contribute and help others learn Elixir. 

Hope you have a great week! -Jerry

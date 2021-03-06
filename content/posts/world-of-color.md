---
title: "IO.ANSI: A World of Color"
date: 2021-03-14T21:08:12-04:00
draft: false
---

Viewing debug text while running a server can be challenging. This holds true while running a Phoenix server. Thankfully there is a fantastic module included with the Elixir standard library.

[IO.ANSI](https://hexdocs.pm/elixir/IO.ANSI.html#format/2) provides an easy way to inject colors into your terminal text. As server output text flies across your terminal, being able to color not only debug text, but the background of the text as well is extremely helpful. 

You can quickly play with this functionality in iex.

Spin up a REPL by running the iex command in your terminal:
```
$ iex
```

Set a string to play as your debug string
```
debug_text = "hello barnaby"
```

Now call the variable using the format/2 function and use the atom `:red` to set the terminal text to red. The atom corresponds to the function [red/0](https://hexdocs.pm/elixir/IO.ANSI.html#red/0). You'll quickly see in the documentation the other available functions you can use to decorate your text.

```
IO.puts(IO.ANSI.format([:red, debug_text])) 
```

This is great! But let's go even further. Highlighting the text by altering the background color is especially useful.

We can do this by passing an additional atom to set the background color. We'll use [cyan_background/0](https://hexdocs.pm/elixir/IO.ANSI.html#cyan_background/0)

```
IO.puts(IO.ANSI.format([:red, :cyan_background, debug_text]))
```

{{< figure src="/img/color_terminal.png" title="Isn't it lovely?" >}} 

That's it! Super easy and really handy! Play around with it and I hope it helps track down your next bug. 

Until next time! -Jerry

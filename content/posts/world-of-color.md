---
title: "World of Color"
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

Now call the variable using the format\2 function
```
IO.puts(IO.ANSI.format([:red, debug_text])) 
```

This is great! But let's go even further. Highlighting the text by altering the background color is especially useful.

```
IO.puts(IO.ANSI.format([:red, :cyan_background, debug_text]))
```

{{< figure src="/img/color_terminal.png" title="Isn't it lovely?" >}} 

That's it! Super easy and really handy! Play around with it and I hope it helps track down your next bug. 

Until next time! -Jerry





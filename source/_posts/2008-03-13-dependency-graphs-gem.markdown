---
layout: post
title: "A dependency graphs gem"
date: 2008-03-13T01:06:00-03:00
categories:
 - Ruby
 - C#
comments: true
---
Some days ago I had to do a big refactoring involving almost 100 C# projects, a little monster. I thought it would be very helpful to have a dependency graph that could quickly show me the projects dependencies I was interested in at any given moment and that would let me apply some filters to the result.
I didn't like the few things I found in the net so I did a Ruby program to traverse csproj files and generate a [Graphviz](http://www.graphviz.org/) graph with the desired results, something like this:

{% img center http://depgraph.rubyforge.org/image1.png %}

So as I thought this could be useful to a lot of people I decided to make it open source so I created [this Rubyforge project](http://depgraph.rubyforge.org) to host it.

I made some changes to make it generic so that it could be used for any kind of text files that have parseable dependencies hidden inside. 
There are 2 examples stored in a yaml configuration file that deal with C# projects and Ruby `requires` statements.

So for example, if you want to graph your C# projects you do this from the root directory:

```bash
depgraph -type csproj
```

And if you want to graph the requires dependencies of your Ruby files you do this:

```bash
depgraph -type ruby_requires
```

Then if you add a new entry in the yaml configuration file you'll be able to do this:

```bash
depgraph -type [new entry name]
```

You can also filter by directories and node name regular expressions against source and dependency targets. I'll add more functionality in next releases but it's already usable.

To install it:

```bash
gem install DepGraph
```

As always, check the [project's webpage](http://depgraph.rubyforge.org/) and the [specs](http://depgraph.rubyforge.org/specs.html) for more info.

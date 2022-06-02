---
title: "methods"
date: "2022-06-01 22:28"
author: "[Doriel Rivalet](https://github.com/DorielRivalet)"
tags:
- ruby
- the-odin-project
- methods
---

# Metadata
2022-06-01 22:28  | methods | [Doriel Rivalet](https://github.com/DorielRivalet)

# Content
implicit return

```ruby
def my_name
  "Joe Smith"
end

puts my_name #=> "Joe Smith"
```

```ruby
def even_odd(number)
  unless number.is_a? Numeric
    "A number was not entered."
  end

  if number % 2 == 0
    "That is an even number."
  else
    "That is an odd number."
  end
end

puts even_odd(20) #=>  That is an even number.
puts even_odd("Ruby") #=>  A number was not entered.
```

```ruby
phrase = ["be", "to", "not", "or", "be", "to"]

puts phrase.reverse.join(" ").capitalize
#=> "To be or not to be"
```

Chaining methods together like this effectively has each method call build off of the outcome of the previous method in the chain. The process that takes place essentially produces the following steps:

```ruby
["be", "to", "not", "or", "be", "to"].reverse
= ["to", "be", "or", "not", "to", "be"].join(" ")
= "to be or not to be".capitalize
= "To be or not to be"
```

predicate methods: returns true/false

You can also create your own method with a `?` at the end of its name to indicate that it returns a Boolean.

A general rule in programming is that you do not want your methods to overwrite the objects that you call them on.

By adding a `!` to the end of your method, you indicate that this method performs its action and simultaneously overwrites the value of the original object with the result.

```ruby
puts whisper.downcase! #=> "hello everybody"
puts whisper #=> "hello everybody"
```

Writing `whisper.downcase!` is the equivalent of writing `whisper = whisper.downcase`.

procedure is also a name for a method

method definitions create their own scope that's entirely outside of the execution flow.

When this program starts running, the call stack initially has one item -- called a **stack frame** -- that represents the global (top-level) portion of the program. The initial stack frame is sometimes called the `main` method. Ruby uses this frame to keep track of what part of the main program it is currently working on.

same as c++ int main()

push and pop the call stack.

-   [Objects have classes](http://ruby-for-beginners.rubymonstas.org/objects/classes.html)
-   [Classes create objects](http://ruby-for-beginners.rubymonstas.org/objects/instances.html)
-   [Objects have methods](http://ruby-for-beginners.rubymonstas.org/objects/methods.html)

Variables name things, methods name behaviour (code).

If we don’t do anything else, then a method will return the return value of the last evaluated statement.

In our example method …

```
def add_two(number)
  number + 2
end

p add_two(3)
```

… the last evaluated statement is the expression `number + 2`. Since in our example `number` is assigned `3` this expression returns the number `5`, and that is why the value returned by our method also is `5`.

u cant reference something outside of the scope u are in

Use :: for describing class methods, # for describing instance methods, and use . for example code.

\# = [“octothorpes”](https://en.wiktionary.org/wiki/octothorpe).

# Sources
Own notes

https://www.theodinproject.com/lessons/ruby-methods

https://launchschool.com/books/ruby/read/methods

http://ruby-for-beginners.rubymonstas.org/writing_methods.html

# Content Lists
If you prefer browsing the contents of this site through a list instead of a graph, you can find content lists here too:

- [All Notes](notes/)

## Knowledge Index
- [The Odin Project](notes/index-list/the-odin-project.md)
- [Open Source Society University](notes/index-list/open-source-society-university.md)
- [Full Stack Open](notes/index-list/fullstack-open.md)
- [Miscellaneous](notes/index-list/miscellaneous.md)
- [Quartz](notes/index-list/quartz.md)


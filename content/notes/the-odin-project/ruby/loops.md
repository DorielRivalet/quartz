---
title: "input-and-output"
date: "2022-05-30 02:24"
author: "[Doriel Rivalet](https://github.com/DorielRivalet)"
tags:
- ruby
---

# Metadata
2022-05-26 18:48

loops

# Content

```ruby
i = 0
loop do
  puts "i is #{i}"
  i += 1
  break if i == 10
end
```

```lua
i = 0
while true do
	print("i is "..i)
	i = i + 1
	if i==10 break
	end
end
```

```ruby
5.times do |number|
  puts "Alternative fact number #{number}"
end
```

next: to next iteration
break: the current iteration

Rubyists

dot operator

 By convention, we use the curly braces (`{}`) when everything can be contained in one line. We use the words `do` and `end` when we are performing multi-line operations.
 
 When this program starts running, the call stack initially has one item -- called a **stack frame** -- that represents the global (top-level) portion of the program. The initial stack frame is sometimes called the `main` method. Ruby uses this frame to keep track of what part of the main program it is currently working on.
 
 this is why theres that main in c++ programs and the like
 
call stack, push and pop

if, unless
while, until


# Sources

https://www.theodinproject.com/lessons/ruby-loops

https://launchschool.com/books/ruby/read/loops_iterators
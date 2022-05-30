---
title: "input-and-output"
date: "2022-05-30 02:24"
author: "[Doriel Rivalet](https://github.com/DorielRivalet)"
tags:
- #ruby
---


# Metadata
2022-05-26 00:47

input and ouput

# Content
`puts` appends a new line to the argument passed in, whereas `print` keeps things all on one line.

#chomp is a method commonly used to trim separators.

```ruby
puts [1,2]

1

2

print [1,2]

[1,2]
```

-   puts always returns nil
-   p returns the object you pass to it

so the hash rocket, =>, would show the object passed

pretty printing arrays and hashes

-   [What are the two methods we can use to output data to the user’s screen?](https://www.theodinproject.com/lessons/ruby-input-and-output#output-commands)

print and puts

-   [What is similar between these two output methods?](https://www.theodinproject.com/lessons/ruby-input-and-output#output-commands)

they return nil

-   [What is different between these two output methods?](https://www.theodinproject.com/lessons/ruby-input-and-output#output-commands)

puts has newline, print doesnt

-   [What is the method you can use to get input from the user?](https://www.theodinproject.com/lessons/ruby-input-and-output#input-commands)

gets

-   [What is at least one difference between the output and input methods?](https://www.theodinproject.com/lessons/ruby-input-and-output#input-commands)

doesnt return nil

# Sources
https://www.theodinproject.com/lessons/ruby-input-and-output

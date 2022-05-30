---
title: "input-and-output"
date: "2022-05-30 02:24"
author: "[Doriel Rivalet](https://github.com/DorielRivalet)"
tags:
- ruby
---

# Metadata
2022-05-25 23:38

Variables

# Content

|varName| local/private

do end {}

tokens
do, make block
end, finalize block
{, make block
}, finalize block

see: lexical anaylizer, interpreter, etc.

reminder: # for comments in ruby
irb to test commands and other things in terminal
ruby filename.rb to run files in ruby environment

curly braces for one liners, do end otherwise

variables declared as is are local by default

eg ```x = 1``` defined inside a function can only be accessed by that function, in that function scope.
so if u print that x outside the function scope it will give an error


methods with a bang (!) mutate (change) the original object.
```
-   a = "answer" 

-   a.capitalize    #returns "Answer" 

-   a                    # returns "answer", < the original string object wasn't changed. 

-   a.capitalize!   #returns "Answer" 

-   a                    #returns "Answer"  < the original string object has been changed.
```
assignment can be expressed as := in other programming languages

snake_case PascalCase cammelCase

# Sources

https://www.theodinproject.com/lessons/ruby-variables

https://launchschool.com/books/ruby/read/variables

https://www.quora.com/What-does-it-mean-if-a-Ruby-method-ends-in-an-exclamation-mark

https://stackoverflow.com/questions/612189/why-are-exclamation-marks-used-in-ruby-methods#:~:text=Bang%20or%20exclamation%20mark%20means,replace%2C%20followed%20by%20saving.%20!

http://ruby-for-beginners.rubymonstas.org/variables/right_goes_first.html
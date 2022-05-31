---
title: "data-types"
date: "2022-05-30 02:24"
author: "[Doriel Rivalet](https://github.com/DorielRivalet)"
tags:
- data-types
- ruby
- the-odin-project
---

# Metadata
2022-05-25 20:30

Data Types

# Content

It’s important to keep in mind that when doing arithmetic with two integers in Ruby, _the result will always be an integer_.

```ruby
17 / 5    #=> 3, not 3.4
```

To obtain an accurate answer, just replace one of the integers in the expression with a float.

```ruby
17 / 5.0  #=> 3.4
```

.to_f  .to_i
.even? .odd?
Concatenation
In true Ruby style, there are plenty of ways to concatenate strings.

# With the plus operator:
"Welcome " + "to " + "Odin!"    #=> "Welcome to Odin!"

# With the shovel operator:
"Welcome " << "to " << "Odin!"  #=> "Welcome to Odin!"

# With the concat method:
"Welcome ".concat("to ").concat("Odin!")  #=> "Welcome to Odin!"

.to_s   

in Ruby, everything is an object

:my_symbol

string interpolation

"My favorite number is #{a}!"

symbol: immutable string

something about floats:
the inaccuracies may be linked as to how, for example, in 3d games the further away you go from the point of origin, the more odd the graphics can get.

### [Hashes](https://launchschool.com/books/ruby/read/basics#hashes)

A **hash**, sometimes referred to as a dictionary, is a set of key-value pairs. Hash literals are represented with curly braces `{ }`. A key-value pair is an association where a key is assigned a specific value. A hash consists of a key, usually represented by a symbol, that points to a value (denoted using a `=>`) of any type of data. Let's make some hashes to get the feel of it. Type along!

```irb
irb :001 > {:dog => 'barks'}
=> {:dog => 'barks'}
```

hash rocket is =>

## [Expressions and Return](https://launchschool.com/books/ruby/read/basics#expressionsandreturn)

You may have noticed, indirectly at this point, that every time you enter something into irb you see the `=>` back, which is called a _hash rocket_ (cool name, huh?), followed by whatever your Ruby expression returns. When you type something in at the irb prompt you are creating an expression. An **expression** is anything that can be evaluated, and pretty much everything you write in Ruby is an expression. An expression in Ruby always returns something, even if that's an error message or `nil`. We'll talk in more depth about `return` as we move on, but remember that _Ruby expressions always return a value_, even if that value is `nil` or an error.

An OBJECT is a location in computer memory where you can store DATA (aka VALUES).

There are many kinds of objects, including String, Number, Array, Hash, Time, ...


```
bundle install
```

This folder contains a Gemfile, which tells bundle which gems to install locally and makes them available for use in that directory. In this case, we are installing RSpec, which is a popular Ruby testing framework.

so rspec is like jest for javascript

```ruby
"MyString".methods.sort
```

```ruby
"MyString".own_methods.sort
```

-   Numbers
    -   [What are the basic arithmetic operators you can use on numbers?](https://www.theodinproject.com/lessons/ruby-basic-data-types#numbers)
```
+-*/%`
```

   -   [What’s the difference between an integer and a float?](https://www.theodinproject.com/lessons/ruby-basic-data-types#integers-and-floats)

```ints are 1 2 3 4 floats are 1.0 2.0 3.0 4.0 ```

	
   -   [What method would you use to convert a float to an integer?](https://www.theodinproject.com/lessons/ruby-basic-data-types#converting-number-types)

.to_i .to_f

    -   [What method would you use to convert an integer to a float?](https://www.theodinproject.com/lessons/ruby-basic-data-types#converting-number-types)
-   Strings
    -   [What is a string?](https://www.theodinproject.com/lessons/ruby-basic-data-types#strings)

a group of 1 or more characters. a data type.


   -   [What are the differences between single and double quotes?](https://www.theodinproject.com/lessons/ruby-basic-data-types#double-and-single-quotation-marks)
	
double quotes allows string interpolation, similar to javascripts ``
	
	
   -   [What is string interpolation?](https://www.theodinproject.com/lessons/ruby-basic-data-types#interpolation)

a = `#{varName}`

interpolation comes from inserting something of another type
a string is a data type
u insert something thats not a string into that string

   -   [How do you concatenate strings?](https://www.theodinproject.com/lessons/ruby-basic-data-types#concatenation)
	
with + or .. or >>, depends on language
	
	
   -   [What method would you use to change all the characters in your string to upper case?](https://www.theodinproject.com/lessons/ruby-basic-data-types#upcase)
	
	string.upcase

	
   -   [What method would you use to split up strings into arrays?](https://www.theodinproject.com/lessons/ruby-basic-data-types#split)

the string.split() method


   -   [What are escape characters?](https://www.theodinproject.com/lessons/ruby-basic-data-types#escape-characters)

for inserting, for example, newlines
eg /n is newline
thers also tabs, /t
etc


   -   [How do you access a specific character or substring?](https://www.theodinproject.com/lessons/ruby-basic-data-types#substrings)

index the string

indexing can be done with []

so

do string[number]

for a range do string[start..end]

   -   [How do you convert other data types into strings?](https://www.theodinproject.com/lessons/ruby-basic-data-types#converting-other-objects-to-strings)

.to_s


-   Symbols
    -   [What is a symbol?](https://www.theodinproject.com/lessons/ruby-basic-data-types#symbols)

an immutable string

   -   [How do you create a symbol?](https://www.theodinproject.com/lessons/ruby-basic-data-types#create-a-symbol)
	
with : before the symbol name
	
   -   [What’s the difference between a symbol and a string?](https://www.theodinproject.com/lessons/ruby-basic-data-types#symbols-vs-strings)

string are mutable, meaning that it can change

-   Booleans
    -   [What does `true` represent?](https://www.theodinproject.com/lessons/ruby-basic-data-types#true-and-false)

1

   -   [What does `false` represent?](https://www.theodinproject.com/lessons/ruby-basic-data-types#true-and-false)
	
0	
	
   -   [What does `nil` represent?](https://www.theodinproject.com/lessons/ruby-basic-data-types#nil)
	
nothingness, for example when u declare a variable but dont assign a value yet. not to be confused with assigning it the value of 0



# Sources

https://www.theodinproject.com/lessons/ruby-basic-data-types

https://launchschool.com/books/ruby/read/basics
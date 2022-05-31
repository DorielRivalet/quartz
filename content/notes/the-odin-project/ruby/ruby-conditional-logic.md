---
title: "conditional logic"
date: "2022-05-30 02:24"
author: "[Doriel Rivalet](https://github.com/DorielRivalet)"
tags:
- ruby
- the-odin-project
---


# Metadata
2022-05-26 01:17

conditional logic

# Content
The only false values in Ruby are the values `nil` and `false` themselves

If there is only one line of code to be evaluated inside the block, then you can rewrite the code to be more succinct and take up only one line:

```ruby
puts "Hot diggity damn, 1 is less than 2" if 1 < 2
```

.eql? in ruby is === in js

 IRB, short for **Interactive Ruby**, is a quick way to explore the Ruby programming language and try out code without creating a file. IRB is a Read-Eval-Print Loop, or REPL, a tool offered by many modern programming languages.
 
 `#equal?` checks whether both values are the exact same object in memory. This can be slightly confusing because of the way computers store some values for efficiency. Two variables pointing to the same number will usually return `true`.

```ruby
a = 5
b = 5
a.equal?(b) #=> true
```

This expression is true because of the way computers store integers in memory. Although two different variables are holding the number 5, they point to the same object in memory. However, consider the next code example:

```ruby
a = "hello"
b = "hello"
a.equal?(b) #=> false
```

This happens because computers can’t store strings in the same efficient way they store numbers. Although the values of the variables are the same, the computer has created two separate string objects in memory.

In addition to the above operators, Ruby has a special operator that is affectionately referred to as the **spaceship operator**. Unlike the other comparison operators, which all return `true` or `false`, the spaceship operator returns one of three numerical values.

`<=>` (spaceship operator) returns the following:

-   `-1` if the value on the left is less than the value on the right;
-   `0` if the value on the left is equal to the value on the right; and
-   `1` if the value on the left is greater than the value on the right.

```ruby
5 <=> 10    #=> -1
10 <=> 10   #=> 0
10 <=> 5    #=> 1
```


**short circuit evaluation** is used in ruby to make it more efficient

You should use an `unless` statement when you want to **not** do something if a condition is `true`, because it can make your code more readable than using `if !true`.

 **your code needs to be readable and understandable by other people**, especially in the development stage. You can always optimize your code for efficiency once it’s finished and you’re moving to a production environment where speed matters.
 
 must use "then" keyword when using 1-line syntax
 
 case/switch statements have more overhead than if statements, but it can be more readable

-   [What is a Boolean?](https://www.theodinproject.com/lessons/ruby-conditional-logic#boolean-logic)

a data type that is stored in 1 byte which holds the values of either true or false

-   [What are “truthy” values?](https://www.theodinproject.com/lessons/ruby-conditional-logic#truthy-and-falsy-in-ruby)

in ruby, anything that isnt false nor nil

-   [Are the following considered true or false: `nil`, `0`, `"0"`, `""`, `1`, `[]`, `{}` and `-1`?](https://www.theodinproject.com/lessons/ruby-conditional-logic#truthy-and-falsy-in-ruby)

all true except nil

-   [When do you use `elsif`?](https://www.theodinproject.com/lessons/ruby-conditional-logic#adding-else-and-elsif)

to create another conditional

-   [When do you use `unless`?](https://www.theodinproject.com/lessons/ruby-conditional-logic#unless-statements)

to make a code run when something is not true

-   [What do `||` and `&&` and `!` do?](https://www.theodinproject.com/lessons/ruby-conditional-logic#logical-operators)

and, or , not
and checks if all conditionals are true
or checks if at least one is true
not makes the inverse boolean

-   [What is short circuit evaluation?](https://www.theodinproject.com/lessons/ruby-conditional-logic#logical-operators)

a way to make logic more efficient
if when using and, at least one value is evaluated to false, then skip all other evaluatioin
if when using or, same thing but check when an expression evaluates to true

-   [What is returned by `puts("woah") || true`?](https://www.eriktrautman.com/posts/ruby-explained-conditionals-and-flow-control)

true

-   [What is the ternary operator?](https://www.theodinproject.com/lessons/ruby-conditional-logic#ternary-operator)

a way to write logic in a more succint way
syntax is conditional ? iftrue : iffalse

-   [When should you use a case statement?](https://www.theodinproject.com/lessons/ruby-conditional-logic#case-statements)

when having a lot of conditionals or when making if statements would create too many nested ifs. keep in mind that if statements are more efficient in memory in most use cases though.

**how Ruby chooses a path through your program, aka "flow control"**

```
> 1 <=> 1000
=> -1
> 1 <=> 1
=> 0
> 1 <=> -1000
=> 1
```



# Sources
https://www.theodinproject.com/lessons/ruby-conditional-logic

---
title: "ruby-arrays"
date: "2022-05-30 02:23"
author: "[Doriel Rivalet](https://github.com/DorielRivalet)"
tags:
- ruby
- arrays
- the-odin-project
---

# Metadata
2022-05-26 20:38

arrays

# Content

shovel operator `<<`

`#shift` and `#unshift` first elements
pop and push last elements

```ruby
num_array.methods       #=> A very long list of methods
```

Both the `push` and the `<<` methods mutate the caller, so the original array is modified.

The `map` method iterates over an array applying a block to each element of the array and returns a new array with those results. The irb session below shows how to use `map` to get the square of all numbers in an array. The `collect` method is an alias to `map` - they do the same thing.

```irb
irb :001 > a = [1, 2, 3, 4]
=> [1, 2, 3, 4]
irb :002 > a.map { |num| num**2 }
=> [1, 4, 9, 16]
irb :003 > a.collect { |num| num**2 }
=> [1, 4, 9, 16]
irb :004 > a
=> [1, 2, 3, 4]
```

adding ! makes mutations

prefix, before
suffix, after
interfix, inbetween

"destructive" here just means mutating the caller).

"is this method returning new data, or is the original data being modified?".

use `each` for iteration and `map` for transformation.


# Sources

https://launchschool.com/books/ruby/read/arrays

https://www.theodinproject.com/lessons/ruby-arrays
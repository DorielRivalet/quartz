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

array.first.last

array.includes?(v)

words.size

Notice that when you reference an index of a string that is beyond the length of the string, Ruby returns `nil` and doesn't throw an error.

| Operation  | Methods               |
| ---------- | --------------------- |
| initialize | Array.new, [], %w     |
| read       | [0], first, last      |
| add        | push, <<, unshift     |
| remove     | pop, delete_at, shift |

numbers.select { |n| n > 10 }

numbers.uniq

random: numbers.sample

numbers.take(3) same as numbers[0,3]

You can do more advanced Ruby array slicing. For example, you may want to get all the elements but the first one:

numbers[1..-1]

Notice the difference between using a comma (`0,3`) & a range (`1..-1`). The first one says "get me 3 elements starting at index 0", while the last one says "get me the characters in this range".

arr.size is same as arr.length ?

remove nil: numbers.compact

```ruby
# Faster, because this changes the users array

users.concat(new_users)

# Slower, because this creates a new array

users += new_users
```

You can also remove elements from one array like this, where `users_to_delete` is also an array:

```users = users - users_to_delete```

Finally, you can get the elements that appear in two arrays at the same time:

```users & new_users```

sets operations: union | , difference -, intersection &

# Sources

https://launchschool.com/books/ruby/read/arrays

https://www.theodinproject.com/lessons/ruby-arrays

https://www.rubyguides.com/2015/05/ruby-arrays/

https://www.endpointdev.com/blog/2011/06/using-set-operators-with-ruby-arrays/
---
title: "basic-enumerable-methods"
date: "2022-06-03 18:42"
author: "[Doriel Rivalet](https://github.com/DorielRivalet)"
tags:
- ruby
- the-odin-project
---

# Metadata
2022-06-03 18:42  | basic-enumerable-methods | [Doriel Rivalet](https://github.com/DorielRivalet)

# Content
The **do** is optional in a for loop in Ruby and may cause issues if used in IRB

| block variable |

This is the element from your array that the block is currently iterating over. You can use any variable name that you find helpful here

For multi-line blocks, the commonly accepted best practice is to change up the syntax to use `do...end` instead of `{...}`:

`#map` method (also called `#collect`) transforms each element from an array according to whatever block you pass to it and returns the transformed elements in a new array.

its like commutativity of multiplication a\*b, a being the array element and b being the block

```ruby
item.gsub('string to change', 'string end result')
```

`#select` method (also called `#filter`)

```#reduce``` is replacement for accumulator variables

`#reduce` method (also called `#inject`)

```ruby
[1,2,3].reduce(initial_accumulator_value) {|accumulator, value| stuff}
```


```ruby
votes = ["Bob's Dirty Burger Shack", "St. Mark's Bistro", "Bob's Dirty Burger Shack"]

votes.reduce(Hash.new(0)) do |result, vote|
  result[vote] += 1
  result
end
#=> {"Bob's Dirty Burger Shack"=>2, "St. Mark's Bistro"=>1}
```

bang methods make the methods destructive, mutates the object.

the ruby way 

```ruby
friends = ['Sharon', 'Leo', 'Leila', 'Brian', 'Arun']

def invited_friends(friends)
  friends.select { |friend| friend != 'Brian' }
end

friends
#=> ['Sharon', 'Leo', 'Leila', 'Brian', 'Arun']

invited_friends(friends)
 #=> ["Sharon", "Leo", "Leila", "Arun"]
```

enumerable methods are used on both arrays and hashes

**Enumerable Iterators Cheat Sheet**

-   `#each` returns the original object it was called on because it's really used for its side effects and not what it returns
-   `#each_with_index` passes not just the current item but whatever position in the array it was located in.
-   `#select` returns a new object (e.g. array) filled with only those original items where the block you gave it returned `true`
-   `#map` returns a new array filled with whatever gets returned by the block each time it runs.

The full list is available [in the docs here](http://ruby-doc.org/core-2.0/Enumerable.html).

-   `#any?` returns true/false (see the question mark?) and answers the question, "do ANY of the elements in this object pass the test in my block?". If your block returns true on any time it runs, `any?` will return true.
-   `#all?` returns true/false and answers the question, "do ALL the elements of this object pass the test in my block?". Every time the block runs it must return true for this method to return true.
-   `#none?` returns true only if NONE of the elements in the object return true when the block is run.
-   `#find` returns the first item in your object for which the block returns true.

**Awesome but less common methods**

-   `#group_by` will run your block and return a hash that groups all the different types of returns from that block. For example:
    
    ```
    > names = ["James", "Bob", "Joe", "Mark", "Jim"]
    > names.group_by{|name| name.length}
    => {5=>["James"], 3=>["Bob", "Joe", "Jim"], 4=>["Mark"]} 
    ```
    
-   `#grep` returns an array with those items that actualy match the specified criteria (RegEx) (using a `===` match)
    
    ```
    > names.grep(/J/)
    => ["James", "Joe", "Jim"]
    ```

```ruby
array = %w(a b c) #a word of a b and c

array.map.with_index { |ch, idx| [ch, idx] }

# [["a", 0], ["b", 1], ["c", 2]]

["11", "21", "5"].map(&:to_i)
["orange", "apple", "banana"].map(&:class)
```

.each{key value}
.each_with_index{value key}



![[notes/images/ruby-map-examples.webp]]


# Sources
Own notes

https://www.theodinproject.com/lessons/ruby-basic-enumerable-methods

https://www.rubyguides.com/2018/10/ruby-map-method/

# Content Lists
If you prefer browsing the contents of this site through a list instead of a graph, you can find content lists here too:

- [All Notes](notes/)

## Knowledge Index
- [The Odin Project](notes/index-list/the-odin-project.md)
- [Open Source Society University](notes/index-list/open-source-society-university.md)
- [Full Stack Open](notes/index-list/fullstack-open.md)
- [Miscellaneous](notes/index-list/miscellaneous.md)
- [Quartz](notes/index-list/quartz.md)


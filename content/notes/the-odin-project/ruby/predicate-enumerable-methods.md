---
title: "predicate-enumerable-methods"
date: "2022-06-04 18:20"
author: "[Doriel Rivalet](https://github.com/DorielRivalet)"
tags:
- enumerable
- enum
- ruby
- the-odin-project
---

# Metadata
2022-06-04 18:20  | predicate-enumerable-methods | [Doriel Rivalet](https://github.com/DorielRivalet)

# Content
a predicate method is indicated by a question mark (`?`) at the end of the method name and returns either `true` or `false`

![[notes/images/ruby-any-all-one.webp]]

`all?` method will return `true` if you call it on an empty array.

**Example**:

```ruby
[].all? { |s| s.size == 1 }

# true
```


**Explanation**:

Since NO elements are `false` then all elements must be `true`.

`any?` works like the inverse of `empty?`. But that won’t work for every situation.

**Because this is asking the question**:

“Are there any TRUTHY elements inside this array?”

If your array includes only non-truthy (`nil`/`false`) values you’ll get `false`, but the array is not really empty.

You can also pass a block to this method:

```ruby
[1,2,3].any? { |n| n > 0 }

# true
```


This will check if `n > 0` is `true` for AT LEAST one element.

(`any?` / `all?` / `none?` / `one?`) also take an argument which works [like grep’s argument](https://www.rubyguides.com/2018/10/grep-method-with-examples/).

**Here’s what I mean**:

```ruby
[:orange, :apple, :coconut].any?(Symbol)

# true

[1,2,3].all?(1..10)

# true
```

This is a nice little shortcut if you want to check for a class, regular expression or a range.


# Sources
Own notes

https://www.theodinproject.com/lessons/ruby-predicate-enumerable-methods

https://www.rubyguides.com/2018/10/any-all-none-one/

a lot of people _think_ that `.any?` checks if an enumerable contains any elements, and `.none?` checks if there are no elements (like `.empty?`). There’s a nasty gotcha lurking in that interpretation.

These don’t check whether elements _exist_, but whether they make the block return a truthy value (or if you don’t pass a block, then whether they _are_ truthy). So frex `[nil, false].any?` is false, and `[nil, false].none?` is true.

arr.any? is same as asking, is any truthy?

arr.none? is same as asking, is any existing?
# Content Lists
If you prefer browsing the contents of this site through a list instead of a graph, you can find content lists here too:

- [All Notes](notes/)

## Knowledge Index
- [The Odin Project](notes/index-list/the-odin-project.md)
- [Open Source Society University](notes/index-list/open-source-society-university.md)
- [Full Stack Open](notes/index-list/fullstack-open.md)
- [Miscellaneous](notes/index-list/miscellaneous.md)
- [Quartz](notes/index-list/quartz.md)


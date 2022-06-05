---
title: "nested-collections"
date: "2022-06-04 18:50"
author: "[Doriel Rivalet](https://github.com/DorielRivalet)"
tags:
- ruby
- the-odin-project
- nesting
- arrays
- hashes
- iteration
---

# Metadata
2022-06-04 18:50  | nested-collections | [Doriel Rivalet](https://github.com/DorielRivalet)

# Content

use #dig to about errors when indexing arrays/hashes

This first example uses the second optional argument for the default value.

```ruby
mutable = Array.new(3, Array.new(2))
#=> [[nil, nil], [nil, nil], [nil, nil]]
mutable[0][0] = 1000
#=> 1000
mutable
#=> [[1000, nil], [1000, nil], [1000, nil]]
```

Changing the value of the first element in the first nested array, causes the first element to change in all three nested arrays! This same behavior will happen with strings, hashes, or any other mutable objects.

Now, let’s take a look at an example that omits the second optional argument and instead passes in the mutable value in a block.

```ruby
immutable = Array.new(3) { Array.new(2) }
#=> [[nil, nil], [nil, nil], [nil, nil]]
immutable[0][0] = 1000
#=> 1000
immutable
#=> [[1000, nil], [nil, nil], [nil, nil]]
```

Changing the value of the first element in the first nested array does not cause the value to change in any other nested array.

if any student scored higher than 80 on everything.

```ruby
test_scores = [[97, 76, 79, 93], [79, 84, 76, 79], [88, 67, 64, 76], [94, 55, 67, 81]]
#=> [[97, 76, 79, 93], [79, 84, 76, 79], [88, 67, 64, 76], [94, 55, 67, 81]]

test_scores.any? do |scores|
  scores.all? { |score| score > 80 }
end
#=> false
```

What do you think will happen if we switch `#any?` and `#all?`? Do you think we will get the same results?

```ruby
test_scores.all? do |scores|
  scores.any? { |score| score > 80 }
end
#=> true
```

The results are different, because now it is determining if **all** of the nested arrays contain **any** number over 80. This returns true, because each of the nested arrays have at least one number over 80.


```ruby
vehicles.filter_map { |name, data| name if data[:year] >= 2020 }
#=> [:caleb, :dave]
```

```#select, #filter, #collect/map, #compact```

```ruby
contacts.each do |person, data|
  #at this level, "person" is Jon Snow or Freddy Mercury and "data" is a hash of
  #key/value pairs to iterate over the "data" hash, we can use the following line:

  data.each do |attribute, value|
    puts "#{attribute}: #{value}"
  end
end
```

```
contacts.each do |person, data|
  #at this level, "person" is Jon Snow or Freddy and "data" is a hash of
  #key/value pairs to iterate over the "data" hash, we can use the following
  #line:

  data.each do |attribute, value|
    #at this level, "attribute" describes the key of :name, :email,
    #:favorite_ice_cream_flavors, or :knows we need to first check and see if
    #the key is :favorite_ice_cream_flavors, if it is, that means the VALUE is
    #an array that we can iterate over to print out each element

    if attribute == :favorite_ice_cream_flavors
      value.each do |flavor|
        # here, each index element in an ice cream flavor string
        puts "#{flavor}"
      end
    end
  end
end
```


Ruby provides a couple of tools to help us comprehend arrays, hashes, and nested mixtures of both.

Assuming your data looks like this (I've added quotes around `GOOG` and `FB`):

```ruby
data = [
  {"id"=>"1", "properties"=>{"name"=>"Google", "stock_symbol"=>"GOOG", "primary_role"=>"company"}},
  {"id"=>"2", "properties"=>{"name"=>"Facebook", "stock_symbol"=>"FB", "primary_role"=>"company"}}
]
```

You can iterate over the array using [`each`](http://ruby-doc.org/core-2.5.1/Array.html#method-i-each), e.g.:

```ruby
data.each do |result|
   puts result["id"]
end
```

Digging into a hash and printing the result can be done in a couple of ways:

```ruby
data.each do |result|
  # method 1
  puts result["properties"]["name"]

  # method 2  
  puts result.dig("properties", "name")
end
```

Method #1 uses the [`hash[key]`](http://ruby-doc.org/core-2.5.1/Hash.html#method-i-5B-5D) syntax, and because the first hash value is another hash, it can be chained to get the result you're after. The drawback of this approach is that if you have a missing `properties` key on one of your results, you'll get an error.

Method #2 uses [`dig`](http://ruby-doc.org/core-2.5.1/Hash.html#method-i-dig), which accepts the nested keys as arguments (in order). It'll dig down into the nested hashes and pull out the value, but if any step is missing, it will return `nil` which can be a bit safer if you're handling data from an external source

## Removing elements from a hash

Your second question is a little more involved. You've got two options:

1.  Remove the `primary_role` keys from the nested hashes, or
2.  Create a new object which contains all the data except the `primary_role` keys.

I'd generally go for the latter, and recommend reading up on immutability and immutable data structures.

However, to achieve [1] you can do an in-place [`delete`](http://ruby-doc.org/core-2.5.1/Hash.html#method-i-delete) of the key:

```ruby
data.each do |company| 
  company["properties"].delete("primary_role")
end
```

## Adding elements to a hash

You assign new hash values simply with [`hash[key] = value`](http://ruby-doc.org/core-2.5.1/Hash.html#method-i-5B-5D-3D), so you can set the industry with something like:

```ruby
data.each do |company| 
  company["properties"]["industry"] = "Advertising/Privacy Invasion"
end
```

which would leave you with something like:

```ruby
[
  {
    "id"=>"1", 
    "properties"=>{
      "name"=>"Google", 
      "stock_symbol"=>"GOOG", 
      "industry"=>"Advertising/Privacy Invasion"
    }
  },
  {
    "id"=>"2", 
    "properties"=>{
      "name"=>"Facebook", 
      "stock_symbol"=>"FB", 
      "industry"=>"Advertising/Privacy Invasion"
    }
  }
]
```


reminder: switch from `if !` to `unless`

# Sources
Own notes

https://www.theodinproject.com/lessons/ruby-nested-collections

https://learn.co/lessons/nested-hash-iteration

https://stackoverflow.com/questions/50529389/manipulating-output-from-an-array-of-nested-hashes-in-ruby


# Content Lists
If you prefer browsing the contents of this site through a list instead of a graph, you can find content lists here too:

- [All Notes](notes/)

## Knowledge Index
- [The Odin Project](notes/index-list/the-odin-project.md)
- [Open Source Society University](notes/index-list/open-source-society-university.md)
- [Full Stack Open](notes/index-list/fullstack-open.md)
- [Miscellaneous](notes/index-list/miscellaneous.md)
- [Quartz](notes/index-list/quartz.md)


---
title: "hashes"
date: "2022-05-31 05:02"
author: "[Doriel Rivalet](https://github.com/DorielRivalet)"
tags:
- hashes
- ruby
- the-odin-project
---

# Metadata
2022-05-31 05:02  | hashes | [Doriel Rivalet](https://github.com/DorielRivalet)| #hashes #ruby #the-odin-project 

# Content
As you can see, the values of a hash can be a number, a string, an array, or even another hash. Keys and values are associated with a special operator called a **hash rocket**: `=>`.

ClassName.new

```ruby
Hash.new
```

```ruby
my_hash = { 
  "a random word" => "ahoy", 
  "Dorothy's math test score" => 94, 
  "an array" => [1, 2, 3],
  "an empty hash within a hash" => {} 
}
```

```ruby
hash = { 9 => "nine", :six => 6 }
```

```ruby
shoes.fetch("hiking", "hiking boots") #=> "hiking boots"
```

hiking is nil, so return the default value, to avoid making the program halt or having a nil value

enumerable is the parent class of hash and array?

```ruby
hash1 = { "a" => 100, "b" => 200 }
hash2 = { "b" => 254, "c" => 300 }
hash1.merge(hash2)      #=> { "a" => 100, "b" => 254, "c" => 300 }
```

:symbols are used instead of "strings" for efficiency purposes, more performant

```ruby
# 'Rocket' syntax 
american_cars = { 
  :chevrolet => "Corvette", 
  :ford => "Mustang", 
  :dodge => "Ram" 
}
# 'Symbols' syntax
japanese_cars = { 
  honda: "Accord", 
  toyota: "Corolla", 
  nissan: "Altima" 
}
```

```ruby
def greeting(name, options = {}) 
	if options.empty?
		puts "Hi, my name is #{name}" 
	else 
			puts "Hi, my name is #{name} and I'm #{options[:age]}" + " years old and I live in #{options[:city]}."
	end 
end 

greeting("Bob") 
greeting("Bob", {age: 62, city: "New York City"})
```

the curly braces, `{ }`, are not required when a hash is the last argument,

-   Does this data need to be associated with a specific label? If yes, use a hash. If the data doesn't have a natural label, then typically an array will work fine.
    
-   Does order matter? If yes, then use an array. As of Ruby 1.9, hashes also maintain order, but usually ordered items are stored in an array.
    
-   Do I need a "stack" or a "queue" structure? Arrays are good at mimicking simple "first-in-first-out" queues, or "last-in-first-out" stacks.

FIFO Means first in first out

LIFO is last in first out

keys can be a lot of different data types, using `=>` when we deviate from using symbols as keys.

```name_and_age.key?("Steve")```

hash.to_a

object.methodName

`name_and_age.keys.each { |k| puts k }`.

hash

hash.keys returns an array

we can use  the each method on arrays

hash.keys.each {|key| puts key|}

key value pairs



# Sources
https://www.theodinproject.com/lessons/ruby-hashes

https://launchschool.com/books/ruby/read/hashes

# Content Lists
If you prefer browsing the contents of this site through a list instead of a graph, you can find content lists here too:

- [All Notes](notes/)

## Knowledge Index
- [The Odin Project](notes/index-list/the-odin-project.md)
- [Open Source Society University](notes/index-list/open-source-society-university.md)
- [Full Stack Open](notes/index-list/fullstack-open.md)
- [Miscellaneous](notes/index-list/miscellaneous.md)
- [Quartz](notes/index-list/quartz.md)


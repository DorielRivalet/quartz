---
title: "files and serialization"
date: "2022-06-21 21:56"
author: "[Doriel Rivalet](https://github.com/DorielRivalet)"
tags:
- the-oodin-project
- input-output
- io
---

# Metadata
2022-06-21 21:56  | files and serialization | [Doriel Rivalet](https://github.com/DorielRivalet)

# Content

Unix-like systems treat all external devices as files. We can see these under the `/dev` directory.

```
$ tree /dev 
/dev 
├── disk0 
├── fd    
│ 	├── 0   
│ 	├── 1 
│   ├── 2 
│	└── 3 [error opening dir] 
├── null 
├── stderr -> fd/2 
├── stdin -> fd/0 
├── stdout -> fd/1 
├── tty 
└── zero
```
The operating system provides three streams by default. They are:

-   Standard input / stdin (`/dev/fd/0`)
-   Standard output / stdout (`/dev/fd/1`)
-   Standard error /  stderr (`/dev/fd/2`)

0, 1 and 2 are the file descriptors

`$stdout.puts 'Hello World'

`$stdin.gets`

`$stdin` is read-only while `$stdout` and `$stderr` are write-only.


```ruby
[1] pry(main)> io = IO.new(1) 
=> #<IO:fd 1> 
[2] pry(main)> io.puts 'hello world' 
hello world 
=> nil
```
```ruby
[1] pry(main)> IO.sysopen '/Users/joelquenneville/Desktop/lorem.txt' 
=> 8 
[2] pry(main)> lorem = IO.new(8) 
=> #<IO:fd 8> 
[3] pry(main)> lorem.gets 
=> "Lorem ipsum\n"
```
position of cursor: lorem.pos

end of file? lorem.eof?

to the beginning: lorem.rewind

streams do not get loaded into memory. Instead, only the lines being operated on are loaded.

Javascript Object Notation

YAML Ain’t Markup Language

XML

```ruby
require 'json'

class Person
  ...
  def to_json
    JSON.dump ({
      :name => @name,
      :age => @age,
      :gender => @gender
    })
  end

  def self.from_json(string)
    data = JSON.load string
    self.new(data['name'], data['age'], data['gender'])
  end
```

<<<<<<< HEAD
replace json with yaml to use yaml. or messagepack

```ruby
class People
  include BasicSerializable

  attr_accessor :persons

  def initialize
    @persons = []
  end

  def serialize
    obj = @persons.map do |person|
      person.serialize
    end

    @@serializer.dump obj
  end

  def unserialize(string)
    obj = @@serializer.parse string
    @persons = []
    obj.each do |person_string|
      person = Person.new "", 0, ""
      person.unserialize(person_string)
      @persons << person
    end
  end

  def <<(person)
    @persons << person
  end
end
```


```ruby
somefile = File.open("sample.txt", "w")
somefile.puts "Hello file!"
somefile.close   
```

Using "w" mode on an existing file will _erase the contents of that file_. If you want to _append_ to an existing file, use "a" as the second argument.

```ruby
require "open-uri"

remote_base_url = "http://en.wikipedia.org/wiki"
remote_page_name = "Ada_Lovelace"
remote_full_url = remote_base_url + "/" + remote_page_name

remote_data = open(remote_full_url).read
my_local_file = open("my-downloaded-page.html", "w") 

my_local_file.write(remote_data)
my_local_file.close
```

```
File.open("sample.txt", "w"){ |somefile| somefile.puts "Hello file!"}
```

The file handle is automatically closed at the end of the block, so no need to call the close method. This is handy in cases when you only need to do all read or write to a file all in one go.


=======
replace json with yaml to use yaml
>>>>>>> 2663bc7f5aa6c055a667fb9ad552e1a15900bb51



# Sources
Own notes

https://www.theodinproject.com/lessons/ruby-files-and-serialization

https://thoughtbot.com/blog/io-in-ruby

<<<<<<< HEAD
http://ruby.bastardsbook.com/chapters/io/

=======
>>>>>>> 2663bc7f5aa6c055a667fb9ad552e1a15900bb51
# Content Lists
If you prefer browsing the contents of this site through a list instead of a graph, you can find content lists here too:

- [All Notes](notes/)

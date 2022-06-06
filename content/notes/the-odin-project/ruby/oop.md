---
title: "oop"
date: "2022-06-06 01:22"
author: "[Doriel Rivalet](https://github.com/DorielRivalet)"
tags:
- object-oriented-programming
- the-odin-project
- ruby
- mixins
- inheritance
- instance-variables
- class-variables
- global-variables
- local-variables
- scope
- methods
- attributes
---

# Metadata
2022-06-06 01:22  | oop | [Doriel Rivalet](https://github.com/DorielRivalet)

# Content
lambdas are nameless methods/functions

another name for properties are attributes

classes have properties and objects have attributes?

the \@ in Ruby classes is the same as ```private``` in Java classes

In Ruby, we use `@` before a variable to signify that it’s an _instance variable_. This means that the variable is attached to the _instance_ of the class.

```ruby
class Person

	def initialize(name)
	
	@name = name
	
	end

end
  

matz = Person.new("Yukihiro")
```

Another important aspect of Ruby classes is _scope_. The scope of a variable is the context in which it’s visible to the program.

When dealing with classes, you can have variables that are available everywhere (_global variables_), ones that are only available inside certain methods (_local variables_), others that are members of a certain class (_class variables_), and variables that are only available to particular instances of a class (_instance variables_).

global, local, class, instance

what is `$`, `@`, or `@@` prepended to a variable name? This helps mark them as global, instance, and class variables (respectively).


```ruby
class Computer

$manufacturer = "Mango Computer, Inc."

@@files = {hello: "Hello, world!"}

def initialize(username, password)

@username = username

@password = password

end

def current_user

@username

end

def self.display_files

@@files

end

end

  

# Make a new Computer instance:

hal = Computer.new("Dave", 12345)

  

puts "Current user: #{hal.current_user}"

# @username belongs to the hal instance.

  

puts "Manufacturer: #{$manufacturer}"

# $manufacturer is global! We can get it directly.

  

puts "Files: #{Computer.display_files}"

# @@files belongs to the Computer class.
```

```ruby
#Current user: Dave
#Manufacturer: Mango Computer, Inc.
#Files: {:hello=>"Hello, world!"}
```


_Global variables_ can be declared in two ways. The first is one that’s already familiar to you: you just define the variable outside of any method or class, and voilà! It’s global. If you want to make a variable global from inside a method or class, just start it with a `$`, like so: `$matz`.

rule of thumb: modularise variables, limit their scope

limit the scope of everything

sandboxing

we can use a class variable to keep track of the number of instances of that class we’ve created. Let’s do that now!

```ruby
class Person

	# Set your class variable to 0 on line 3
	
	@@people_count = 0
	
	def initialize(name)
	
		@name = name
		
		# Increment your class variable on line 8
		
		@@people_count += 1
	
	end
	
	def self.number_of_instances
	
		# Return your class variable on line 13
		
		@@people_count
	
	end

end

  

matz = Person.new("Yukihiro")

dhh = Person.new("David")

  

puts "Number of Person instances: #{Person.number_of_instances}"
```

```ruby
class SuperBadError < ApplicationError #same as saying SuperBadError inherits FROM ApplicationError, so superbaderror is a child class or subclass of applicationerror, which is the superclass or parent class
class DerivedClass < BaseClass  
  # Some stuff!  
end
```

you can override/overwrite methods/attributes you inherit from

```ruby
class DerivedClass < Base 
	def some_method 
		super(optional args) # Some stuff 
		end 
	end 
end
```

When you call `super` from inside a method, that tells Ruby to look in the superclass of the current class and find a method with the same name as the one from which `super` is called. If it finds it, Ruby will use the superclass’ version of the method.

```ruby
class Creature

	def initialize(name)
	
		@name = name
	
	end
	
	def fight
	
		return "Punch to the chops!"
	
	end

end

  

# Add your code below!

class Dragon < Creature

	def fight
	
		puts "Instead of breathing fire..."
		
		super

	end

end
```

```
Instead of breathing fire...
Punch to the chops!
```

Any given Ruby class can have only one superclass. Some languages allow a class to have more than one parent, which is a model called **multiple inheritance**. This can get really ugly really fast, which is why Ruby disallows it.

However, there are instances where you want to incorporate data or behavior from several classes into a single class, and Ruby allows this through the use of _mixins_. We’ll learn about mixins in a later lesson! For now, we’ll demonstrate what happens if you try to do multiple inheritance in Ruby.

```ruby
# class Monkey end on just one line: `class Monkey; end`.
```

```ruby
class Message

	@@messages_sent = 0
	
	def initialize(from,to)
	
		@from = from
		
		@to = to
		
		@@messages_sent += 1
	
	end

end


class Email < Message

	def initialize(from,to)
	
		super
	
	end

end

my_message = Message.new("a","b")
```

```ruby
class Computer

	@@users = {}

	def Computer.get_users()
	
		@@users
	
	end

	def initialize(username,password)
	
		@username, @password = username, password
		
		@files = {}
		
		@@users[username] = password
	
	end

	def create(filename)
	
		time = Time.now
		
		@files[filename] = time
		
		puts "new file created, #{filename} #{time} #{self.username}"
		
	end
	
end

my_computer = Computer.new("a","b")
```

Ruby allows you to explicitly make some methods `public` and others `private`. Public methods allow for an **interface** with the rest of the program; they say, “Hey! Ask me if you need to know something about my class or its instances.”

`private` methods are just that: they’re private to the object where they are defined. This means you can only call these methods from other code inside the object. Another way to say this is that the method cannot be called with an _explicit receiver_. You’ve been using receivers all along—these are the objects on which methods are called! Whenever you call `object.method`, `object` is the receiver of the `method`.

In order to access private information, we have to create public methods that know how to get it. This separates the private _implementation_ from the public _interface_, and we’ll go over this in more detail in the next two exercises.

```ruby
class Dog

def initialize(name, breed)

@name = name

@breed = breed

end

public def bark

puts "Woof!"

end

  

private def id()

@id_number = 12345

end

end
```

If we want to both read and write a particular variable, there’s an even shorter shortcut than using `attr_reader` and `attr_writer`. We can use `attr_accessor` to make a variable readable _and_ writeable in one fell swoop.

```ruby
class Person

attr_reader :name

attr_accessor :job

def initialize(name, job)

@name = name

@job = job

end

end
```

```ruby
module MyLibrary

FAVE_BOOK = "The Hobbit"

end
```


One of the main purposes of modules is to separate methods and constants into named spaces. This is called (conveniently enough) **namespacing**, and it’s how Ruby doesn’t confuse `Math::PI` and `Circle::PI`.

```c++
using namespace std
//So when we run a program to print something, “using namespace std” says **if you find something that is not declared in the current scope go and check std**. using namespace std; are used. It is because computer needs to know the code for the cout, cin functionalities and it needs to know which namespace they are defined.
std::cout
```

See that double colon we just used? That’s called the **scope resolution operator**, which is a fancy way of saying it tells Ruby _where_ you’re looking for a specific bit of code. If we say `Math::PI`, Ruby knows to look inside the `Math` module to get that `PI`, not any other `PI` (such as the one we created in `Circle`).

```ruby
require 'date'

  

puts Date.today
```

We can do more than just `require` a module, however. We can also `include` it!

Any class that `include`s a certain module can use those module’s methods!

A nice effect of this is that you no longer have to prepend your constants and methods with the module name. Since everything has been pulled in, you can simply write `PI` instead of `Math::PI`.

```ruby
class Angle

	include Math
	
	attr_accessor :radians
	
	def initialize(radians)
	
		@radians = radians
	
	end
	
	def cosine
	
		cos(@radians)
	
	end

end

acute = Angle.new(1)

acute.cosine
```

When a module is used to mix additional behavior and information into a class, it’s called a **mixin**. Mixins allow us to customize a class without having to rewrite code!


```ruby
module Action

def jump

@distance = rand(4) + 2

puts "I jumped forward #{@distance} feet!"

end

end

  

class Rabbit

include Action

attr_reader :name

def initialize(name)

@name = name

end

end

  

class Cricket

include Action

attr_reader :name

def initialize(name)

@name = name

end

end

  

peter = Rabbit.new("Peter")

jiminy = Cricket.new("Jiminy")

  

peter.jump

jiminy.jump

#I jumped forward 4 feet!
#I jumped forward 3 feet!

```

```ruby
# Create your module here!

module MartialArts

def swordsman

puts "I'm a swordsman."

end

end

  
  

class Ninja

include MartialArts

def initialize(clan)

@clan = clan

end

end

  

class Samurai

include MartialArts

def initialize(shogun)

@shogun = shogun

end

end
```

Whereas `include` mixes a module’s methods in at the instance level (allowing instances of a particular class to use the methods), the `extend` keyword mixes a module’s methods at the _class_ level. This means that _class itself_ can use the methods, as opposed to _instances_ of the class.

You probably also noticed we used underscores in our `1_000_000` (one million). Ruby allows this, and it makes it easier to read big numbers! Cool, no?

```ruby
class Account

attr_reader :name

attr_reader :balance

def initialize(name, balance=100)

@name=name

@balance=balance

end

private def pin

@pin = 1234

end

private def pin_error

"Access denied: incorrect PIN."

end

public def display_balance(pin_number)

if pin_number == pin

puts "Balance: $#{@balance}."

else pin_error()

end

end

  

public def withdraw(pin_number,amount)

if pin_number == @pin

balance -= amount

puts "Withdrew #{amount}. New balance: $#{@balance}."

else

puts pin_error()

end

end

end

  

checking_account = Account.new("a",1000)
```

**Encapsulation** is hiding pieces of functionality and making it unavailable to the rest of the code base. It is a form of data protection, so that data cannot be manipulated or changed without obvious intention. It is what defines the boundaries in your application and allows your code to achieve new levels of complexity. Ruby, like many other OO languages, accomplishes this task by creating objects, and exposing interfaces (i.e., methods) to interact with those objects.

**Polymorphism** is the ability for different types of data to respond to a common interface. For instance, if we have a method that expects argument objects that have a `move` method, we can pass it any type of argument, provided it has a compatible `move` method. The object might represent a human, a cat, a jellyfish, or, conceivably, even a car or train. That is, it lets objects of different types respond to the same method invocation.


https://launchschool.com/books/oo_ruby/read/the_object_model

## [Classes Define Objects](https://launchschool.com/books/oo_ruby/read/the_object_model#classesdefineobjects)

modules are another way to achieve polymorphism in Ruby. A **module** is a collection of behaviors that is usable in other classes via **mixins**. A module is "mixed in" to a class using the `include` method invocation. Let's say we wanted our `GoodDog` class to have a `speak` method but we have other classes that we want to use a speak method with too. Here's how we'd do it.

```ruby
module Speak
  def speak(sound)
    puts sound
  end
end

class GoodDog
  include Speak
end

class HumanBeing
  include Speak
end

sparky = GoodDog.new
sparky.speak("Arf!")        # => Arf!
bob = HumanBeing.new
bob.speak("Hello!")         # => Hello!
```

We can use the `ancestors` method on any class to find out the method lookup chain.


To disambiguate from creating a local variable, we need to use `self.name=` to let Ruby know that we're calling a method. So our `change_info` code should be updated to this:

This tells Ruby that we're calling a setter method, not creating a local variable. To be consistent, we could also adopt this syntax for the getter methods as well, though it is not required.

```ruby
def info
  "#{self.name} weighs #{self.weight} and is #{self.height} tall."
end
```

Note that prefixing `self.` is not restricted to just the accessor methods; you can use it with any instance method. For example, the `info` method is not a method given to us by `attr_accessor`, but we can still call it using `self.info`:


```ruby
class GoodDog
  # ... rest of code omitted for brevity
  def some_method
    self.info
  end
end
```

While this works, the general rule from the [Ruby style guide](https://rubystyle.guide/#no-self-unless-required) is to "Avoid self where not required."

```ruby
# bad 
def ready? 
	if self.last_reviewed_at > self.last_updated_at
		self.worker.update(self.content, self.options) 
		self.status = :in_progress 
	end 
	self.status == :verified 
end 

# good 
def ready? 
	if last_reviewed_at > last_updated_at 
		worker.update(content, options) 
		self.status = :in_progress 
	end 
	status == :verified 
end
```

```ruby
class Person
  def initialize(age)
    @age = age
  end

  def age
    @age
  end

  def age_difference_with(other_person)
    (self.age - other_person.age).abs
  end

  protected :age
end
```

Writing `@age` directly accesses the instance variable `@age`. Writing `self.age` tells the object to send itself the message `age`, which will usually return the instance variable `@age` — but could do any number of other things depending on how the `age` method is implemented in a given subclass. For example, you might have a MiddleAgedSocialite class that always reports its age 10 years younger than it actually is. Or more practically, a PersistentPerson class might lazily read that data from a persistent store, cache all its persistent data in a hash.

---

When you find that you want the same method to be run on a bunch of different objects without having to make a bunch of different `if/else` or `case` statements, you should start thinking about using a class.

```ruby
class Viking
    @@starting_health
    def initialize(name, age, strength)
        @health = @@starting_health
        # ...other stuff
    end
end
```

There are two good times to use class methods: when you're building new instances of a class that have a bunch of known or "preset" features, and when you have some sort of utility method that should be identical across all instances and won't need to directly access instance variables.

The first case is called a **factory method**, and is designed to save you from having to keep passing a bunch of parameters manually to your `#initialize` method:

```ruby
class Viking
    def initialize(name, health, age, strength)
        #... set variables
    end
    def self.create_warrior(name)
        age = rand * 20 + 15   # remember, rand gives a random 0 to 1
        health = [age * 5, 120].min
        strength = [age / 2, 10].min
        Viking.new(name, health, age, strength)  # returned
    end
end

#> sten = Viking.create_warrior("Sten")
#=> #<Viking:0x007ffc05a79848 @age=21.388120526202737, 
```

If a hash (good data storage) and a module (good methods) had a love child, would it be a class (object with methods)?

```ruby
1.class.superclass.superclass.superclass.superclass
#=> BasicObject
```

**Scope** is the formal term that represents when you can access a variable or method and when you can't. It's nothing explicit in the code (you're never calling a method named `scope` or anything like that); it's just a concept. If your variable is "in scope" then it's available for use, otherwise it's "out of scope".

Since we don't want `#take_damage` to be visible to anyone on the command line but we DO want it to be visible to the methods inside other instances of `Viking`, we call that **`protected`**. `protected` provides most of the privacy of `private` but lets the methods inside other instances of the same class or its descendents also access it:

In Ruby, a protected method (or protected message handler) **can only respond to a message with an implicit/explicit receiver (object) of the same family**. It also cannot respond to a message sent from outside of the protected message handler context.

Both protected and private methods cannot be called from the outside of the defining class. **Protected methods are accessible from the subclass and private methods are not**. Private methods of the defining class can be invoked by any instance of that class. Public access is the default one.

`protected` methods can be called by any instance of the defining class or its subclasses.

`private` methods can be called only from within the calling object. You cannot access another instance's private methods directly.

```attr_accessor :name, :location```

```ruby
class Movie  

	attr_accessor :title, :showtime, :cinema  
	@@all = []  

	def initialize(title, showtime)  
	    @title = title  
	    @showtime = showtime  
	    @@all << self  
	end
end
```

```ruby
def add_movie(movie)  
	@movies << movie  
	movie.cinema = self  
end
```


```ruby
#exception handling
a = 10
b = "42"

begin
   a + b
rescue
   puts "Could not add variables a (#{a.class}) and b (#{b.class})"
else
   puts "a + b is #{a + b}"
ensure
	puts "this will print regardless"
end
```

the ```ensure``` branch will execute whether an error/exception was rescued or not. Here, we've decided to sleep for 3 seconds no matter the outcome of the open method. ([ruby-doc definition](http://ruby-doc.org/docs/keywords/1.9/Object.html#method-i-ensure "Class: Object"))

retry retries the begin block.

```ruby
require 'open-uri'
remote_base_url = "http://en.wikipedia.org/wiki"

[1900, 1910, 'xj3490', 2000].each do |yr|
 
 retries = 3
 
 begin
   url = "#{remote_base_url}/#{yr}"
   puts "Getting page #{url}"
   rpage = open(url)
 rescue StandardError=>e
   puts "\tError: #{e}"
   if retries > 0
       puts "\tTrying #{retries} more times"
       retries -= 1
       sleep 1
       retry
   else
       puts "\t\tCan't get #{yr}, so moving on"
   end    
 else
   puts "\tGot page for #{yr}"
 ensure   
   puts "Ensure branch; sleeping"
   sleep 1

 end
end
```


```ruby
**Exception**
    NoMemoryError
    ScriptError
        LoadError
        NotImplementedError
        SyntaxError
    SignalException
        Interrupt
    **StandardError**
        ArgumentError
        IOError
            EOFError
        IndexError
            StopIteration
        LocalJumpError
        NameError
            NoMethodError
        RangeError
            FloatDomainError
        RegexpError
        RuntimeError
        SecurityError
        SystemCallError
        SystemStackError
        ThreadError
        TypeError
        ZeroDivisionError
    SystemExit
    fatal
```

```ruby
class Lamp
  def self.about_me()
    return("We brighten up people's lives")
  end
end

#OR

class Lamp
  def Lamp.about_me()
    return("We brighten up people's lives")
  end
end

#The about_me() method can be called directly on the Lamp class:

Lamp.about_me()
```

```ruby
class Person
  def initialize(age)
    @age = age
  end

  def age=(new_age)
    @age = new_age
  end

  def age()
    return(@age)
  end
end

p = Person.new(24)
p.age  # returns 24
p.age=(42)  # update the @age instance variable
p.age  # now returns 42
```

Modules cannot be used to create objects

Array.ancestors()

Array.ancestors() returns the following array: \[Array, Enumerable, Object, Kernel, BasicObject\]. In this list, Array, Object, and BasicObject are classes. Array inherits from Object and Object inherits from BasicObject. Enumerable and Kernel are modules. The Enumerable module is included in the Array class and the Kernel module is mixed-in to the Object class (mixed-in is another way of saying that a module is included in a class).

# Sources
Own notes

https://www.theodinproject.com/lessons/ruby-object-oriented-programming

https://www.codecademy.com/courses/learn-ruby/lessons/object-oriented-programming-i/exercises/scope-it-out

https://launchschool.com/books/oo_ruby/read/the_object_model

https://launchschool.com/books/oo_ruby/read/classes_and_objects_part1#statesandbehaviors

https://rubystyle.guide/#no-self-unless-required

https://stackoverflow.com/questions/1693243/instance-variable-self-vs

https://www.eriktrautman.com/posts/ruby-explained-classes

# Content Lists
If you prefer browsing the contents of this site through a list instead of a graph, you can find content lists here too:

- [All Notes](notes/)

## Knowledge Index
- [The Odin Project](notes/index-list/the-odin-project.md)
- [Open Source Society University](notes/index-list/open-source-society-university.md)
- [Full Stack Open](notes/index-list/fullstack-open.md)
- [Miscellaneous](notes/index-list/miscellaneous.md)
- [Quartz](notes/index-list/quartz.md)


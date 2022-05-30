# Metadata
2022-05-25 17:12

202205251705

# Content
Domain Specific Languages (DSL's): Rails, Rspec

When you start learning programming in Ruby you’ll need three tools: A text editor, a terminal, and a Ruby runtime.

.rb is ruby file

A terminal is an application that doesn’t do much more but provide a window to run another program, called a “shell”. A shell is a text-based program, so it does not have a window, and thus needs the terminal to be run on your graphical user interface.

tab for autocomplete, double tab to see choices if multiple

tools:
terminal -> shell: for commands
ruby runtime
text editor: vsc (or others)
the ruby runtime can be run in the shell
eg with ruby fileName.rb

Extrapolation for other languages:

go run .
luvit filename.lua
java --enable-preview fileName
etc

sdk = software development kit

## Workflow
-   Write some code in your text editor.
-   Save the code to a file in a particular directory. The filename should end with `.rb`.
-   Open your terminal.
-   Navigate to that directory using `cd`.
-   Execute the file using `ruby`.
-   Switch back and forth between the text editor and terminal, so you can make small changes in your code, and then run it through `ruby` to see what it does.

In your shell you can use the `cursor up` key to go through your last used commands: you don’t have to type `ruby hello.rb` again. Just hit `cursor up` and then enter to run it again.

often `$` is used to indicate that this is a system shell prompt, while `>` is used by IRB to indicate that this is an interactive Ruby shell.

snake_case: define or initialize a method, variable, or file"

 In Ruby, constants are denoted with all uppercase letters.
 
 namespace: variables environment
 
 The libraries that the system publishes are called "gems".
  
  npm install
  gem install
  sudo apt install ruby
  
  puts is print
  
  ctrl d to close
  
  irb -r ./your_file.rb
  
  ```bash
sudo apt update
sudo apt upgrade
```

```bash
sudo apt install gcc make libssl-dev libreadline-dev zlib1g-dev libsqlite3-dev
```

`rbenv`, which makes it easy to install and manage Ruby versions.


rbenv global 3.0.3

ruby -v

# Sources
https://launchschool.com/books/ruby/read/introduction

http://ruby-for-beginners.rubymonstas.org/your_tools.html

https://www.theodinproject.com/lessons/ruby-installing-ruby

---
title: "overview of the layers of abstraction"
date: "2022-05-30 02:28"
author: "[Doriel Rivalet](https://github.com/DorielRivalet)"
tags:
- abstraction
---


# Metadata
2022-05-27 03:12

overview of the layers of abstraction

# Content

"thousands of layers" might be a bit of an exaggeration. But that does raise an interesting question. How many layers are there? Here's a (_very_) rough draft. I skip over a lot of complexity and options for simplicity - to make the point and to keep this reasonably readable. I may also have missed a layer or two (**edit** or more - see the replies for lots of great details!) - this is off the top of my head and it's been a long day. Still, enjoy, and maybe some other people can add on and round this out.

-   At the bottom, it's electrons in a circuit.
    
-   The circuits are arranged into patterns that happen to execute very simple boolean logic if you watch the inputs and outputs at the right time.
    
-   Those simple boolean circuits are built into more complex, integrated circuits that happen to execute more complex mathematical operations - boolean algebra and addition, subtraction, etc.
    
-   Those integrated circuits are arranged into modules, grouping them together into useful processors and sub processors.
    
-   Those modules are arranged and connected together via a bus, with some inputs and outputs, long-term storage and a clock - now you've got the hardware of a computer!
    

Now things get interesting - we switch to software layers.

-   This machine is basically a complex calculator. It does nothing unless you tell it to do something via a list of instructions - inputs to put in to various modules and what to do with the outputs.
    
-   These instructions are called the Machine Codes - they're particular to this specific machine - they correspond to the specific hardware after all.
    
-   They're very low level instructions - usually things like "add 2 and 5", etc.
    

Setting aside how those instructions get written for the moment -

-   On boot-up one of the module has a set of instructions to run - they're basically hardwired (Flash ROM)
    
-   Among those instructions are various tests to see what is plugged in (modular hardware!) and if it's functioning properly.
    
-   One of the last things that boot ROM does is look for another program to launch - the Operating System.
    
-   The OS takes over and starts running things.
    
-   The OS provides more complex instructions and a whole new set of abstractions - files, folders, ways to talk to all the hardware that is plugged in, ways to start other programs running, handle their termination, etc.
    
-   Those programs are the applications that we run on computers all the time - games, web browsers, email, all the services the OS runs in the background, etc.
    
-   Web browsers are particularly interesting - they provide yet another layer of abstraction.
    
-   More code can be retrieved from another computer and run within the web browser - HTML to display the page itself, and interpreted languages like Javascript, which make calls to instructions the Web Browser provides.
    
-   How the code is retrieved from another computer is also interesting - network communications go through a stack of abstractions all the way down to the hardware level. Check out [the TCP/IP stack](https://www.google.com/search?q=tcp+ip+stack&oq=tcp+ip+stack&aqs=chrome.0.57j0l3j62.2073j0&sourceid=chrome&ie=UTF-8) some time.
    

Backing up - how does that software get written?

-   One could write the machine code directly - a series of 1's and 0's arranged in a file that the OS can load and run.
    
-   But that's wildly tedious and prone to error - there's a lot to do just to get the program to do anything useful and leave the computer in a state that can continue to process.
    
-   So people invented languages - first Assembly Language, which is a straight 1:1 mapping to something more human readable than the 1's and 0's.
    
-   Then more complex languages that directly express more complex operations than the machine code does - abstract constructs like functions and loops.
    
-   Assembly is converted into machine code by an Assembler - a program that does the task of substituting the machine codes for each of the assembly instructions.
    
-   More complex languages are compiled - converted from the more abstract language to a set of machine instructions.
    
-   Another option is interpreted languages, which are basically compiled at run time - each line converted as it's needed.
    
-   One more thing people can do is write Libraries of useful functions - a layer that wraps up the lower-level instructions into a new abstraction that provides a more useful, condensed set of alternate, more complex instructions.
    
-   These libraries are chunks of machine code that you can add to your program so you don't have to write them yourself. Open GL is one such library - it provides useful graphics abstractions that let you think in terms of polygons instead of moving numbers into screen memory space and the like.
    

So, adding it all up, a program you write will pull in libraries, usually a layer or two of them. Those libraries and some of your code will call through to OS instructions. Those OS instructions are mapped to lower-level instructions (libraries within the OS - it's not a single layer... probably has more than a few layers of its own). Eventually it all gets boiled down into assembly/machine code. That code then runs in the hardware - within a module, on an integrated circuit. And "runs" means putting the specified 1's and 0's where they should be when they should be there. Those 1's and 0's are electrical switches - 1 for on, 0 for off. They're fed into the integrated circuits which are themselves composed of lots of lower-level boolean logic gates. Those logic gates are composed of simple transistors.

All together, call it ... maybe 4 layers before you hit the OS, then another... say 3? 4? 5? before you hit machine code. Then it's modules, integrated chips, logic gates and transistors. Another 4 layers of abstraction. Toss in a couple more for good measure (I'm sure there are some additional physical abstraction layers in there - EEPROMS, and the like), my back-of-the-envelope math puts us in the ballpark of 15... maybe 20 layers from your compiled software to the transistors. Depending on what you're doing, of course.


# Sources

https://www.reddit.com/r/learnprogramming/comments/1gbe4j/comment/caimx99/?utm_source=share&utm_medium=web2x&context=3
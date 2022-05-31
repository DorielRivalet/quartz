---
title: "computer"
date: "2022-05-31 05:09"
author: "[Doriel Rivalet](https://github.com/DorielRivalet)"
tags:
- computer-science
- programming
---

# Metadata
2022-05-31 05:09  | computer | [Doriel Rivalet](https://github.com/DorielRivalet)| #computer-science #programming 

# Content
### Fundamentals of a Computer

A computer is a machine which has the ability to

-   Read and write from a memory which can be addressed
-   Perform comparisons on the state of the memory, and perform an operation as a result of that. These operations include rewriting memory.
-   Start functions based on content written in the memory. We call such content "programs + data", and the act of writing them **programming**.

A very notable example of this is the most basic concept of computing, a [Turing machine](https://en.wikipedia.org/wiki/Turing_machine "wikipedia:Turing machine"), where the machine will read from one infinite line of code and instruction set in order to complete a function.

### Redstone

Redstone computers work by mimicking the architecture of a real computer. The mechanics of redstone and the items derived from it allow for the player to construct some simple constructs known as "gates" that mirror the real life function of similar real-life electronics. By combining them in certain ways, one can make something more advanced, including the various parts of a computer.

As you may know from school, electrical charge moves from an area of high concentration, to an area of low concentration. For this reason, using a battery to form a circuit is what allows things like light bulbs in your house to work; the electrons flow out from the negative end, through the bulb, exciting the filament, which produces photons and heat, then continue toward the positive side of the battery. With redstone however, a circuit is not required, because the power simply flowing to the block it's activating is all that's required (and all that's really convenient due to the nature of the voxel-based game). By using it and things such as redstone torches, repeaters, and comparitors, it's possible to make things known as "gates". Gates take an input, which is True if there's power, and False if there isn't power, and give an output based on simple rules. For example, the simplest gates to make are known as the "identity" and "negation" gates, or the "A" and "NOT" gates. The A gate is simply the redstones that transfers the power, or the use of a repeater, which pumps out a full-power signal when a signal is input. The Not gate is achievable by running a signal onto the top of a block that has a redstone torch on the side. It outputs whatever the input is not, thus the name. More advanced gates use 2 or sometimes 3 inputs, such as the "OR" gate, which outputs a signal when either input is True, and the "AND" gate, which outputs a signal only when BOTH inputs are True.

More advanced gates such as NAND, which means NOT AND- a fancy way to say the opposite output an AND gate gives, and NOR, which means NOT OR, can allow for you to process the information you send more complexly, or even store the information. In fact, NAND latch based memory, also known as Flip-Flops, are used for data storage in SSDs.

By knowing how computer hardware works, and by knowing how one can build different kinds of redstone gates, one can figure out how to combine them in order to replicate the functions of a computer. If you're interested in trying for yourself, I'm sure you can look around for something instructing to build a simple processing device known as an ALU (Arithmetic Logic Unit), which is basically the brain of a calculator. You would learn how to build something with the sole purpose of taking two sets of inputs, applying a specific function, and outputting a number based on it. After that, you could attempt to build a computer meant to carry out other tasks, such as word processing, or even simulating a game.

All in all, it's just a case of people who know how the parts of a computer work, and who know how to make redstone do what they want it to do. As a result, they are able to design computers out of blocks and dust and sticks. And it's really amazing.

# Sources
https://minecraft.fandom.com/wiki/Tutorials/Redstone_computers

https://www.reddit.com/r/Minecraft/comments/2fj27w/comment/ck9qf4y/?utm_source=share&utm_medium=web2x&context=3

# Content Lists
If you prefer browsing the contents of this site through a list instead of a graph, you can find content lists here too:

- [All Notes](notes/)

## Knowledge Index
- [The Odin Project](notes/index-list/the-odin-project.md)
- [Open Source Society University](notes/index-list/open-source-society-university.md)
- [Full Stack Open](notes/index-list/fullstack-open.md)
- [Miscellaneous](notes/index-list/miscellaneous.md)
- [Quartz](notes/index-list/quartz.md)


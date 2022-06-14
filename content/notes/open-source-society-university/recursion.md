---
title: "recursion"
date: "2022-06-14 20:08"
author: "[Doriel Rivalet](https://github.com/DorielRivalet)"
tags:
- recursion
- data structures
- dictionaries
- sets
- arrays
- call stack
- stack overflow
---

# Metadata
2022-06-14 20:08  | recursion | [Doriel Rivalet](https://github.com/DorielRivalet)

# Content
1.  But Yea another way that can help by knowing when to use sets or arrays, arrays that have non numerical keys are literally called dictionaries in certain other langs. Dicts are like sets. So yes a dictionary could be represented in a ... dictionary data structure
    
    ```
    dictionary = {
     ["fight"] = {
        definitions = ["An altercation between two parties", "a conflict between entities"],
      references = ["brawl","quarrel"]
      }
    }
    
    print(dictionary.fight.definitions[1]) -- An altercation ...
    print("See also: "..dictionary.fight.references[2] -- See also: quarrel
    ```
    
2.  _[_7:31 PM_]_
    
    Self references would create recursion because u go back and again over and over
    
3.  _[_7:32 PM_]_
    
    Except computers can go back over and over and that is counted in something called a call stack, if the stack overflows it's gg and it errors.
    
4.  _[_7:34 PM_]_
    
    Recursion in reading dictionary irl: u read fight references, it references fight, so u read fight again, and it references fight...
    
5.  _[_7:38 PM_]_
    
    Doing 1/3, u put a 0 next to 1 and a 0, below 3, do 10/3 u put 3 next to 0, cause it's closest to 10, u get remainder 1, so u put another 0 next to it to get rid of remainder, 3\*3 is closest to 10... Now so far we have 0,3 then 0,33 then 0,333... U never get rid of remainder

# Sources
Own notes

# Content Lists
If you prefer browsing the contents of this site through a list instead of a graph, you can find content lists here too:

- [All Notes](notes/)

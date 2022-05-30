---
title: "Document Object Model"
date: "2022-05-30 02:22"
author: "[Doriel Rivalet](https://github.com/DorielRivalet)"
tags:
- dom
---

# Metadata

2022-05-21 16:00

# Glossary
- HTML Element -> DOM Node
- JavaScript manipulates the DOM nodes
- Manipulation: modifying attributes, creation, deletion

# Deduction

- A DOM Node is an object that represents HTML Elements

- An object has attributes and methods

- We access the attributes via indexing, the notation can be something such as objectName.attributeName

- Conclusion: This means a DOM Node could have things such as .disabled

- .disabled sounds like an attribute/property that has a boolean value

- true or false, if domNodeName.disabled == true then the DOM Node is disabled.

```javascript

const element = document.querySelector(".className");
typeof element // Look at what this outputs
console.dir(element) // This gives you a list of all the properties the object reporesenting the element contains. Look at this as well I recommend ASU'S courses on precalculus and the preceeeding one on college algebra oboth available on edx. They use some software that tests your initial  knowledgfe and from them recommend you material to learn, very nice for gap-filling.

```

Remember: use ```defer``` in the HTML script tag to wait for everything to load.

# Sources: 
- The Odin Project Discord Server
- Own notes
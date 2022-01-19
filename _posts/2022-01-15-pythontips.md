---
layout: post
title: "Python Tips"
date: 2022-01-15
categories: learn
---

Some python tips for life

# Python 3

> Taking python course from github learning lab made me remember some things or learn brand new others. Check it out!

***

## Table of Contents
  - [Initializing the main function](#initializing-the-main-function)
  - [Reading files](#reading-files)
  - [Appending on lists](#appending-on-lists)

***
## Initializing the main function

Files `.py` are modules, and when imported they are executed within the main program.
To identify the difference between main program and imported modules we use the special variable `__name__`.
`__name__` tells us the name of our running module.
So, to single programs `__name__` = `__main__` (MAIN SCOPE), and imported modules `__name__` = the name of the module. 

```
if __name__ == "__main__":
    function_name()
```

***
## Reading files
Do you want to read lines from a `.txt` file?
Having the `file.txt` just:

```
    f = open("file.txt")
    file = f.readlines()
    f.close() # closes the reading file
```

***
## Appending on lists
List is a mutable chain of elements like `pizza = ['nice', 'cold']`. To append more elements :

```
    pizza.append('hot')
```

***

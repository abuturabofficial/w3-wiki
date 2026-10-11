---
draft: false
date: "2026-10-09T07:16:32+05:00"
title: "Week 7: Regualr Expressions"
linkTitle: "Regular Expressions"
menuPre: ""
LastModifierDisplayName: AbuTurab
LastModifierEmail: thesajid@proton.me
collapsibleMenu: true
alwaysOpen: false
weight: 8
---

| Week 7: Practice Code | [GitHub](https://github.com/abuturabofficial/pythonprac/tree/main/cs50p/week7-regex) |
| :-------------------: | :----------------------------------------------------------------------------------: |

## Regular Expressions

> A RegEx, or Regular Expression, is a sequence of characters that forms a search pattern. --- W3School

RegEx can be used to check if a string contains the specified search pattern.

Python has a built-in packaged called `re`, which can be used to word with Regular Expressions.

Import the `re` module:

```py
import re
```

### Metacharacters

Metacharacters are characters with a special meaning:

| Character |                                Description                                 |    Example     |
| :-------: | :------------------------------------------------------------------------: | :------------: |
|    []     |                            A set of characters                             |    "[a-m]"     |
|     \     | Signals a special sequence (can also be used to escape special characters) |      "\d"      |
|     .     |                  Any character (except newline character)                  |    "he..o"     |
|     ^     |                                Starts with                                 |    "^hello"    |
|     $     |                                 Ends with                                  |   "planet$"    |
|     *     |                          Zero or more occurrences                          |    "he.*o"     |
|     +     |                          One or more occurrences                           |    "he.+o"     |
|     ?     |                          Zero or one occurrences                           |    "he.?o"     |
|    {}     |                Exactly the specified number of occurrences                 |   "he.{2}.o"   |
|   {m,n}   |                          m-n range of repetitions                          |  "he.{2,4}.o"  |
|    \|     |                                 Either or                                  | "falls\|stays" |
|    ()     |                             Capture and group                              |

### Flags

You can add flags to the pattern when using regular expressions.

![W3School](/notes/cs50p/week7-regex-1.webp)

### Special Sequences

A special sequence is a `\` followed by one of the characters in the list below, and has a special mean:

![W3School](/notes/cs50p/week7-regex-2.webp)

### Sets

A set is a set of characters inside a pair of square brackets `[]` with a special meaning:

![W3School](/notes/cs50p/week7-regex-3.webp)

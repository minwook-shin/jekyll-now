---
layout: post
title: How to solve the Codewars's Array.diff
---

Today I try to solve the algorithm problem of codewars.

## Description

Your goal in this kata is to implement a difference function, which subtracts one list from another and returns the result.

It should remove all values from list a, which are present in list b.

## Example

* array_diff([1,2],[1]) == [2]

* array_diff([1,2,2,2,3],[2]) == [1,3]

## Code

* [] : built-in list type.

* append() : adds a single item to the existing list.

```python
def array_diff(a, b):
    result = []

    for i in a:
        if i not in b:
            result.append(i)
            
    return result
```
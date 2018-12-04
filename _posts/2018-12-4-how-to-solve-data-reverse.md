---
layout: post
title: How to solve the Codewars's Data Reverse
---

Today I try to solve the algorithm problem of codewars.

## Description

A stream of data is received and needs to be reversed.

Each segment is 8 bits long, meaning the order of these segments needs to be reversed.

## Example

11111111  00000000  00001111  10101010

->

10101010  00001111  00000000  11111111

## Code

* [] : built-in list type.

* slice : work on lists just as with strings.

```python
def data_reverse(data):
    arr = []
    while data:
        for i in data[-8:]:
            arr.append(i)
        data = data[:-8]
    return arr
```
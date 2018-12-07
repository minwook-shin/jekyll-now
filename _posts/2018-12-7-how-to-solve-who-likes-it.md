---
layout: post
title: How to solve the Codewars's Who likes it?
---

Today I try to solve the algorithm problem of codewars.

## Description

You probably know the "like" system from Facebook and other pages. 
People can "like" blog posts, pictures or other items. 
We want to create the text that should be displayed next to such an item.

## Examples

* likes {} -> "no one likes this"

* likes {"Peter"} -> "Peter likes this"

* likes {"Jacob", "Alex"} -> "Jacob and Alex like this"

* likes {"Max", "John", "Mark"} -> "Max, John and Mark like this"

* likes {"Alex", "Jacob", "Mark", "Max"} -> "Alex, Jacob and 2 others like this"


## Code

```java
class Solution {
    public static String whoLikesIt(String... names) {
        if(names.length == 0){
            return "no one likes this";
        }
        else if(names.length == 1){
            return names[0] + " likes this";
        }
        else if(names.length == 2){
            return names[0] + " and " + names[1] + " like this";
        }
        else if(names.length == 3){
            return names[0] + ", " + names[1] +  " and " + names[2] + " like this";
        }
        else{
            return names[0] + ", " + names[1] + " and " + (names.length - 2) + " others like this";
        }
    }
}
```
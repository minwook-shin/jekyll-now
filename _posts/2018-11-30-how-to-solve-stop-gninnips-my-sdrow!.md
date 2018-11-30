---
layout: post
title: How to solve the Codewars's Stop gninnipS My sdroW!
---

Today I try to solve the algorithm problem of codewars.

## Description

Write a function that takes in a string of one or more words, and returns the same string, but with all five or more letter words reversed (Just like the name of this Kata). 
Strings passed in will consist of only letters and spaces. 
Spaces will be included only when more than one word is present.

* five or more letter words : length() >= 5

## Examples

* spinWords("Hey fellow warriors") -> "Hey wollef sroirraw"

* spinWords("This is a test") -> "This is a test" 

* spinWords("This is another test") -> "This is rehtona test"

## Code

* StringBuffer().reverse() : returns StringBuffer object with the reversed sequence.

* String.join() : returns the concatenated string.

```java
public class SpinWords {
    public String spinWords(String sentence) {
        String[] arr = sentence.split(" ");
        for(int i=0;i<arr.length;i++){
            if(arr[i].length() >= 5)
                arr[i] = new StringBuffer(arr[i]).reverse().toString();
        }
        return String.join(" ",arr);
    }
}
```
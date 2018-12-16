---
layout: post
title: How to solve the Codewars's Count the smiley faces!
---

Today I try to solve the algorithm problem of codewars.

## Description

Given an array (arr) as an argument complete the function countSmileys that should return the total number of smiling faces.

Rules for a smiling face:

* Each smiley face must contain a valid pair of eyes. Eyes can be marked as : or ;

* A smiley face can have a nose but it does not have to. Valid characters for a nose are - or ~

* Every smiling face must have a smiling mouth that should be marked with either ) or D.

No additional characters are allowed except for those mentioned.

## Example

* countSmileys([':)', ';(', ';}', ':-D']) -> 2

* countSmileys([';D', ':-(', ':-)', ';~)']) -> 3

* countSmileys([';]', ':[', ';*', ':$', ';-D']) -> 1

## Code

* charAt() : returns the character at the String's specified index.

```java
import java.util.*;

public class SmileFaces {
  public static int countSmileys(List<String> arr) {
    int num = 0;
    for (String i : arr) {
      if (i.length() == 2) {
        if ((i.charAt(0) == ':' || i.charAt(0) == ';')&&(i.charAt(1) == 'D' || i.charAt(1) == ')')) {
          num++;
        }
      }
      if (i.length() == 3) {
        if ((i.charAt(0) == ':' || i.charAt(0) == ';')&&(i.charAt(1) == '-' || i.charAt(1) == '~')&&(i.charAt(2) == 'D' || i.charAt(2) == ')')) {
          num++;
        }
      }
    }
    return num;
  }
}
```
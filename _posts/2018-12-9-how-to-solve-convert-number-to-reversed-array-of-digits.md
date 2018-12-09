---
layout: post
title: How to solve the Codewars's Convert number to reversed array of digits
---

Today I try to solve the algorithm problem of codewars.

## Description

Convert number to reversed array of digits.
Given a random number.
You have to return the digits of this number within an array in reverse order.

## Example

348597 -> [7,9,5,8,4,3]


## Code

* stack : last-in-first-out (LIFO) stack of objects.

* valueOf() : Returns the string representation of the argument.

* split() : returns array of strings computed by splitting.

* parseInt() :  returns the integer representation of the argument.

```java
import java.util.*;

public class Kata {
    public static int[] digitize(long n) {
        Stack<String> stack = new Stack<String>();
        String tmp = String.valueOf(n);
        String[] tmpArr = tmp.split("");
        int [] digits = new int[tmpArr.length];
    
        for(String i : tmpArr){
            stack.push(i);
        }
        for(int i= 0;!stack.empty();i++){
            digits[i] = Integer.parseInt(stack.pop());
        }
    
        return digits;
    }
}
```
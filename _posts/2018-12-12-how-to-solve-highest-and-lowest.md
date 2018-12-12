---
layout: post
title: How to solve the Codewars's Highest and Lowest
---

Today I try to solve the algorithm problem of codewars.

## Description

In this little assignment you are given a string of space separated numbers, and have to return the highest and lowest number.

## Example

* HighAndLow("1 2 3 4 5") -> "5 1"

* HighAndLow("1 2 -3 4 5") -> "5 -3"

* HighAndLow("1 9 3 4 -5") -> "9 -5"


## Code

* split() : returns array of strings computed by splitting.

* parseInt() : returns the integer representation of the argument.

* Arrays.sort() : array to be sorted.

* Integer.toString() : returns the String object representing the Integer value.

```java
import java.util.*;

public class Kata {
    public static String HighAndLow(String numbers) {
        String[] arr = numbers.split(" ");
        int [] intArr = new int[arr.length];
        for(int i= 0;intArr.length>i;i++){
            intArr[i] = Integer.parseInt(arr[i]);
        }
        Arrays.sort(intArr);
        return Integer.toString(intArr[intArr.length-1]) + " " + Integer.toString(intArr[0]) ;
    }
}
```
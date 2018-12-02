---
layout: post
title: How to solve the Codewars's Scramblies
---

Today I try to solve the algorithm problem of codewars.

## Description

Complete the function scramble(str1, str2) that returns true if a portion of str1 characters can be rearranged to match str2, otherwise returns false.

## Examples

* scramble('rkqodlw', 'world') -> True

* scramble('cedewaraaossoqqyt', 'codewars') -> True

* scramble('katas', 'steak') -> False

## Code

* split : returns array of strings computed by splitting.

* equals : returns true if the String are equal.

Similar to the bubble sort algorithm.
However, if finds a value, erases it.

```java
public class Scramblies {
    public static boolean scramble(String str1, String str2) {
        int count = 0;
        String[] str1arr = str1.split("");
        String[] str2arr = str2.split("");
        for(String i : str2arr){
            int tmp = 0;
            for(String j : str1arr){
                if(i.equals(j)){
                    count++;
                    for(int k = tmp;k<str1arr.length -1;k++){
                        str1arr[k] = str1arr[k+1];
                    }
                    break;
                }
                tmp++;
            }
        }
        return str2.length() == count;
    }
}
```
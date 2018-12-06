---
layout: post
title: How to solve the Codewars's Valid Braces
---

Today I try to solve the algorithm problem of codewars.

## Description

Write a function that takes a string of braces, and determines if the order of the braces is valid. 

It should return true if the string is valid, and false if it's invalid.

All input strings will be nonempty, and will only consist of parentheses, brackets and curly braces: ()[]{}.

## Examples

* "(){}[]"   ->  True

* "([{}])"   ->  True

* "(}"       ->  False

* "[(])"     ->  False

* "[({})](]" ->  False

## Code

* stack : last-in-first-out (LIFO) stack of objects.

* split() : returns array of strings computed by splitting.

* equals() : returns true if the String are equal.

```java
import java.util.Stack;

public class BraceChecker {
    public boolean isValid(String braces) {
        String[] arr = braces.split("");
        Stack<String> s = new Stack<>();
        for(String i : arr){
            if(i.equals("(")||i.equals("{")||i.equals("[")){
                s.push(i);
            }
            else{
                if(s.empty()){
                    return false;
                }
                if(i.equals("]")&& s.peek().equals("[")){
                    s.pop();
                    continue;
                }
                if(i.equals(")")&& s.peek().equals("(")){
                    s.pop();
                    continue;
                }
                if(i.equals("}")&& s.peek().equals("{")){
                    s.pop();
                    continue;
                }
                else{
                    return false;
                }
            }
        }
        return (s.empty());
    }
}
```
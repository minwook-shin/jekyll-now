---
layout: post
title: How to solve the Codewars's Regex validate PIN code
---

Today I try to solve the algorithm problem of codewars.

## Description

ATM machines allow 4 or 6 digit PIN codes and PIN codes cannot contain anything but exactly 4 digits or exactly 6 digits.

If the function is passed a valid PIN string, return true, else return false.

## Example

* Solution.validatePin("1234") -> true

* Solution.validatePin("12345") -> false

* Solution.validatePin("a234") -> false

## Code

* charAt() : returns the character at the String's specified index.

```java
public class Solution {
  public static boolean validatePin(String pin) {
    for(int i = 0; i < pin.length(); i++){
      if((pin.length() == 4 || pin.length() == 6)&&(pin.charAt(i) >= '0' && pin.charAt(i) <= '9')){
        try {
            Integer.valueOf(pin);
        }catch (Exception e) {
            break;
        }
        return true;
      }
      else{
        break;
      }
    }
    return false;
  }
}
```
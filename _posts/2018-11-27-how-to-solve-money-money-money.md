---
layout: post
title: How to solve the Codewars's Money, Money, Money
---

Today I try to solve the algorithm problem of codewars.

## Description

Mr. Scrooge has a sum of money 'P' that wants to invest, and he wants to know how many years 'Y' this sum has to be kept in the bank in order for this sum of money to amount to 'D'.

The sum is kept for 'Y' years in the bank where interest 'I' is paid yearly, and the new sum is re-invested yearly after paying tax 'T'

Note that the principal is not taxed but only the year's accrued interest

## Example

* Let P be the Principal = 1000.00      

* Let I be the Interest Rate = 0.05      

* Let T be the Tax Rate = 0.18      

* Let D be the Desired Sum = 1100.00


* After 1st Year --> P = 1041.00

* After 2nd Year --> P = 1083.86

* After 3rd Year --> P = 1128.30

## Code

Interest : money * interest

Tax : money * interest * tax

money = money + (Interest - Tax)

```java
public class Money {
    public static int calculateYears(double principal, double interest,  double tax, double desired) {
        double money = principal;
        int count = 0;
        while(desired > money){
            count++;
            money = money + (money * interest - (money * interest * tax));
        }
        return count;
    }
}
```

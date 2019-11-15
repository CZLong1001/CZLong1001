---
layout:     post
title:      "LeetCode9"
subtitle:   " \回文数\""
date:       2019-11-15 13:50
author:     "Czl"
header-img: "img/post-bg-2015.jpg"
tags:
    - 算法
---

## 题目概述

### 题号：[9.回文数](" https://leetcode-cn.com/problems/palindrome-number/ ")

### 难度：简单

### 内容：

```
判断一个整数是否是回文数。回文数是指正序（从左向右）和倒序（从右向左）读都是一样的整数。

示例 1:

输入: 121
输出: true
示例 2:

输入: -121
输出: false
解释: 从左向右读, 为 -121 。 从右向左读, 为 121- 。因此它不是一个回文数。
示例 3:

输入: 10
输出: false
解释: 从右向左读, 为 01 。因此它不是一个回文数。
进阶:

你能不将整数转为字符串来解决这个问题吗？

```


## 思路

利用LeetCode7 整数反转的方法将数字反转，判断是否与原数字相等，若相等则为回文数，否则不是。

### Code

```
class Solution {
public:
    bool isPalindrome(int x) {
        	int num=0;
            int a=x;
            if((x<0) || (x%10==0 && x != 0)){
                return false;
            }else {
                for(;x/10 != 0;x=x/10){
                    num=num*10+x%10;
                }
                if( num < -2147483648/10 || num > 2147483647/10){
                    return false;
                }else {
                    num = num*10+x;
                    if(num == a){
                        return true;
                    }else {
                        return false;
                    }
                }
            }
    }
};
```

## 测试 Submit

![submit](http://ww1.sinaimg.cn/large/006Gc1hlly1g8yp4f0fxqj308s01st8i.jpg "")

## 收获总结

回文数肯定不会溢出，所以反转后溢出的肯定不是回文数

通过% / * 即可完成整数的反转，判断是否溢出时不可直接判断，可通过比较整数/10和2147483647/10的大小进行判断
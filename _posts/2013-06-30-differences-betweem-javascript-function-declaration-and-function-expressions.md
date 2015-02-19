---
title: Differences betweem Javascript Function Declaration and Function Expressions
author: Martin Wolf
layout: post
permalink: /2013/06/30/differences-betweem-javascript-function-declaration-and-function-expressions/
linked_list_url:
  - http://tckidd.wordpress.com/2013/05/17/javascript-function-declaration-vs-function-expressions/
categories:
  - Linked List
tags:
  - functions
  - javascript
  - js
---
<p class="linked-list-quote-author">
  tckidd:
</p>

> While javascript usually executes code on a line by line basis, functions are handled slightly differently. Before the code starts to execute, functions are usually pulled to the execution context, a process called function declaration hoisting. Function declarations make the respective functions available for execution regardless of their position. Function expression, on the other hand, limits the scope of the function until the line has been executed. This means the function is useless when called before function has been declared.
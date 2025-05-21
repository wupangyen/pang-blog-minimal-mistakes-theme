---
layout: single
title: What is pointer in C++
author: 邦彥
date: 2025-05-21T12:44:00.000Z
thumbnail: /images/pexels-luis-gomes-166706-546819.jpg
---
pointer in c++ is like creating a new object in java 

in java:\
Listnode node = new Listnode(1);

in c++:

Listnode* node = new Listnode(1);\
\
and when you dereferencing a pointer , it's like get or change a variable in java, in java dereferencing is done automatically

in c++:\
node-value = 5;



in java:

node.value = 5;

what dereferencing actually is we go to the actual memory address stored in the pointer and get the value, or the object stored in the memory address\
\
what is & in c++\
\
& in c++ is getting the memory address of the variable \
\
example:\
\
string s = "godisgood";

string *p = &s;\
\
\
what is memory leak?

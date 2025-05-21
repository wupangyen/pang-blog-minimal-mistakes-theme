---
layout: single
title: What is a pointer in C++
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

it's when you create a new object and never delete it inside the scope, so when you are out of scope, there is no pointer to reach the variable, and the memory is lost.\
\
example:

```
void example() {
  Listnode* node = new Listnode(1); // allocate memory on heap 
  // we didn't called delete node at the end of function 
  // node pointer disappears when the function ends 
}
// but the memory still on the heap, and we have no pointer to reach it, caused memory leak 

```

\
what is a heap:\
a part of computer's memory where our program and dynamically store data \
\
what is a memory:\
where data is store and access by the processor when the program is running \
\
what is a processor:\
part of computer called the central processing unit , runs program makes decision and performs calculation when the program is running

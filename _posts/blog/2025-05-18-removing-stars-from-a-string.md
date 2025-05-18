---
layout: single
title: Removing Stars From a String
author: 邦彥
date: 2025-05-18T16:45:00.000Z
thumbnail: /images/pexels-luis-gomes-166706-546819.jpg
---
🔗<https://leetcode.com/problems/removing-stars-from-a-string/?envType=study-plan-v2&envId=leetcode-75>\
\
This is my first solution, but the run time can be improved.\
Currently

`result = result + value.next();`\
this part the complexity is O(n^2)\
can be improved with string builder \
\
so why is string concatenation in a loop time complexity O(n^2)?\
example: we have a string "god"

"" + g\
g + o

go + d

so each operation don't just add a single character a time, instead it's creating a new string and added the previous string \
\
\
1 + 2  + 3 + ....... +n\
total copy operation under the hood\
which is n(n+1)/2 = n^2

```
class Solution {
    public String removeStars(String s) {
        // have a loop go through the length of s 

        // and create a stack 
        // if the character is not a star then push the character to stack, if it's a start pop don't push and remove the last char

        Stack<Character> res = new Stack<>();

        for(int i = 0; i < s.length(); i++) {
            if(s.charAt(i) != '*') {
                res.push(s.charAt(i));
            }
            else {
                res.pop();
            }

        }

        String result = "";

        Iterator value = res.iterator();

        while(value.hasNext()) {
            result = result + value.next();
        }

        return result;
    }
}
```

---
layout: single
title: Removing Stars From a String
author: 邦彥
date: 2025-05-18T16:45:00.000Z
thumbnail: /images/pexels-luis-gomes-166706-546819.jpg
---
🔗<https://leetcode.com/problems/removing-stars-from-a-string/?envType=study-plan-v2&envId=leetcode-75>\
\
This is my first solution, but the time complexity can be improved!

Space Complexity is O(n)
n is the length of String s

\
Currently`result = result + value.next();`\
this part the Time Complexity is O(n^2)\
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
1 + 2  + 3 + ....... +n        which is n(n+1)/2 = n^2\
is the total copy operation under the hood.

```
class Solution {
    public String removeStars(String s) {
        // have a loop go through the length of s 

        // and create a stack 
        // if the character is not a star then push the character to stack, 
        // if it's a star, pop, don't push and remove the last char

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



Below uses String Builder:\
Time complexity Improve to O(n)\
Space complexity is the same 

```
class Solution {
    public String removeStars(String s) {


        Stack<Character> res = new Stack<>();

        for(int i = 0; i < s.length(); i++) {
            if(s.charAt(i) != '*') {
                res.push(s.charAt(i));
            }
            else {
                res.pop();
            }

        }
        StringBuilder sb = new StringBuilder("");
        while(!res.isEmpty()) {
            sb.append(res.pop());

        }

        return sb.reverse().toString();
    }
}
```

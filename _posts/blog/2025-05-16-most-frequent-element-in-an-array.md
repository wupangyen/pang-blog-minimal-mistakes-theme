---
layout: single
title: "Most Frequent Element In An Array "
author: 邦彥
date: 2025-05-16T18:26:00.000Z
thumbnail: /images/pexels-luis-gomes-166706-546819.jpg
---
Question Link: <https://www.geeksforgeeks.org/problems/most-frequent-element-in-an-array/1>\
\
There are 3 approaches to tackle this question \
\
First is the Naive approach, the time complexity is O(n^2), we are using 2 for loops 

and is O(1) space because the 2 for loop is going through the same array, we didn't create any extra space in this algorithm 

```
class Solution {
    public int mostFreqEle(int[] arr) {
    int res = 0;
    int maxcount = 0;
    int n = arr.length;
    
    1,1,2,2,3
    
    for(int i = 0; i < n; i++){
      int count = 0;
      for(int j = 0; j < n; j++){
        if(arr[i] == arr[j]){
          count++;
        }
        if(count > maxcount || count == maxcount && arr[i] > res){
          maxcount = count;
          res = arr[i];
        }
      }
    }

    return res;
}
```

\
second approach

---
layout: single
title: Finding the Most Frequent Element in an Array — 3 Approaches (Java)
author: 邦彥
date: 2025-05-16T18:26:00.000Z
thumbnail: /images/pexels-luis-gomes-166706-546819.jpg
---



### 🔗Problem Link: [https://www.geeksforgeeks.org/problems/most-frequent-element-in-an-array/1](<>)[](https://www.geeksforgeeks.org/problems/most-frequent-element-in-an-array/1)

[](https://www.geeksforgeeks.org/problems/most-frequent-element-in-an-array/1)

## ✅ Objective

Given an array of integers, return the most frequent element. If multiple elements have the same highest frequency, return the one with the greater value.



## 1️⃣ Naive Approach

The time complexity is O(n^2), because we are using 2 for loops, and is O(1) space because the 2 for loop is going through the same array, we didn't create any extra space in this algorithm 



### 🧑🏻‍💻 Code:

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



## 2️⃣ Better Approach (Using Sorting)

we sort first, and use linear traversal to find the most frequent number \
for time complexity is O(nlogn) because of sorting average take that amount of time\
for space complexity is O(1) we didn't create extra space in this case 




### 🧑🏻‍💻 Code:

```
class Solution {
    public int mostFreqEle(int[] arr) {
      Arrays.sort(arr);
      
      int res = arr[i], currCnt = 1, maxCnt = 1;
      for(int i = 1; i < arr.length; i++) {
        if(arr[i] == arr[i-1]) {
          currCnt++;
        }
        else {
        currCnt = 1;
        }
        
        if(currCnt > maxCnt || currCnt == maxCnt && arr[i] > res){
          maxCnt = currCnt;
          res = arr[i];
        }
      }
      return res;
    }
}
```



## 3️⃣ Optimal Approach (Using HashMap)

\
\
use a hash table, use O(n) time and O(n) space \
we store the frequency of each number in the array in a single traversal.

### 🧑🏻‍💻Code:

```
import java.util.HashMap;
class Solution {
    public int mostFreqEle(int[] arr) {
      HashMap<Integer, Integer> freqMap = new HashMap<Integer, Integer>();
      for(int i = 0; i < arr.length; i++){
        freqMap.put(arr[i],freqMap.getOrDefault(arr[i],0)+1);
      }
      
      int res = -1;
      int maxCnt = 0;
      for(var entry: freq.entrySet()) {
        int count = entry.getValue();
        int val = entry.getKey();
        
        if(count > maxCnt || count == maxCnt && val > res){
          maxCnt = count;
          res = val;
        }
      }
      return res;
    }
}
```

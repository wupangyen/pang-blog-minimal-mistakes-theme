---
layout: single
title: 2215. Find the Difference of Two Arrays
author: 邦彥
date: 2025-05-17T21:17:00.000Z
thumbnail: /images/pexels-luis-gomes-166706-546819.jpg
---
\
🔗Question Link: <https://leetcode.com/problems/find-the-difference-of-two-arrays/description/?envType=study-plan-v2&envId=leetcode-75>


⏱ Time & Space Complexity

Time Complexity: O(M + N) We loop through both arrays once (M = nums1.length, N = nums2.length), and then iterate through the sets.

Space Complexity: O(M + N) We store two sets and two result lists, each proportional to the input size.




First, we use two sets to store the unique elements from nums1 and nums2. This removes duplicates.

Then, we create two empty lists: One to store elements that are in nums1 but not in nums2

Another to store elements that are in nums2 but not in nums1



We loop through each element in the first set (set1) and check if it does not exist in set2. If this condition is valid we add it to list1. 

Finally, we return both lists wrapped in a single list as the result.



















```
class Solution {
    public List<List<Integer>> findDifference(int[] nums1, int[] nums2) {
        Set<Integer> set1 = new HashSet<>();
        Set<Integer> set2 = new HashSet<>();

        for(int num: nums1) {
            set1.add(num);
        }

        for(int num: nums2) {
            set2.add(num);
        }

        List<Integer> list1 = new ArrayList<>();
        List<Integer> list2 = new ArrayList<>();

        for(int num: set1){
            if(!set2.contains(num)){
                list1.add(num);
            }
        }

        for(int num: set2) {
            if(!set1.contains(num)) {
                list2.add(num);
            }
        }
        return Arrays.asList(list1, list2);
    }
}
```

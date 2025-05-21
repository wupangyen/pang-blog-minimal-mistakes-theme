---
layout: single
title: Unique Paths
author: 邦彥
date: 2025-05-19T21:29:00.000Z
thumbnail: /images/pexels-luis-gomes-166706-546819.jpg
---
🔗https://leetcode.com/problems/unique-paths/?envType=study-plan-v2&envId=leetcode-75\
\
this is the first solution\
Time: O(m*n) m is the number of rows, n is the number of columns\
Space: O(m*n) we created a 2d vector, so extra space with m elements for row vector , and n elements for column vector 

```
class Solution {
public:
    int uniquePaths(int m, int n) {
        vector<vector<int>> dp(m,vector<int>(n,1));
        for(int i = 1; i < m; i++) {
            for(int j = 1; j < n; j++) {
                dp[i][j] = dp[i-1][j] + dp[i][j-1];
            }
        }
        return dp[m-1][n-1];
    }
};
```

\
The code below  is an improvement of space complexity\
we don't need a 2d vector

we only need 2, 1d vectors

one store the previous row, one store the current row 



```
class Solution {
public:
    int uniquePaths(int m, int n) {

        vector<int> pre(n,1), cur(n,1);
        for(int i = 1; i < m; i++) {
            for(int j = 1; j < n; j++) {
                cur[j] = pre[j] + cur[j-1];
            }
            swap(pre,cur);
        }
        return pre[n-1];
    }
};
```



code below reduce the space to one vector \
before we have 2 vectors pre and cur

but pre\[j](the value from the row above) is just cur\[j] before updating

by iterating from left to right we ensure that cur\[j-1] holds the correct value for current row (left) and cur\[j] holds the correct value for previous role(top)so we don't need pre\[j] this vector 

```
class Solution {
public:
    int uniquePaths(int m, int n) {

        vector<int> cur(n,1);
        for(int i = 1; i < m; i++) {
            for(int j = 1; j < n; j++) {
                cur[j] += cur[j] + cur[j-1];
            }
        }
        return cur[n-1];
    }
};
```

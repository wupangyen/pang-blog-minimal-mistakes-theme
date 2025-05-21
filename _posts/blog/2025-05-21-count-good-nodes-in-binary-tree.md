---
layout: single
title: Count Good Nodes in Binary Tree
author: 邦彥
date: 2025-05-21T15:07:00.000Z
thumbnail: /images/pexels-luis-gomes-166706-546819.jpg
---
🔗 https://leetcode.com/problems/count-good-nodes-in-binary-tree/?envType=study-plan-v2&envId=leetcode-75\
Time: O(n) n is the total number of nodes\
Space: O(h) h is the height of the tree

```
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode() : val(0), left(nullptr), right(nullptr) {}
 *     TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
 *     TreeNode(int x, TreeNode *left, TreeNode *right) : val(x), left(left), right(right) {}
 * };
 */
class Solution {
public:
    int count = 0;
    void dfs(TreeNode* node, int curMax) {
        if(!node) return;
        
        if(node->val >= curMax) {
            count++;
            curMax = node->val;
        }
        dfs(node->left, curMax);
        dfs(node->right, curMax);
    }
    int goodNodes(TreeNode* root) {
        dfs(root, root->val);
        return count;
        
    }
};
```

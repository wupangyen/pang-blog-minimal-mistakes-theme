---
layout: single
title: Delete the Middle Node of a Linked List
author: 邦彥
date: 2025-05-20T21:17:00.000Z
thumbnail: /images/pexels-luis-gomes-166706-546819.jpg
---
we use two pointers method.\
slow pointer set to the prev node

fast pointer set to the head node

\
fast is going twice as fast as slow, so when fast is at the node before the last node of the linked list, slow is at the position before the middle node, and we remove the middle element by setting slow-> next = slow -> next -> next \
\
\
\
Time: O(n) n is the length of linked list \
Space: O(1)





```
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode() : val(0), next(nullptr) {}
 *     ListNode(int x) : val(x), next(nullptr) {}
 *     ListNode(int x, ListNode *next) : val(x), next(next) {}
 * };
 */
class Solution {
public:
    ListNode* deleteMiddle(ListNode* head) {
        if(head == NULL)return NULL;
        ListNode* prev = new ListNode(0);
        prev->next = head;
        ListNode* slow = prev;
        ListNode* fast = head;
        while(fast != NULL && fast->next != NULL){
            slow = slow->next;
            fast = fast->next->next;
        }
        slow->next = slow->next->next;
        return prev->next;

        
    }
};
```

# leetcode 148 排序链表

## edited by 王少锐

## c++

### 题目要求在 O(n log n) 时间复杂度和常数级空间复杂度下，对链表进行排序。

### 直接使用快排 sort，当然你也可以手写一个!

```cpp
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode(int x) : val(x), next(NULL) {}
 * };
 */
class Solution {
public:
    ListNode *sortList(ListNode *head) {
        vector<int> temp;
        ListNode *p = head;
        while (p) {
            temp.push_back(p->val);
            p = p->next;
        }
        sort(temp.begin(), temp.end());
        int i = 0;
        p = head;
        while (p) {
            p->val = temp[i++];
            p = p->next;
        }
        return head;
    }
};

```

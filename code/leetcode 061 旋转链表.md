# leetcode 061 旋转链表

## edited by 王少锐

## c++

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
    ListNode *rotateRight(ListNode *head, int k) {
        if (head == NULL || k == 0)
            return head;
        vector<int> temp;
        int len = 0;
        ListNode *p = head;
        while (p) {
            temp.push_back(p->val);
            p = p->next;
            len++;
        }
        int a[len];
        for (int i = 0; i < len; i++) {
            a[(i + k) % len] = temp[i];
        }
        int i = 0;
        p = head;
        while (p) {
            p->val = a[i++];
            p = p->next;
        }
        return head;
    }
};

```

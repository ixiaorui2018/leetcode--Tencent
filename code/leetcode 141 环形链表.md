# leetcode 141 环形链表

## edited by 王少锐

## c

```c
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     struct ListNode *next;
 * };
 */
bool hasCycle(struct ListNode *head) {
    struct ListNode *p1 = head;
    struct ListNode *p2 = head;

    while (p2 != NULL && p2->next != NULL) {
        p2 = p2->next->next;
        p1 = p1->next;
        if (p1 == p2)
            return true;
    }
    return false;
}

```

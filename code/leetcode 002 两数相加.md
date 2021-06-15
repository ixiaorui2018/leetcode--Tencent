# leetcode 002 两数相加

## edited by 王少锐

## C

```c
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     struct ListNode *next;
 * };
 */
struct ListNode *addTwoNumbers(struct ListNode *l1, struct ListNode *l2) {
    int x = 0, temp;
    struct ListNode *p1, *p2, *ret;
    ret = l1;
    while (l1 && l2) {
        temp = l1->val + l2->val + x;
        l1->val = temp % 10;
        x = temp / 10;
        p2 = l1;
        l1 = l1->next;
        l2 = l2->next;
    }
    if (!l1) {
        p2->next = l2;
        l1 = p2->next;
    }
    while (l1) {
        temp = l1->val + x;
        l1->val = temp % 10;
        x = temp / 10;
        p2 = l1;
        l1 = l1->next;
    }
    if (x) {
        p1 = (struct ListNode *)malloc(sizeof(struct ListNode));
        p1->next = NULL;
        p1->val = x;
        p2->next = p1;
    }
    return ret;
}
```

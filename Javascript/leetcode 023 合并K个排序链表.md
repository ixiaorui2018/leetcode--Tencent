# leetcode 023 合并 K 个排序链表

## edited by 王少锐

## JavaScript

```javascript
/**
 * Definition for singly-linked list.
 * function ListNode(val, next) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.next = (next===undefined ? null : next)
 * }
 */
/**
 * @param {ListNode[]} lists
 * @return {ListNode}
 */
const mergeKLists = function (lists) {
    if (!lists.length) return null;
    if (lists.length === 1) return lists[0];
    let res = lists.reduce((l1, l2) => {
        return mergeTwoLists(l1, l2);
    }, null);
    return res;
};

let mergeTwoLists = function (l1, l2) {
    let head = new ListNode(),
        pre = head;
    while (l1 && l2) {
        if (l1.val > l2.val) {
            pre.next = l2;
            l2 = l2.next;
        } else {
            pre.next = l1;
            l1 = l1.next;
        }
        pre = pre.next;
    }
    pre.next = l1 ? l1 : l2;
    return head.next;
};
```

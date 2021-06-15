# leetcode 002 两数相加

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
 * @param {ListNode} l1
 * @param {ListNode} l2
 * @return {ListNode}
 */
var addTwoNumbers = function (l1, l2) {
    const l3 = new ListNode(0);
    let p = l3;
    let cf = 0;
    while (l1 || l2) {
        const v1 = l1 ? l1.val : 0;
        const v2 = l2 ? l2.val : 0;
        const v3 = v1 + v2 + cf;
        cf = Math.floor(v3 / 10);
        p.next = new ListNode(v3 % 10);
        p = p.next;
        if (l1) l1 = l1.next;
        if (l2) l2 = l2.next;
    }
    if (cf) p.next = new ListNode(cf);
    return l3.next;
};

```

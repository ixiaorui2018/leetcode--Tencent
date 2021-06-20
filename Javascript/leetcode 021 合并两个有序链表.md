# leetcode 021 合并两个有序链表

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
const mergeTwoLists = function (l1, l2) {
    let res = new ListNode(0, null);
    let p = res;
    while (l1 || l2) {
        if (!l1) {
            p.next = l2;
            break;
        }
        if (!l2) {
            p.next = l1;
            break;
        }
        if (l1.val < l2.val) {
            let t = new ListNode(l1.val, null);
            p.next = t;
            p = t;
            l1 = l1.next;
        } else {
            let t = new ListNode(l2.val, null);
            p.next = t;
            p = t;
            l2 = l2.next;
        }
    }
    return res.next;
};
```

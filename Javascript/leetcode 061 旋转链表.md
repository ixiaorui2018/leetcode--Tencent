# leetcode 061 旋转链表

## edited by 王少锐

## JavaScript

### 方法一，空间换时间！

```javascript
/**
 * Definition for singly-linked list.
 * function ListNode(val, next) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.next = (next===undefined ? null : next)
 * }
 */
/**
 * @param {ListNode} head
 * @param {number} k
 * @return {ListNode}
 */
const rotateRight = function (head, k) {
    if (!head || !head.next || k === 0) return head;
    let a = [],
        b = [];
    let p = head,
        len = 0;
    while (p) {
        a.push(p.val);
        p = p.next;
        len++;
    }
    p = head;
    for (let i = 0; i < len; i++) {
        b[(i + k) % len] = a[i];
    }
    for (let i = 0; i < len; i++) {
        p.val = b[i];
        p = p.next;
    }
    return head;
};
```

### 方法二，快慢指针法！

```javascript
/**
 * Definition for singly-linked list.
 * function ListNode(val, next) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.next = (next===undefined ? null : next)
 * }
 */
/**
 * @param {ListNode} head
 * @param {number} k
 * @return {ListNode}
 */
const rotateRight = function (head, k) {
    if (!head || !head.next || k === 0) return head;
    let p = head,
        len = 0;
    while (p) {
        p = p.next;
        len++;
    }
    k = k % len;
    let fast = head,
        slow = head;
    for (let i = 0; i < k; i++) {
        slow = slow.next;
    }
    while (slow.next) {
        fast = fast.next;
        slow = slow.next;
    }
    slow.next = head;
    head = fast.next;
    fast.next = null;
    return head;
};
```

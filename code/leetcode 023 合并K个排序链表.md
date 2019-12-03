# leetcode 023 合并K个排序链表
## edited by 王少锐
## Java


```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) { val = x; }
 * }
 */
class Solution {
    public ListNode f(ListNode l1,ListNode l2){
        if(l1==null)return l2;
        if(l2==null)return l1;
        ListNode p;
        if(l1.val>l2.val){
            p=l2;
            p.next=f(l1,l2.next);
        }else{
            p=l1;
            p.next=f(l1.next,l2);
        }
        return p;
    }
    public ListNode mergeKLists(ListNode[] lists) {
        if(lists.length==0)
            return null;
        if(lists.length==1)
            return lists[0];
        if(lists.length==2)
            return f(lists[0],lists[1]);
        int mid=lists.length/2;
        ListNode []l1=new ListNode[mid];
        for(int i=0;i<mid;i++){
            l1[i]=lists[i];
        }
        ListNode []l2=new ListNode[lists.length-mid];
        int j=0;
        for(int i=mid;i<lists.length;i++){
            l2[j++]=lists[i];
        }
        return f(mergeKLists(l1),mergeKLists(l2));
    }
}

```


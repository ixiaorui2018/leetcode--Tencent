# leetcode 021 合并两个有序链表
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
struct ListNode* mergeTwoLists(struct ListNode* l1, struct ListNode* l2) {
    struct ListNode*a=(struct ListNode*)malloc(sizeof(struct ListNode));
    struct ListNode*p,*q,*w;
    a->next=NULL;
    p=a;
    q=l1;
    w=l2;
    while(q!=NULL&&w!=NULL){
        if(q->val<w->val)
        {
            p->next=q;
            q=q->next;
            p=p->next;
            p->next=NULL;
        }
        else
        {
            p->next=w;
            w=w->next;
            p=p->next;
            p->next=NULL;
        }
    }
    while(q!=NULL){
        p->next=q;
        q=q->next;
        p=p->next;
        p->next=NULL;
    }
    while(w!=NULL){
        p->next=w;
        w=w->next;
        p=p->next;
        p->next=NULL;
    }
    p=a->next;
    free(a);
    return p;
}

```


# leetcode 206 反转链表
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
    ListNode* reverseList(ListNode* head) {
        vector<int>temp;
        int count=0;
        ListNode* p=head;
        while(p){
            temp.push_back(p->val);
            p=p->next;
            count++;
        }
        p=head;
        for(int i=count-1;i>=0;i--){
            p->val=temp[i];
            p=p->next;
        }
        return head;
    }
};

```

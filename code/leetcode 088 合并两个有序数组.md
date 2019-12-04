# leetcode 88 合并两个有序数组
## edited by 王少锐
## c++



```cpp
class Solution {
public:
    void merge(vector<int>& nums1, int m, vector<int>& nums2, int n) {
        int i=0,j=0,k=0;
        vector<int>t(m+n,0);
        while(i<m&&j<n){
            if(nums1[i]<nums2[j]){
                t[k++]=nums1[i++];
            }
            else{
                t[k++]=nums2[j++];
            }
        }
        while(i<m){
            t[k++]=nums1[i++];
        }
        while(j<n){
            t[k++]=nums2[j++];
        }
        for(int a=0;a<m+n;a++){
            nums1[a]=t[a];
        }
    }
};

```


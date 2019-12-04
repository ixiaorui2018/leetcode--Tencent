# leetcode 217 存在重复元素
## edited by 王少锐
## c



```c
bool containsDuplicate(int* nums, int numsSize) {
    int i,j;
    for(i=0;i<numsSize-1;i++){
        for(j=i+1;j<numsSize;j++){
            if(nums[i]==nums[j])
                return true;
        }
    }
    return false;
}

```


# leetcode 026 删除排序数组中的重复项

## edited by 王少锐

## c

```c
int removeDuplicates(int *nums, int numsSize) {
    if (numsSize == 0)
        return 0;
    int length = 1;
    for (int i = 0; i < numsSize; i++) {
        if (nums[i] != nums[length - 1])
            nums[length++] = nums[i];
    }
    return length;
}

```

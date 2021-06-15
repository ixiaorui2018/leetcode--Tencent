# leetcode 238 除自身以外数组的乘积

## edited by 王少锐

## Java

```java
//hhh本来很简单的题目，要求不使用除法;
class Solution {
    public int[] productExceptSelf(int[] nums) {
        //通过两遍循环，记录每个位置左边的所有数的乘积已右边所有数的乘积;
        //建个临时数组暂存数据先;
        int len = nums.length;
        int[] temp = new int[len];
        int left = 1, right = 1;
        for (int i = 0; i < len; i++) {
            temp[i] = left;
            left *= nums[i];
        }
        for (int j = len - 1; j >= 0; j--) {
            temp[j] *= right;
            right *= nums[j];
        }
        return temp;
    }
}

```

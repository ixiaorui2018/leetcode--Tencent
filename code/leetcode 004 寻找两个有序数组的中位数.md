# leetcode 004 寻找两个有序数组的中位数

## edited by 王少锐

## C++

```cpp
class Solution {
public:
    double findMedianSortedArrays(vector<int> &nums1, vector<int> &nums2) {
        double res;
        vector<int> t;
        for (int i = 0, j = 0; i < nums1.size() || j < nums2.size();) {
            if (i < nums1.size() && j < nums2.size()) {
                if (nums1[i] <= nums2[j]) {
                    t.push_back(nums1[i]);
                    i++;
                }
                else {
                    t.push_back(nums2[j]);
                    j++;
                }
            }
            else if (j == nums2.size()) {
                t.push_back(nums1[i]);
                i++;
            }
            else if (i == nums1.size()) {
                t.push_back(nums2[j]);
                j++;
            }
        }
        if (t.size() % 2 == 1) {
            res = t[t.size() / 2] * 1.0;
        }
        else {
            res = (t[t.size() / 2] + t[t.size() / 2 - 1]) * 1.0 / 2;
        }
        return res;
    }
}
};

```

## 这里再展示来自评论区 python 的写法！

```python
class Solution(object):
    def findMedianSortedArrays(self, nums1, nums2):
        """
        :type nums1: List[int]
        :type nums2: List[int]
        :rtype: float
        """
        if nums1 is None or nums2 is None:
            return
        a = len(nums1)
        b = len(nums2)
        total = a + b
        if total == 0:
            return
        if b == 0:
            return self.findMedianSortedArrays(nums2, nums1)
        left = -1
        right = -1
        nums1_start = 0
        nums2_start = 0
        for i in range(int(total / 2) + 1):
            left = right
            if nums1_start < a and (nums2_start >= b or
                                    nums1[nums1_start] < nums2[nums2_start]):
                right = nums1[nums1_start]
                nums1_start += 1
            else:
                right = nums2[nums2_start]
                nums2_start += 1
        #判断总长度是否为偶数；
        if (total & 1) == 0:
            return (left + right) / 2.0
        else:
            return right / 1.0

```

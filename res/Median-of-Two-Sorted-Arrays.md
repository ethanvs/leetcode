# Median of Two Sorted Arrays

### 原题

There are two sorted arrays nums1 and nums2 of size m and n respectively.

Find the median of the two sorted arrays. The overall run time complexity should be O(log (m+n)).

#### Example 1:

    nums1 = [1, 3]
    nums2 = [2]

    The median is 2.0
    
#### Example 2:

    nums1 = [1, 2]
    nums2 = [3, 4]

    The median is (2 + 3)/2 = 2.5

### 翻译

有两个大小为m和n的排序数组nums1和nums2。

找到两个排序数组的中位数。整体运行时间复杂度应该是O（log（m + n））。


```javascript

var findMedianSortedArrays = function(nums1, nums2) {
    var arr = nums1.concat(nums2);
    arr = arr.sort(function(a,b){
        return a-b;
    });
    if (arr.length %2 === 0 && arr.length > 0) {
        var startInx = arr.length/2 - 1;
        var endInx = arr.length/2;
        return (arr[startInx] + arr[endInx])/2;
    } else {
        var inx = Math.floor(arr.length/2);
        return arr[inx];
    }
};

```

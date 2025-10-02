
✅ **Status:** Accepted  
⏱ **Runtime:** 0 ms  
💾 **Memory Usage:** 41.9 MB  
📊 **Test Cases Passed:** 89 / 89  

---

## 📌 Problem Statement
> Given an array nums with n objects colored red, white, or blue, sort them in-place so that objects of the same color are adjacent, with the colors in the order red, white, and blue.

We will use the integers 0, 1, and 2 to represent the color red, white, and blue, respectively.

---

## 💡 Approach
- Implemented the **Dutch National Flag Algorithm**.  
- Used three pointers (`low`, `mid`, `high`) to sort in-place.  
- Time Complexity: **O(n)**  
- Space Complexity: **O(1)**  

---

## 📝 Code (Java)
```java
class Solution {
    public void sortColors(int[] nums) {
        int low = 0, mid = 0, high = nums.length - 1;

        while (mid <= high) {
            if (nums[mid] == 0) {
                int temp = nums[low];
                nums[low] = nums[mid];
                nums[mid] = temp;
                low++;
                mid++;
            } else if (nums[mid] == 1) {
                mid++;
            } else {
                int temp = nums[mid];
                nums[mid] = nums[high];
                nums[high] = temp;
                high--;
            }
        }
    }
}

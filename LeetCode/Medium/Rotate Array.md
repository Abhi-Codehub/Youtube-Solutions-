# Java Code 
## LeetCode - 189 
## Using an Extra Array
```
import java.util.Arrays;

public class RotateArray {
    public static void main(String[] args) {
        int[] nums1 = {1, 2, 3, 4, 5, 6, 7};
        int k1 = 3;
        rotate(nums1, k1);
        System.out.println("Rotated Array 1: " + Arrays.toString(nums1));

        int[] nums2 = {-1, -100, 3, 99};
        int k2 = 2;
        rotate(nums2, k2);
        System.out.println("Rotated Array 2: " + Arrays.toString(nums2));
    }

    public static void rotate(int[] nums, int k) {
        int n = nums.length;
        // Handle edge cases where k might be greater than n
        k %= n;
        // Create an extra array to store rotated elements
        int[] rotatedArray = new int[n];
        // Copy the elements to the rotated array
        for (int i = 0; i < n; i++) {
            rotatedArray[(i + k) % n] = nums[i];
        }
        // Copy elements back to the original array
        System.arraycopy(rotatedArray, 0, nums, 0, n);
    }
}
```
## Using Reverse function 
```
class Solution {

    public static void reverse (int[] nums, int start, int end){
        while(start < end){
            int temp = nums[start];
            nums[start] = nums[end];
            nums[end] = temp;
            start++;
            end--;
        }
    }
    public void rotate(int[] nums, int k) {
        k %= nums.length;
        reverse (nums, 0, nums.length -1 );
        reverse (nums, 0, k-1);
        reverse (nums, k, nums.length-1);
    }
}
```

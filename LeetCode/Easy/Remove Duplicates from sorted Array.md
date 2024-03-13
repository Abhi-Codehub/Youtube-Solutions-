# Java Solution 
## LeetCode 26
## Using HashSet
```
import java.util.Arrays;
import java.util.HashSet;

public class RemoveDuplicatesSortedArray {
    public static void main(String[] args) {
        int[] sortedArray = {1, 1, 2, 2, 3, 4, 5, 5, 5, 6};
        int[] uniqueArray = removeDuplicates(sortedArray);
        System.out.println("Original Array: " + Arrays.toString(sortedArray));
        System.out.println("Array after removing duplicates: " + Arrays.toString(uniqueArray));
    }

    public static int[] removeDuplicates(int[] nums) {
        HashSet<Integer> set = new HashSet<>();
        int index = 0;
        for (int num : nums) {
            // Add the element to the set if it's not already present
            if (!set.contains(num)) {
                set.add(num);
                // Overwrite the current index in the array with the unique element
                nums[index++] = num;
            }
        }
        // Return a new array containing only the unique elements
        return Arrays.copyOf(nums, index);
    }
}
```

## Using 2 Pointers 
```
class Solution {
    public int removeDuplicates(int[] nums) {

        int j = 0;
        for(int i = 0; i<nums.length; i++){
            if(nums[j] != nums[i]){
                nums[++j] = nums[i];
            }
        }
        return j+1;
    }
}
```

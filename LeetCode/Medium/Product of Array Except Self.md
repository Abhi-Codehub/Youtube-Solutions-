# Java Solution   
## Brute Force (Using 2 for Loops)
```
public class ProductExceptSelf {
    public static int[] productExceptSelf(int[] nums) {
        int n = nums.length;
        int[] result = new int[n];
        
        for (int i = 0; i < n; i++) {
            int product = 1;
            for (int j = 0; j < n; j++) {
                if (j != i) {
                    product *= nums[j];
                }
            }
            result[i] = product;
        } 
        return result;
    }
}
```
## Using Extra Space Array
```
class Solution {
    public int[] productExceptSelf(int[] nums) {
        
        int n = nums.length;
        int product = 1;

        int [] result = new int[n];
        int [] left_pro = new int[n];
        int [] right_pro = new int[n];

        right_pro[n-1] = 1;
        left_pro[0] = 1;

        for(int i = 1; i<n; i++){
            left_pro[i] = nums[i-1] * left_pro[i-1];
        }

        for(int i = n-2; i>=0; i--){
            right_pro[i] = nums[i+1] * right_pro[i+1];
        }
        for(int i = 0; i < n; i++){
        result[i] = left_pro[i] * right_pro[i];
        }
        return result;
    }
}
```

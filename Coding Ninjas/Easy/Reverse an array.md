# Java Code: 
## Reverse an array using an extra array:
```
import java.util.Arrays;

public class ReverseArrayUsingExtraArray {
    public static void main(String[] args) {
        int[] originalArray = {1, 2, 3, 4, 5};
        int[] reversedArray = reverseArray(originalArray);
        System.out.println("Original Array: " + Arrays.toString(originalArray));
        System.out.println("Reversed Array: " + Arrays.toString(reversedArray));
    }

    public static int[] reverseArray(int[] arr) {
        int[] reversedArray = new int[arr.length];
        for (int i = 0; i < arr.length; i++) {
            reversedArray[i] = arr[arr.length - 1 - i];
        }
        return reversedArray;
    }
}
```
## Reverse an array using a stack:
```
import java.util.Stack;

public class ReverseArrayUsingStack {
    public static void main(String[] args) {
        int[] originalArray = {1, 2, 3, 4, 5};
        int[] reversedArray = reverseArray(originalArray);
        System.out.println("Original Array: " + Arrays.toString(originalArray));
        System.out.println("Reversed Array: " + Arrays.toString(reversedArray));
    }

    public static int[] reverseArray(int[] arr) {
        Stack<Integer> stack = new Stack<>();
        for (int num : arr) {
            stack.push(num);
        }
        int[] reversedArray = new int[arr.length];
        int i = 0;
        while (!stack.isEmpty()) {
            reversedArray[i++] = stack.pop();
        }
        return reversedArray;
    }
}
```
## Reverse an array using pointers:
```
import java.util.Arrays;

public class ReverseArrayUsingPointers {
    public static void main(String[] args) {
        int[] originalArray = {1, 2, 3, 4, 5};
        reverseArray(originalArray);
        System.out.println("Reversed Array: " + Arrays.toString(originalArray));
    }

    public static void reverseArray(int[] arr) {
        int start = 0;
        int end = arr.length - 1;
        while (start < end) {
            // Swap elements at start and end indices
            int temp = arr[start];
            arr[start] = arr[end];
            arr[end] = temp;
            // Move pointers inward
            start++;
            end--;
        }
    }
}
```


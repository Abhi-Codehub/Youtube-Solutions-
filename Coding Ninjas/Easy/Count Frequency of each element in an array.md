# Java Code
## Using HashMap
```
import java.util.HashMap;

public class FrequencyCounter {
    public static void main(String[] args) {
        int[] arr = {1, 2, 3, 4, 5, 1, 2, 3, 1, 2, 3};
        HashMap<Integer, Integer> frequencyMap = countFrequency(arr);
        
        // Printing frequencies
        System.out.println("Element : Frequency");
        for (int key : frequencyMap.keySet()) {
            System.out.println(key + " : " + frequencyMap.get(key));
        }
    }

    public static HashMap<Integer, Integer> countFrequency(int[] arr) {
        HashMap<Integer, Integer> frequencyMap = new HashMap<>();
        // Traverse the array
        for (int num : arr) {
            // If the number is already present in the map, increment its count
            // Otherwise, add it to the map with count as 1
            frequencyMap.put(num, frequencyMap.getOrDefault(num, 0) + 1);
        }
        return frequencyMap;
    }
}

```

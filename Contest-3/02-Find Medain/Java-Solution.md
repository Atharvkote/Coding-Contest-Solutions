### **Approach**
1. **Sort the array** using `Arrays.sort()`, which has a time complexity of **O(n log n)**.
2. **Find the middle index** using `n / 2`, since `n` is always odd.
3. **Return the middle element** as the median.

---

### **Java Code**
```java
import java.util.*;

public class MedianFinder {
    public static int findMedian(int[] arr) {
        Arrays.sort(arr); // Step 1: Sort the array (O(n log n))
        int midIndex = arr.length / 2; // Step 2: Find middle index
        return arr[midIndex]; // Step 3: Return median
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int n = scanner.nextInt(); // Input size of the array (must be odd)
        int[] arr = new int[n];

        for (int i = 0; i < n; i++) {
            arr[i] = scanner.nextInt(); // Input array elements
        }

        System.out.println(findMedian(arr)); // Output median
        scanner.close();
    }
}
```

---

### **Sample Input**
```
7
0 1 2 4 6 5 3
```

### **Sorted Array**
```
[0, 1, 2, 3, 4, 5, 6]
```

### **Sample Output**
```
3
```

---

### **Time Complexity**
- **Sorting:** `O(n log n)` (Using `Arrays.sort()` which is a Dual-Pivot Quicksort).
- **Finding the median:** `O(1)` (Accessing the middle element).
- **Overall Complexity:** **O(n log n)**.

This solution efficiently finds the median for large inputs up to **1,000,000** elements, as per the problem constraints. 🚀
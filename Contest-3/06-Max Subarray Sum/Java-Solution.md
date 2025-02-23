
### **Approach**
1. Use **prefix sums** to track cumulative sums.
2. Use a **TreeSet** to efficiently find the smallest prefix sum greater than the current sum modulo \( m \).
3. Iterate through the array while maintaining the maximum possible sum modulo \( m \).

---

### **Optimized Algorithm**
- Initialize `maxModSum = 0` to store the maximum sum found.
- Use a **prefix sum** to compute cumulative sums of the array.
- Store previous prefix sums in a **TreeSet** to efficiently find the next higher prefix sum.
- Use the property:  
  \[
  \text{maxModSum} = \max(\text{currentPrefix} \% m, (\text{currentPrefix} - \text{smallestGreater}) \% m)
  \]
  where `smallestGreater` is the smallest prefix sum in the TreeSet that is **greater than** the current prefix sum.

---

### **Efficient Java Code**
```java
import java.util.*;

public class MaximumSubarrayModuloM {
    public static long maximumSum(long[] arr, long m) {
        TreeSet<Long> prefixSet = new TreeSet<>();
        long maxModSum = 0, prefixSum = 0;

        for (long num : arr) {
            prefixSum = (prefixSum + num) % m;
            maxModSum = Math.max(maxModSum, prefixSum);

            Long higher = prefixSet.higher(prefixSum);
            if (higher != null) {
                maxModSum = Math.max(maxModSum, (prefixSum - higher + m) % m);
            }

            prefixSet.add(prefixSum);
        }

        return maxModSum;
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int queries = scanner.nextInt();

        while (queries-- > 0) {
            int n = scanner.nextInt();
            long m = scanner.nextLong();
            long[] arr = new long[n];

            for (int i = 0; i < n; i++) {
                arr[i] = scanner.nextLong();
            }

            System.out.println(maximumSum(arr, m));
        }

        scanner.close();
    }
}
```

---

### **Explanation**
1. **Prefix Sum Calculation:**
   - Compute prefix sum modulo \( m \).
   - Track the **max modulo sum** seen so far.

2. **TreeSet for Efficient Lookup:**
   - Insert each prefix sum into `TreeSet`.
   - Use `.higher()` to find the smallest prefix sum greater than the current sum.
   - If found, update `maxModSum` using:  
     \[
     (\text{currentPrefix} - \text{higher} + m) \% m
     \]

3. **Final Result:**  
   - Return the **maximum** of all possible subarray sums modulo \( m \).

---

### **Complexity Analysis**
- **Iterate through array:** \( O(n) \)
- **TreeSet operations (insert + higher lookup):** \( O(\log n) \)
- **Total complexity:** \( O(n \log n) \), which is efficient for large inputs.

---

### **Example Walkthrough**
#### **Input**
```
1
5 7
3 3 9 9 5
```
#### **Subarrays & Modulo Calculation**
| Subarray        | Sum | Sum % 7 |
|---------------|-----|-------|
| 3            | 3   | 3     |
| 3,3         | 6   | 6     |
| 3,3,9       | 15  | 1     |
| 3,3,9,9     | 24  | 3     |
| 3,3,9,9,5   | 29  | 1     |
| 3,9         | 12  | 5     |
| 3,9,9       | 21  | 0     |
| 3,9,9,5     | 26  | 5     |
| 9           | 9   | 2     |
| 9,9         | 18  | 4     |
| 9,9,5       | 23  | 2     |
| 9,5         | 14  | 0     |
| 5           | 5   | 5     |

#### **Output**
```
6
```
✅ The maximum subarray sum modulo \( 7 \) is **6**.

---

### **Why This Works?**
- **Brute force:** \( O(n^2) \) (too slow).
- **Optimized prefix sum with TreeSet:** \( O(n \log n) \) (efficient).
- **Handles large \( m \) (up to \( 10^{15} \)) well.**

Would you like me to explain any part further? 😊
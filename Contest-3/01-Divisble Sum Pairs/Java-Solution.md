### **Optimized Approach (Using Frequency Array)**
Instead of checking each pair explicitly (**O(n²)**), we use **modulo frequency counting**:

1. **Use an array `freq[]`** to store the count of elements with the same remainder when divided by `k`.
2. **Iterate through the array**:
   - Compute the remainder `rem = ar[i] % k`.
   - Find the complementary remainder `(k - rem) % k` that forms a valid pair.
   - Use `freq` to count such pairs efficiently.
   - Update `freq[rem]` for future elements.

This **reduces the time complexity from \(O(n^2)\) to \(O(n)\)**.

---

### **Java Code:**
```java
import java.util.Scanner;

public class DivisibleSumPairs {
    public static int divisibleSumPairs(int n, int k, int[] ar) {
        int[] freq = new int[k]; // Frequency array for remainders
        int count = 0;

        for (int i = 0; i < n; i++) {
            int rem = ar[i] % k; // Compute remainder
            int complement = (k - rem) % k; // Complement remainder
            
            count += freq[complement]; // Add valid pairs found so far
            
            freq[rem]++; // Store current remainder frequency
        }

        return count;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        // Input size of array and divisor
        int n = sc.nextInt();
        int k = sc.nextInt();

        int[] ar = new int[n];
        for (int i = 0; i < n; i++) {
            ar[i] = sc.nextInt();
        }

        sc.close();

        // Function Call
        System.out.println(divisibleSumPairs(n, k, ar));
    }
}
```

---

### **Sample Input & Output:**
#### **Input:**
```
6 3
1 3 2 6 1 2
```
#### **Output:**
```
5
```

---

### **Explanation:**
For `k = 3`, the valid pairs `(i, j)` are:
- `(0,2) → 1 + 2 = 3`
- `(0,5) → 1 + 2 = 3`
- `(1,3) → 3 + 6 = 9`
- `(2,4) → 2 + 1 = 3`
- `(4,5) → 1 + 2 = 3`

Thus, the output is `5`.

---

### **Time Complexity Analysis:**
- **Optimized Approach:** **\(O(n)\)**  
  - Each element is processed **once**.
  - Using an array for **constant-time frequency lookup**.

- **Brute Force Approach:** **\(O(n^2)\)**  
  - Iterates through all possible pairs.

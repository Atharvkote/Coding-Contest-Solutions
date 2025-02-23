Here are **two approaches** to solve the **Maximum Subarray Sum Modulo m** problem:  

1️⃣ **Brute Force Approach** – Checks all possible subarrays (O(n²))  
2️⃣ **Kadane's Algorithm with Modulo** – Optimized (O(n))  

Both approaches **do not use TreeSet**.

---

## **Approach 1: Brute Force (O(n²))**
We iterate over all possible subarrays, compute their sum modulo \( m \), and keep track of the maximum result.  

### **Java Code**
```java
import java.util.*;

public class MaximumSubarrayBruteForce {
    public static long maximumSumBruteForce(long[] arr, long m) {
        long maxModSum = 0;
        
        for (int i = 0; i < arr.length; i++) {
            long sum = 0;
            for (int j = i; j < arr.length; j++) {
                sum = (sum + arr[j]) % m;  // Compute sum modulo m
                maxModSum = Math.max(maxModSum, sum);
            }
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

            System.out.println(maximumSumBruteForce(arr, m));
        }

        scanner.close();
    }
}
```

### **Time Complexity:**  
- **O(n²)** because of the two nested loops.  
- **Best for small constraints (n ≤ 1000).**  

---

## **Approach 2: Kadane’s Algorithm with Modulo (O(n))**
Instead of iterating over all subarrays, we use **Kadane’s Algorithm** to maintain a running sum while applying modulo.  

### **Java Code**
```java
import java.util.*;

public class MaximumSubarrayKadane {
    public static long maximumSumKadane(long[] arr, long m) {
        long maxModSum = 0;
        long currentSum = 0;
        
        for (long num : arr) {
            currentSum = (currentSum + num) % m;
            maxModSum = Math.max(maxModSum, currentSum);
            
            if (currentSum < 0) {
                currentSum = 0;  // Reset subarray if needed
            }
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

            System.out.println(maximumSumKadane(arr, m));
        }

        scanner.close();
    }
}
```

### **Time Complexity:**  
- **O(n)** – Much faster than brute force.  
- **Works well for large inputs (n ≤ 10⁵).**  

---

## **Key Differences**
| Approach  | Complexity  | When to Use?  | Pros  | Cons  |
|-----------|-------------|--------------|-------|------|
| **Brute Force** | O(n²) | Small arrays (n ≤ 1000) | Simple & intuitive | Slow for large n |
| **Kadane’s Algorithm** | O(n) | Large arrays (n ≤ 100,000) | Fastest approach | Doesn't track all subarrays |

---

### **Example Run**
#### **Input**
```
1
5 7
3 3 9 9 5
```
#### **Output (Both Approaches)**
```
6
```

---

## **Conclusion**
- **If n is small** → **Use Brute Force (O(n²))**  
- **If n is large** → **Use Kadane's Algorithm (O(n))**  

Would you like me to explain another optimization? 🚀
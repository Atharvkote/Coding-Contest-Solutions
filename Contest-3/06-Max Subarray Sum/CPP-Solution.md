Here are the **two approaches** in **C++** to find the maximum subarray sum modulo \( m \) **without using TreeSet**.

---

## **Approach 1: Brute Force (O(n²))**
We generate all possible subarrays, compute their sum modulo \( m \), and keep track of the maximum result.

### **C++ Code**
```cpp
#include <iostream>
#include <vector>
using namespace std;

long maximumSumBruteForce(vector<long> &arr, long m) {
    long maxModSum = 0;

    for (int i = 0; i < arr.size(); i++) {
        long sum = 0;
        for (int j = i; j < arr.size(); j++) {
            sum = (sum + arr[j]) % m; // Compute sum modulo m
            maxModSum = max(maxModSum, sum);
        }
    }

    return maxModSum;
}

int main() {
    int queries;
    cin >> queries;

    while (queries--) {
        int n;
        long m;
        cin >> n >> m;
        vector<long> arr(n);

        for (int i = 0; i < n; i++) {
            cin >> arr[i];
        }

        cout << maximumSumBruteForce(arr, m) << endl;
    }

    return 0;
}
```

### **Time Complexity:**
- **O(n²)** due to two nested loops.
- Works well for **small constraints** (n ≤ 1000).

---

## **Approach 2: Kadane’s Algorithm with Modulo (O(n))**
Instead of iterating over all subarrays, we use **Kadane’s Algorithm** to maintain a running sum while applying modulo.

### **C++ Code**
```cpp
#include <iostream>
#include <vector>
using namespace std;

long maximumSumKadane(vector<long> &arr, long m) {
    long maxModSum = 0;
    long currentSum = 0;

    for (long num : arr) {
        currentSum = (currentSum + num) % m;
        maxModSum = max(maxModSum, currentSum);

        if (currentSum < 0) {
            currentSum = 0;  // Reset subarray if needed
        }
    }

    return maxModSum;
}

int main() {
    int queries;
    cin >> queries;

    while (queries--) {
        int n;
        long m;
        cin >> n >> m;
        vector<long> arr(n);

        for (int i = 0; i < n; i++) {
            cin >> arr[i];
        }

        cout << maximumSumKadane(arr, m) << endl;
    }

    return 0;
}
```

### **Time Complexity:**
- **O(n)** → much faster than brute force.
- Works well for **large inputs (n ≤ 100,000).**

---

## **Key Differences**
| Approach | Complexity | When to Use? | Pros | Cons |
|----------|-----------|--------------|------|------|
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
- **Use Brute Force** for **small inputs** (O(n²)).
- **Use Kadane's Algorithm** for **large inputs** (O(n)).

Would you like further optimizations? 🚀
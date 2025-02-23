### **Approach:**
1. **Sort the array** in ascending order using `std::sort()`. This has a time complexity of **O(n log n)**.
2. **Find the middle index** using `n / 2`, since `n` is always odd.
3. **Return the middle element** as the median.

---

### **C++ Code:**
```cpp
#include <bits/stdc++.h>
using namespace std;

int findMedian(vector<int>& arr) {
    sort(arr.begin(), arr.end()); // Step 1: Sort the array
    int mid_index = arr.size() / 2; // Step 2: Find middle index
    return arr[mid_index]; // Step 3: Return median
}

int main() {
    int n;
    cin >> n; // Input size of array
    vector<int> arr(n);
    
    for (int i = 0; i < n; i++) {
        cin >> arr[i]; // Input array elements
    }
    
    cout << findMedian(arr) << endl; // Output median
    return 0;
}
```

---

### **Sample Input:**
```
7
0 1 2 4 6 5 3
```

### **Sorted Array:**
```
[0, 1, 2, 3, 4, 5, 6]
```

### **Sample Output:**
```
3
```

---

### **Time Complexity:**
- **Sorting:** `O(n log n)` (Using `std::sort()` which is implemented as Introsort).
- **Finding the median:** `O(1)` (Accessing an element at the middle index).
- **Overall Complexity:** **O(n log n)**.

This approach efficiently finds the median for large input sizes up to **1,000,000** as per the problem constraints. 🚀
### **Problem Statement: Lowest Common Ancestor in a Binary Search Tree**  

You are given a pointer to the root of a **Binary Search Tree (BST)** and two values **v1** and **v2**. You need to return the **lowest common ancestor (LCA)** of **v1** and **v2** in the BST.  

In the diagram below, the **lowest common ancestor** of the nodes **4** and **5** is the node **3**. Node **3** is the lowest node that has both **4** and **5** as descendants.  

### **Function Description**  
Complete the function **`findLCA`** in the editor below. It should return a pointer to the **lowest common ancestor node** of the two values given.  

**`findLCA`** has the following parameters:  
- `root`: a pointer to the root node of a Binary Search Tree  
- `v1`: a node data value  
- `v2`: a node data value  

### **Input Format**  
- The first line contains an integer, **n**, the number of nodes in the tree.  
- The second line contains **n** space-separated integers representing the node data values.  
- The third line contains two space-separated integers, **v1** and **v2**.  

> **Note:** To use the test data, you will have to create the **Binary Search Tree (BST)** yourself. However, on the platform, the tree will be created for you.  

### **Constraints**  
- \( 1 \leq n, \text{node data} \leq 25 \)  
- \( 1 \leq v1, v2 \leq 25 \)  
- The tree will contain nodes with data equal to **v1** and **v2**.  

### **Output Format**  
Return a **pointer to the node** that is the **lowest common ancestor** of **v1** and **v2**.  

---

### **Sample Input**
```
6
4 2 3 1 7 6
1 3
```
### **Sample Output**
```
LCA: 2
```

---

### **Explanation**  
The **Binary Search Tree (BST)** is structured as follows:  

```
        4
       / \
      2   7
     / \  /
    1   3 6
```
- The **LCA** of `1` and `3` is **2**, as it's the **lowest node** that has both as descendants.  

Let me know if you need any modifications! 🚀
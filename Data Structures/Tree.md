
- A tree is a hierarchical data structure that consists of nodes connected by edges

- A tree is a non-linear data structure, compared to arrays, linked lists, stacks and queues which are linear data structures.

- In linear data structures, the time required to search is proportional to the size of the data set

- Trees however, owing to the nonlinear nature allow quicker and easier access to the data

- A tree will not contain any loops or cycles.
- ![[Pasted image 20250901230247.png]]

### 🌳 **Tree Basics**

A **tree** is a hierarchical data structure consisting of nodes.

- The **topmost node** is called the **root**.
    
- Nodes connected below are called **children**, and a node with children is a **parent**.
    
- Nodes with no children are called **leaves**.
    

---

### 🔹 1. **Degree of a Node / Tree**

- **Degree of a Node** → The number of **direct children** of that node.  
    Example: If a node has 3 children, its degree is 3.
    
- **Degree of a Tree** → The maximum degree of all nodes in the tree.
    

---

### 🔹 2. **Depth of a Node**

- The number of **edges from the root to that node**.
    
- Root node has **depth 0**.
    
- Example: If a node is 3 edges away from the root, its depth is 3.
    

---

### 🔹 3. **Height**

- **Height of a Node** → The number of edges on the **longest path** from that node down to a leaf.
    
- **Height of a Tree** → Height of the root node (longest path from root to any leaf).
    
- A leaf node has height **0**.
    

---

### 📌 Quick Example

        `A (root)        / \       B   C      / \     D   E`

- **Degree of A = 2** (children: B, C)
    
- **Degree of B = 2** (children: D, E)
    
- **Degree of C = 0**, **Degree of D = 0**, **Degree of E = 0**
    
- **Degree of Tree = 2** (max of all degrees)
    
- **Depth(A) = 0**, **Depth(B) = 1**, **Depth(D) = 2**
    
- **Height(D) = 0**, **Height(B) = 1**, **Height(A) = 2**
    
- **Height of Tree = 2**
    

---

👉 A good way to remember:

- **Degree → children count**
    
- **Depth → distance from root**
    
- **Height → distance to deepest leaf**

---
**Delete Element from the Binary Tree**

1. Scenario 1: Node to be deleted is a *leaf Node*.
2. Scenario 2: Node to be deleted has *ONE CHILD NODE*
3. Scenario 3: Node to be deleted has *TWO CHILD NODE* --> 

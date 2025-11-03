<div align="center">

# **Appendix & Exercises – Parallel Programming in Data Structures with OpenMP**

</div>

**Author:** Dr. Rutal Mahajan  
**Course:** Data Structures & Algorithms (with Parallel Programming using OpenMP)  
**Term:** Fall 2024  
**Affiliation:** Utica University, New York, USA  

---

## 1️⃣ Classroom Code Samples

These examples were demonstrated in class to explain parallelization concepts alongside core DSA topics:

- **Parallel “Hello World”** [basic demonstration in classroom](https://www.onlinegdb.com/uPn335sXP) 
- **Parallelizing Loops in C++** [Link to the Code Here](https://www.onlinegdb.com/oRW7RhDWP) 
- **Sum of 1,000,000 Random Numbers** [Link to the Code Here](https://www.onlinegdb.com/1JKBPKm8I)
  The code writes the results in CSV files to analyze the time complexity of sequential code and parallel code.
  

---
Examples of assignments used in the Course for parallelization concepts along with data structures topics
## 2️⃣ Assignments

### 2.1 Parallel Loops with Arrays
- Introduce parallel loop concepts using arrays (example assignment on karastuba matrix algorithm of matrix multiplication)
  <img width="1013" height="534" alt="image" src="https://github.com/user-attachments/assets/8ca5d5cc-c16d-4fd6-b90b-dea3da40c050" />

### 2.2 Parallel Merge Sort

**Learning Objectives:**  
- Understand divide-and-conquer in sorting  
- Learn to parallelize recursive calls using OpenMP tasks  

**Problem Statement:**  
- Write a program to sort an array using Merge Sort  
- Parallelize recursive calls using OpenMP tasks  
- Compare sequential and parallel performance  

**Sequential & Parallel Implementation:**  
- Sequential version – standard recursive approach  
- Parallel version – use OpenMP directives:  
```cpp
#pragma omp parallel
#pragma omp single
#pragma omp sections
```
**Sequential Code Template (C++)**
<img width="923" height="623" alt="image" src="https://github.com/user-attachments/assets/97774d0a-3c7b-4a7a-bd39-403cf7460bb5" />
You are required to implement the Merge Sort algorithm in C++ in two versions:
1.	A sequential version, using the standard recursive approach.
2.	A parallel version, where the recursive calls are parallelized using OpenMP
you should use above mentioned directives to parallelize the two recursive calls to mergeSort.


### 2.3 Comparing Sorting Algorithms
- Compare serial and parallel versions for best, worst, and average cases on different input sizes
- [Sample Solution Code](https://onlinegdb.com/Ge3T7VDyo)

### 2.4 Linear Search on Large Dataset
- Implement sequential and parallel search  

### 2.5 Conceptual Activity – Reasoning About Concurrent Data Structures
**Title:** _What Could Go Wrong? – Stack & Queue Operations  _

**Objective:**  
- Introduce conceptual challenges of multiple threads accessing the same data structure  

**Scenarios:**  
1. Two `pop()` operations on a stack simultaneously  
2. One `enqueue()` and one `dequeue()` on a queue simultaneously  
3. Stack used as shared undo history
   
**Scenario 1: Two pop() Operations on a Stack**

Initial stack: [10, 20, 30]

Thread A and Thread B both try to pop().

**Guiding Questions:**
1. What might happen if both read the top as 30 and try to pop it?
2. What value will remain? Will one pop be "lost"?

**Scenario 2: One enqueue() and One dequeue() on a Queue**

Initial queue: [A, B, C]
Thread A enqueues D, Thread B dequeues an item.

**Guiding Questions:**
1. Could they interfere with each other's read/write pointers?
2. What might go wrong with the front/back indicators?

**Scenario 3: Stack Used as Shared Undo History**

Imagine an undo stack shared by multiple tabs in a text editor. What could go wrong if two users press undo at the same time?

**Expected Outcome for Instructor:** Students should be able to:

•	Present simulated operation sequences.
•	Identify problems (e.g., duplicated/removal conflict, skipped values).
•	Gain an intuitive grasp that correct sequencing matters when sharing structures.

**Instructor Notes:**

•	This assignment does not require threads, synchronization, or parallel code.
•	It is a reasoning-based activity designed to:
  o	Foster awareness of real-world complexity.
  o	Provide a segue into why thread safety is important.
  o	Encourage discussion about correctness and state consistency, even in a sequential mindset.

**Optional Extension (non-assessed):**

•	Share logs or visuals from actual concurrent code on OnlineGDB to show real anomalies, just for curiosity.


### 2.6 BFS, Stack, Queue Assignments
- Implement BFS, Stack, Queue operations and explore parallelization opportunities  

---

## 3️⃣ Project Guidelines & Rubrics

**Objective:**  
- Solve a real-world problem using DSA + OpenMP concepts  

**Guidelines:**  
1. Identify a real-time application using course data structures/algorithms  
2. Choose algorithmic technique (divide & conquer, graph/tree traversal, searching/sorting)  
3. Identify portions for parallelization with OpenMP  
4. Implement & document solution in C++  
5. Test sequential vs parallel execution and report findings  

**Rubrics:**

| Criteria | Excellent (10) | Good (7–9) | Needs Improvement (4–6) | Poor (1–3) |
|----------|----------------|------------|-------------------------|------------|
| Dataset Selection | Highly relevant, aligns perfectly | Relevant, minor misalignment | Generic, less relevant | No dataset or irrelevant |
| Problem Definition | Real-world, highly relevant | Moderately relevant | Generic or lacks real-world connection | Poorly defined |
| Algorithm Design | Efficient & innovative | Appropriate, minor inefficiencies | Basic, less relevant | Missing or incorrect |
| Implementation (C++) | Well-structured, modular, documented | Functional, minor issues | Runs with errors, poor readability | Incomplete, non-functional |
| Parallel Programming | Highly effective & optimal | Implemented with minor inefficiencies | Limited improvement | Missing or incorrect |
| Testing & Results | Thorough testing & comparison | Moderate testing, some comparison | Minimal analysis | Incomplete |
| Documentation & Reporting | Comprehensive, clear explanations | Adequate documentation | Limited, unclear | Minimal or none |

---

**Tips for Students:**  
- All exercises combine DSA concepts with basic OpenMP parallel programming  
- Use OnlineGDB or local compiler (`g++ -fopenmp`) for testing  



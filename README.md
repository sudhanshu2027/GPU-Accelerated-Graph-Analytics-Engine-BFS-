# GPU-Accelerated Parallel BFS 

A high-performance, asynchronous parallel Breadth-First Search (BFS) engine built in CUDA. This project traverses large-scale synthetic directed graphs utilizing the Compressed Sparse Row (CSR) data format, a standard in high-performance graph analytics.

## 🚀 Features & Optimizations
* **CSR Format Integration:** Efficiently maps sparse graph topologies into contiguous memory blocks for optimized GPU memory access.
* **Level-Synchronized Frontier Expansion:** Utilizes a vertex-centric approach to expand the search frontier in parallel across discrete graph levels.
* **Data Race Mitigation:** Implements warp-level atomic instructions (`atomicCAS`) to safely manage concurrent updates to neighboring vertices by multiple threads.
* **CPU Verification:** Automatically verifies GPU traversal distances against a sequential CPU BFS implementation to ensure algorithmic correctness.

##  Performance Benchmarks
Tested on a synthetic uniform out-degree directed graph containing **1,000,000 vertices** and **16,000,000 edges**.

* **Traversal Levels:** 1,064 
* **Execution Time:** 56.17 ms
* **Throughput:** **284.84 MTEPS** (Million Traversed Edges Per Second)
* **Validation:** 100% match with sequential CPU baseline.





# combinational_depth
Predicting combinational depth of RTL modules using GNN

Combinational depth prediction in RTL circuits is important for catching possible timing violations.
This project seeks to:

Translate RTL code into a graph form.

Trained a Graph Neural Network (GNN) for predicting combinational depth.

Employed the OpenABC-D dataset and rtl_timing_dataset as training data.
**Dataset**
1.## Dataset Download
The OpenABC-D dataset can be downloaded from [(https://drive.google.com/drive/folders/15UhMvJZHTl7cOC9G7dDcaNcpDvAOg4UE?usp=drive_link)]
2.rtl_timing_dataset can be downloaded from [(https://drive.google.com/drive/folders/1q_S_qpzXi4-SJzSCS5rnog1MMF9YUOVR?usp=drive_link)]


**proof of correctness**

The following guidelines are used in our method to accurately calculate the combinational depth:

RTL circuits are represented graphically as **Directed Acyclic Graphs (DAGs),** in which dependencies are represented by edges and logic gates by nodes.
  
**Topological Sorting:** - To prevent cycles and guarantee precise depth computation,  made sure that every node is handled in a valid order.
  
**Longest Path Algorithm:** - **Dynamic Programming (DP)** is used to calculate the combinational depth, which is the longest path in the DAG.
  
**GNN Validation:** - The trained GNN successfully generalises combinational depth predictions and picks up structural patterns in the RTL graph.
## **🔹 Complexity Analysis**

         

**Parsing RTL Code** : (O(N))             -->  Parsing is done linearly. 
**Graph Construction** : (O(V + E))        --> Each node and edge is processed once. 
**Topological Sorting** : (O(V + E))       --> Uses Kahn’s algorithm or DFS-based approach. 
**Longest Path Calculation** : (O(V + E))  --> Dynamic programming on DAG. 
**GNN Training** : (O(E *F))         --> F is the feature size per node. 
**GNN Inference** : (O(E))                 --> Each edge is used in forward propagation. 

### **Overall Complexity:**  
- The overall pipeline runs in **linear time** with respect to the number of gates and interconnections.
- The GNN model is efficient and scalable for large RTL designs.


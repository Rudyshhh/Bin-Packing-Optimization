# Bin-Packing-Optimization
This project addresses the rectangular bin-packing problem, where the goal is to optimally arrange a set of rectangles within a fixed bin while adhering to predefined constraints using graph-based techniques, specifically Graph Neural Networks (GCNs).


## Rectangle Placement Algorithm - Iterations Overview

This project aims to solve the bin packing problem by optimizing the placement of 9 rectangles within a bin of width 80 and height 40. Over the course of multiple iterations, the algorithm has evolved from a simple rule-based approach to a sophisticated Graph Convolutional Network (GCN)-based solution. Below is an overview of each iteration and its key features.

---

## **First Iteration**

### Goal:
Develop a functional and straightforward placement algorithm capable of solving the problem while adhering to basic placement constraints.

### Features:
1. **Greedy, Rule-Based Placement**:
   - **Fixed Placement for Rectangles 1 and 2**: These rectangles were manually positioned at the top and bottom of the bin, respectively.
   - **Proximity-Based Placement for Rectangles 3, 4, 5, and 9**: Rectangles placed based on proximity to other rectangles.
   - **Priority on Critical Rectangles**: Focused on satisfying the placement of the key rectangles before others.

2. **Randomized Search for Remaining Rectangles**:
   - Random placement of remaining rectangles to avoid overlap.
   - No optimization of space usage, and the layout might include significant unused gaps.

3. **Constraint Satisfaction**:
   - Ensured that key placement constraints were respected.
   - Used manual checks for proximity and fixed placements.

4. **No Advanced Optimization**:
   - No optimization for space efficiency.
   - The approach was primarily focused on functionality rather than optimality.

### What We Aimed to Achieve:
- Develop a working prototype that met basic constraints.
- Generate a valid bin layout with no overlaps.
- Create a visual representation of the placement for future comparison.

### Relation to Later Iterations:
- This iteration served as a foundation for future iterations, focusing on basic functionality rather than optimization.
- Future iterations introduced optimization and constraint handling improvements.

---

## **Second Iteration**

### Goal:
Introduce Graph Convolutional Networks (GCNN) combined with Reinforcement Learning (RL) to enhance the rectangle placement process.

### Features:
1. **Use of Graph Convolutional Networks (GCNN)**:
   - The placement problem is treated as a graph, where each node represents a rectangle and edges represent relationships (proximity, etc.).
   - GCNN processes the graph to optimize the placement based on learned relationships.

2. **Reinforcement Learning for Optimization**:
   - The agent learns from its placements and receives rewards for favorable outcomes, like proximity adherence, space efficiency, and penalty for overlaps.
   - The reward system encourages space-efficient placement.

3. **Algorithm Breakdown**:
   - **Graph Construction**: Constraints are converted into a graph structure.
   - **GCNN Layers**: Two layers of graph convolutions allow the model to learn complex relationships.
   - **Training with Adam Optimizer**: The GCNN is trained to improve placement iteratively.

---

## **Third Iteration**

### Goal:
Refine the rectangle placement using Graph Convolutional Networks (GCN) for optimized placements while adhering to the constraints.

### Features:
1. **Graph-Based Problem Representation**:
   - Rectangles are nodes, and edges capture proximity relationships based on constraints.

2. **GCN Architecture**:
   - Two convolutional layers aggregate features from neighboring nodes.
   - Outputs optimized positions for rectangles while respecting constraints.

3. **Optimization Loop**:
   - The GCN is trained over multiple epochs, adjusting positions and resolving overlaps.

4. **Loss Function**:
   - The loss function aims to avoid overlap and ensure proximity constraints are respected.

5. **Training Process**:
   - Adam optimizer is used to adjust the model’s weights for better placements.

---

## **Fourth Iteration**

### Goal:
Refine optimization by keeping the fixed positions of Rectangles 1 and 2 unchanged during optimization.

### Changes in the Optimization Process:
1. **Fixed Positions for Rectangles 1 and 2**:
   - These rectangles are placed manually at the top and bottom and excluded from the optimization loop.
   - Optimization efforts focus on the remaining rectangles.

2. **GCN Optimization**:
   - The GCN model continues to adjust the other rectangles, optimizing space utilization while respecting proximity constraints.

---

## **Fifth Iteration**

### Goal:
Introduce more advanced optimization by refining the x and y coordinates of rectangles using a Graph Convolutional Network.

### Features:
1. **Graph Construction and Constraints Handling**:
   - Graph structure captures relationships between rectangles (proximity, fixed placements).
   - Ensures constraints are respected during optimization.

2. **Initial Rectangle Placement**:
   - Rectangles 1 and 2 are placed with fixed y-coordinates, leaving only the x-coordinates to be optimized.

3. **GCN for Optimization**:
   - GCN processes the feature matrix and optimizes rectangle placements over 5000 epochs.

4. **Overlap Check and Update**:
   - New placements are checked for overlap, and adjustments are made to achieve valid configurations.

5. **Loss Function**:
   - Focused on optimizing x-coordinates for fixed rectangles while avoiding overlap and respecting constraints.

6. **Results After Optimization**:
   - The GCN optimizes placements, improving space utilization and reducing overlap.
   - Rectangles 1 and 2 have their x-coordinates optimized, while maintaining their fixed y-positions.

---

## **Conclusion**

Each iteration of this project introduced key improvements to the rectangle placement algorithm. Starting from a simple rule-based approach in the first iteration, the algorithm gradually evolved to incorporate sophisticated machine learning techniques like GCNN and RL for optimization. These advancements have led to improved space utilization and better compliance with the placement constraints, providing a robust foundation for future iterations and enhancements.

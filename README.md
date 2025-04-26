# KMeans-Clustering-Manhattan
Python implementation of K-Means clustering using Manhattan distance with 2D grid visualization.
# 📊 K-Means Clustering with Manhattan Distance (Python)

Welcome to my Python implementation of a **modified K-Means clustering algorithm**!  
This project replaces the usual **Euclidean distance** with **Manhattan distance** for clustering and visualizes the result using a simple **text-based 2D grid**.

---

## 📌 Objective

To implement a K-Means clustering algorithm using **Manhattan distance** as the metric for assigning points to clusters, and display the final clustered data through a **console-based 2D grid visualization**.

---

## 📄 Description  

- 📌 Generate **100 random 2D Cartesian points** within a 21×21 grid.
- 📌 Select **10 random initial cluster centers**.
- 📌 Use **Manhattan distance** to assign each point to the nearest cluster.
- 📌 Update cluster centers by calculating the average position of their assigned points.
- 📌 Repeat the process until cluster centers no longer move.
- 📌 Visualize the final clusters in a **matrix grid format** using only Python’s `print()` function.

---

## 🚀 How to Run  

1. 📥 Clone the repository or download the `.py` file.
2. Open your terminal / command prompt.
3. Run the program:
   ```bash
   python filename.py
   

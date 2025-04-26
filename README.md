# KMeans-Clustering-Manhattan
Python implementation of K-Means clustering using Manhattan distance with 2D grid visualization.
# 📊 K-Means Clustering with Manhattan Distance (Python)

Welcome to my Python implementation of a **modified K-Means clustering algorithm**!  
This project replaces the usual **Euclidean distance** with **Manhattan distance** for clustering and visualizes the result using a simple **text-based 2D grid**.

---

## 📌 Objective

To implement a K-Means clustering algorithm using **Manhattan distance** as the metric for assigning points to clusters, and display the final clustered data through a **console-based 2D grid visualization**.

---code

```import random

POINT_COUNT = 100
CLUSTER_COUNT = 10
GRID_SIZE = 21

points = [(random.randint(0, GRID_SIZE - 1), random.randint(0, GRID_SIZE - 1)) for _ in range(POINT_COUNT)]
clusters = [(random.randint(0, GRID_SIZE - 1), random.randint(0, GRID_SIZE - 1)) for _ in range(CLUSTER_COUNT)]

def manhattan_distance(a, b):
    return abs(a[0] - b[0]) + abs(a[1] - b[1])

def k_means(points, clusters):
    while True:
        groups = {i: [] for i in range(len(clusters))}
        for p in points:
            nearest = min(range(len(clusters)), key=lambda i: manhattan_distance(p, clusters[i]))
            groups[nearest].append(p)

        updated_clusters = []
        for i in range(len(clusters)):
            if groups[i]:
                xs = [p[0] for p in groups[i]]
                ys = [p[1] for p in groups[i]]
                updated_clusters.append((round(sum(xs) / len(xs)), round(sum(ys) / len(ys))))
            else:
                updated_clusters.append(clusters[i])

        if updated_clusters == clusters:
            break
        clusters = updated_clusters

    return clusters, groups

final_clusters, final_cluster_points = k_means(points, clusters)

def visualize(points, clusters):
    grid = [['.' for _ in range(GRID_SIZE)] for _ in range(GRID_SIZE)]
    for x, y in points:
        grid[y][x] = '*'
    for x, y in clusters:
        grid[y][x] = 'C'
    for y in range(GRID_SIZE - 1, -1, -1):
        print(' '.join(grid[y]))

print("\nClustered Data Visualization:\n")
visualize(points, final_clusters)   

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
   

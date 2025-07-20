import matplotlib.pyplot as plt

# Data points for the graph
data = [
    {"label": "Huang 2023 Li–Zn 0.3 C", "x": 50, "y": 357, "color": "blue", "marker": "o"},
    {"label": "Huang 2023 Li–Sr 2 C", "x": 200, "y": 113, "color": "green", "marker": "s"},
    {"label": "Li@ZDDP 5 C", "x": 350, "y": 120, "color": "orange", "marker": "D"},
    {"label": "Chen 2021 Li@ZDDP 5 C", "x": 350, "y": 120, "color": "orange", "marker": "D"},
    {"label": "Cu@Cu3N 0.5 C", "x": 50, "y": 90, "color": "blue", "marker": "o"},
    {"label": "Cu@MLG 0.2 C", "x": 100, "y": 61, "color": "blue", "marker": "o"},
]

# Create the plot
plt.figure(figsize=(10, 6))
for point in data:
    plt.scatter(point["x"], point["y"], color=point["color"], marker=point["marker"], s=100)
    plt.text(point["x"] + 5, point["y"] + 2, point["label"], fontsize=9)

# Set axis labels and title
plt.xlabel("Cycle Number", fontsize=12)
plt.ylabel("Capacity (mAh/g)", fontsize=12)
plt.title("Free-Standing Lithium Metal Anodes: Cycle Number vs Capacity (2021–2024)", fontsize=14)

# Legend
from matplotlib.lines import Line2D
legend_elements = [
    Line2D([0], [0], marker='o', color='w', label='0.3–0.5 C', markerfacecolor='blue', markersize=10),
    Line2D([0], [0], marker='s', color='w', label='2 C', markerfacecolor='green', markersize=10),
    Line2D([0], [0], marker='D', color='w', label='5 C', markerfacecolor='orange', markersize=10),
]
plt.legend(handles=legend_elements, loc='lower left')

# Grid and limits
plt.grid(True)
plt.xlim(0, 400)
plt.ylim(50, 380)

plt.tight_layout()
plt.show()

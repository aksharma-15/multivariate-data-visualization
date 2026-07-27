# multivariate-data-visualization
Hands on guide for making appealing and clean charts for multivariate problems


![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white) ![NumPy](https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white) ![Matplotlib](https://img.shields.io/badge/Matplotlib-%23ffffff.svg?style=for-the-badge&logo=Matplotlib&logoColor=black) ![Seaborn](https://img.shields.io/badge/Seaborn-%23388E3C.svg?style=for-the-badge)


## Core Objectives

This notebook is engineered to tackle several key data visualization challenges:
*   Demonstrate plotting 3 dimensional data with colorblind templates for easy access to colorblind individuals.
*   Demonstration of fixing bad and unnactractive charts which are less appealing for stakeholders.
*   Execute Multivariate Data Visualization techniques, specifically focusing on CCN, CNN, and NNN data types.
*   Implement advanced Seaborn plotting architectures like Joint plots and Pairplots.

---

## The Dataset

I have utilized the Video Game Sales dataset, sourced from `datasets/vgsales.csv` after which I have produced a synthetic dataset to demonstrate the differences between a good and a bad chart.

High-cardinality categorical features can easily clutter a visualization. To maintain a clean and interpretable analysis space, the data is systematically pre-filtered to focus exclusively on the top 3 categories for `Genres`, `Publisher`, and `Platform`. 

---

## Visualization Architectures Explored

### NNC (Numerical-Numerical-Categorical)
Visualizing the correlation between two continuous variables while retaining categorical context.
*   **The Challenge:** Adding information about a categorical variable onto a standard numerical scatterplot.
*   **The Implementation:** We utilize `sns.scatterplot` to map `NA_Sales` against `EU_Sales`, leveraging the `hue` parameter to seamlessly encode the `Publisher` categorical data using color.

### CCN (Categorical-Categorical-Numerical)
Visualizing numerical distributions across multiple nested categories.
*   **The Challenge:** Visualizing the global sales for each publisher, but separated by genres.
*   **The Implementation:** We deploy a "dodged" `sns.boxplot` mapping `Publisher` against `Global_Sales`, with `Genre` acting as our hue separator.
*   **Engineering Insights:** This visualization immediately highlights that Namco possesses lower median sales across all genres compared to its peers. Furthermore, we can clearly see that each of the three publishers dominates a distinct genre median: Action for Namco, Misc for Activision, and Sports for EA.

### NNN (Numerical-Numerical-Numerical)
Mapping three continuous variables simultaneously without reverting to complex 3D plots that often fail in static stakeholder reports.
*   **The Challenge:** Understanding how a game's rank affects the correlation between North American and Japanese sales.
*   **The Implementation:** We construct a Bubble Chart using `sns.scatterplot`, mapping `NA_Sales` against `JP_Sales` and binding the `Rank` integer to the `size` parameter (scaled from 1 to 100) for each data point.

---

## Prerequisites & Execution

> **Engineering Note:** It is highly recommended to execute this notebook within an isolated virtual environment (e.g., `venv` or `conda`) to prevent package conflicts.

1.  Clone this repository to your local machine.
2.  Ensure you have the core libraries installed: `pandas`, `numpy`, `matplotlib`, and `seaborn`.
3.  Execute the Jupyter Notebook environment to interact with the data and render the visualizations.

---

## 🤝 Contributing

Contributions to improve the examples, add new functions or methods, or fix typos are always welcome. Please feel free to open an issue or submit a pull request!

---

## Connect with me
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/abhay-kumar-sharma-a22a94171)

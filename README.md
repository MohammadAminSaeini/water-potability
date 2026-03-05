# Water Potability Analysis

## Overview
Access to safe drinking water is a fundamental human right and a cornerstone of global public health. Ensuring water potability not only protects communities from waterborne diseases but also drives significant economic benefits. In this project, I analyze a comprehensive dataset containing water quality metrics for 3,276 different water sources. By examining key chemical and physical parameters, the goal is to perform a thorough exploratory data analysis, address missing values, and ultimately understand the defining characteristics that classify water as safe for human consumption.

## Dataset Features
The dataset (`src/water_potability.csv`) contains 3,276 entries and includes the following 10 columns:
* `ph`: pH value indicating the acid-base balance of the water.
* `Hardness`: Capacity of water to precipitate soap, primarily caused by the presence of calcium and magnesium salts.
* `Solids`: Total dissolved solids.
* `Chloramines`: Amount of chloramines present in the water.
* `Sulfate`: Amount of dissolved sulfates.
* `Conductivity`: Electrical conductivity of the water.
* `Organic_carbon`: Amount of organic carbon present.
* `Trihalomethanes`: Amount of trihalomethanes present.
* `Turbidity`: Measure of the water's light-emitting properties.
* `Potability`: The target classification variable where `1` indicates potable (safe) water and `0` indicates not potable.

## Project Workflow
1.  **Data Inspection**:
    * Performed an initial evaluation of the dataframe's columns, data types, and unique values.
    * Identified a substantial number of missing values across three variables: `ph` (491 missing), `Sulfate` (781 missing), and `Trihalomethanes` (162 missing).
2.  **Handling Missing Values**:
    * Evaluated deleting the missing values, but dropping the data reduced the dataset down to 2,011 rows, which was deemed unjustifiable.
    * **Selected Approach (Custom KNN Imputation)**: Implemented a custom K-Nearest Neighbors (KNN) algorithm (`simple_knn_impute`). This algorithm utilizes Manhattan distance (L1) to find the nearest data points and accurately impute the missing values for `Sulfate`, `ph`, and `Trihalomethanes`.
3.  **Data Visualization**:
    * Visualized relationships between crucial parameters, including pH vs. Hardness and pH vs. Turbidity.
    * Compared the data against standard World Health Organization (WHO) allowable ranges, such as the pH safe range of 6.5 to 8.5.
4.  **Conclusion**:
    * The evidence and distributions observed during the analysis suggest that this dataset was likely synthetically generated rather than collected from real-world, natural water sources.

## Technologies & Libraries Used
* **Python 3**
* **Pandas**: For data manipulation and summary generation.
* **NumPy**: For numerical array operations.
* **Matplotlib**: For plotting and data visualization.

## How to Run
1. Clone this repository to your local machine.
2. Ensure you have the dataset located at `src/water_potability.csv` relative to the notebook.
3. Run the Jupyter Notebook (`water_potability.ipynb`) sequentially to view the data inspection, the custom KNN imputation process, and the final visualizations.

**Kaggle** : [https://www.kaggle.com/code/mohammadaminsaeini/water-potability](https://www.kaggle.com/code/mohammadaminsaeini/water-potability)
**Linkedin**: [https://www.linkedin.com/in/mohammad-amin-saeini](https://www.linkedin.com/in/mohammad-amin-saeini)

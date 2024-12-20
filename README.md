# Apriori Algorithm for System Call Data Analysis  

This repository demonstrates how to use the **Apriori Algorithm** to analyze system call data, identify frequent patterns, and generate association rules. The project features a complete pipeline, including data preprocessing, feature selection, and visualization. Both structured and unstructured datasets are included to illustrate the data transformation process.

---

## **Table of Contents**  
1. [Overview](#overview)  
2. [Dataset Details](#dataset-details)  
3. [Repository Structure](#repository-structure)  
4. [Code Details](#code-details)  
5. [Requirements](#requirements)  
6. [Usage](#usage)  
7. [Outputs](#outputs)  
8. [Future Enhancements](#future-enhancements)

---

## **Overview**  

This project focuses on applying **Association Rule Learning** to system call data, which is commonly used in malware detection, cybersecurity, and behavior analysis of software. The core functionality is implemented using the **Apriori Algorithm** to extract frequent itemsets and generate rules based on metrics like support, confidence, and lift. The results are visualized to provide insights into relationships between system events.  

---

## **Dataset Details**  

### **Unstructured Dataset**  
- The unstructured dataset contains raw data representing system calls and their occurrences.  
- Each row corresponds to a different sample, and columns are raw values that require preprocessing.  

### **Structured Dataset**  
- The structured dataset is a preprocessed binary matrix derived from the unstructured dataset.  
- **Rows**: Represent system call samples.  
- **Columns**: Binary indicators (`0` or `1`) for the presence or absence of specific system events.  
- **Dimensions**: The dataset contains 540 rows and 5195 columns after preprocessing.

### **Preprocessing Steps**  
1. **Cleaning**: Removal of unnecessary spaces or special characters from column names.  
2. **Feature Selection**: Low-variance features (those with variance ≤ 0.01) are removed.  
3. **Binary Transformation**: Numerical values are converted to binary (`0` for absence, `1` for presence).  

---

## **Repository Structure**  

The repository contains the following files and directories:  
- **`apriori-system-calls code.py`**: Main script containing the full code for data preprocessing, Apriori analysis, and visualization.  
- **`structured_dataset (2).csv`**: Binary dataset ready for analysis.  
- **`dataset - System calls.csv`**: Raw data before preprocessing.  
- **`README.md`**: Documentation for the project.  

---

## **Code Details**  

### **1. Data Preprocessing**  
The preprocessing pipeline includes:  
- Cleaning column names using `str.strip` and `str.replace`.  
- Feature selection with `VarianceThreshold` to remove features with low variability.  
- Binary conversion (`True`/`False`) to represent feature presence or absence.  
  

### **2. Apriori Algorithm**  
The **Apriori Algorithm** is applied to identify frequent itemsets. Key parameters include:  
- **`min_support`**: Minimum frequency threshold for itemsets (e.g., 0.1).  
- **`max_len`**: Maximum size of the itemsets (e.g., 2 for pairs).  

### **3. Association Rule Generation**  
Rules are generated from frequent itemsets using metrics like:  
- **Support**: Fraction of rows containing the itemset.  
- **Confidence**: Probability of consequent given antecedent.  
- **Lift**: Strength of association compared to random chance.  

### **4. Visualization**  
The results are visualized using `matplotlib` and `seaborn`:
- **Bar Plots**: Show top association rules ranked by lift.  
- **Heatmaps**: Display support, confidence, and lift for top rules.  

---

## **Requirements**  

Install the following libraries to run the project:  
- `pandas`  
- `numpy`  
- `mlxtend`  
- `scikit-learn`  
- `scipy`  
- `matplotlib`  
- `seaborn`  

## **Usage** 
- **1. Clone the repository:
git clone https://github.com/Abig12/apriori-system-calls.git
cd apriori-system-calls

- **2. Run the main script:
python apriori-system-calls code.py


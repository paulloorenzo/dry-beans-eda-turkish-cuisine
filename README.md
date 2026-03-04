# Dry Beans EDA — Exploring Turkish Cuisine Through Data
Dry Beans EDA is an Exploratory Data Analysis project that investigates the physical characteristics of bean varieties used in traditional Turkish cuisine through data visualization and statistical exploration.
The analysis uses the UCI Dry Bean Dataset within a Jupyter Notebook environment to uncover patterns between **Seker**, **Horoz**, and other bean varieties featured in Turkey's classic *Etli Kuru Fasulye* (White Bean Stew).

## Project Overview
This repository documents the full exploratory analysis pipeline — from data loading and inspection through feature engineering and visual storytelling. The project was developed alongside a companion Medium article that contextualizes the findings within Turkish culinary traditions.

## System Features
- **Jupyter Notebook Analysis:** Provides a step-by-step, reproducible EDA workflow with inline visualizations.
- **Data Quality Inspection:** Checks for duplicates and missing values to assess dataset integrity.
- **Feature Engineering Pipeline:** Creates derived columns for binary classification and multi-class grouping.
- **Multi-Chart Visualization Suite:** Generates histograms, scatterplots, violin plots, and correlation matrices for comparative analysis.
- **Cultural Data Storytelling:** Connects analytical findings to real-world culinary context in Turkish cuisine.

## System Architecture
The notebook follows a structured EDA pipeline designed to progressively deepen understanding of the dataset:

### Data Ingestion & Inspection
- Loads the dataset from a compressed `.zip` archive containing `.xlsx` files.
- Inspects shape, data types, and summary statistics.
- Identifies duplicate entries and confirms zero null values across all features.

### Feature Engineering
- Creates the `is_seker` binary column to flag Seker bean samples.
- Creates the `Class2` categorical column to group beans into SEKER, HOROZ, and OTHERS.
- Simplifies the 7-class problem into a focused 3-group comparison.

### Exploratory Data Analysis
- Generates class distribution bar charts for value count comparison.
- Builds a correlation matrix to identify relationships between geometric features.
- Plots scatterplots comparing Major vs. Minor Axis Length across classes.
- Creates histograms for area distribution between Seker and Horoz beans.
- Produces violin plots to compare solidity distribution between the two varieties.

## Data Model
The UCI Dry Bean Dataset contains 13,611 grain samples across 7 registered bean varieties from Turkey. Features were extracted from grain images using computer vision techniques.

| Feature Group | Count | Examples |
|---------------|-------|----------|
| Dimensional Features | 12 | Area, Perimeter, MajorAxisLength, MinorAxisLength |
| Shape Features | 4 | Solidity, Roundness, Compactness, ShapeFactor1–4 |
| Target Variable | 1 | Class (SEKER, BARBUNYA, BOMBAY, CALI, HOROZ, SIRA, DERMASON) |

### Engineered Features

| Column | Type | Description |
|--------|------|-------------|
| `is_seker` | Binary | Flags whether a sample belongs to the SEKER class or not. |
| `Class2` | Categorical | Groups all 7 bean types into three categories: **SEKER**, **HOROZ**, and **OTHERS**. |

> **Citation:** Koklu, M. and Ozkan, I.A., 2020. Multiclass classification of dry beans using computer vision and machine learning techniques. *Computers and Electronics in Agriculture*, 174, 105507.

## Key Findings Summary
The analysis revealed the following insights about Seker and Horoz beans:

1. **Similar Area Distributions** — Both varieties have nearly identical area ranges, making size an unreliable differentiator.
2. **Overlapping Dimensions** — Width and length measurements show significant overlap in the scatterplot.
3. **Comparable Solidity** — Violin plots confirm only minor differences in compactness between the two classes.
4. **Effective Grouping** — The `Class2` feature engineering step simplifies downstream analysis by reducing 7 classes to 3 meaningful groups.

## Tech Stack
| Layer | Technology |
|-------|------------|
| Environment | Jupyter Notebook |
| Language | Python 3 |
| Data Manipulation | pandas, NumPy |
| Visualization | Matplotlib, Seaborn |
| Data Source | UCI Machine Learning Repository |
| Article Platform | Medium |

## Repository Structure
```
dry-beans-eda-turkish-cuisine/
│
├── Beans_model.ipynb          # Main EDA notebook with all analysis and visualizations
├── dry_bean_dataset.zip       # Compressed dataset (Dry_Bean_Dataset.xlsx)
└── README.md                  # Project overview and documentation (this file)

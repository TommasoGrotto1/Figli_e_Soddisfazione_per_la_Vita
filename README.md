# Children and Life Satisfaction  
### Analysis using European Social Survey (ESS) – Bachelor’s Thesis Project

This repository contains the Stata code and final written thesis (in Italian) for my bachelor's degree project in Sociology.  
The research investigates the relationship between **having children** and **life satisfaction**, using data from **ESS Round 9**.

The aim of this repository is to showcase the analytical workflow I followed, including data preparation, variable recoding, exploratory analysis, and regression modelling.

---

## Repository Structure

Figli_e_Soddisfazione_per_la_Vita/
│
├── Dofile.do # Stata script containing all steps of the analysis
└── Figli e felicità.pdf # Final bachelor’s thesis (Italian)

---

## Research Overview

The project explores:

- Whether having children increases or decreases **life satisfaction**.
- Whether the relationship varies by:
  - **Gender**
  - **Education level**
  - **Marital status**
  - **Health status**
  - **Employment contract type**
  - **Working hours**
  - **Age**
  - **Religiosity**

The analysis relies on **microdata from the European Social Survey (ESS), Round 9** and focuses on building interpretable statistical models.

---

## Methods and Analytical Workflow

The `Dofile.do` executes the entire pipeline:

### **1. Data Import and Inspection**
- Import ESS dataset  
- Descriptive checks using `tab1`, `codebook`, and summary statistics by country and round

### **2. Variable Recoding**
The script reconstructs cleaned versions of key predictors, including:

- `bthcld_m` – indicator for having children  
- `nbthcld_m` – number of children (1–4+)  
- `eisced_m` – education level (low/medium/high)  
- `maritalb_m` – marital status  
- `wrkctra_m` – contract type  
- `wkhtot_m` – working hours (grouped)  

A combined variable `children` is created and used in the main models.

### **3. Missing Data Handling**
- Removes ESS Round 10  
- Keeps only valid responses for all model variables  

### **4. Exploratory Analysis**
- Univariate and bivariate frequency tables  
- Boxplots and histograms for:
  - Life satisfaction  
  - Religiosity  
  - Age  
  - Working hours  

### **5. Regression Models**
The core of the analysis includes:

- Baseline models of **life satisfaction on number of children**  
- Separate models for men and women  
- Full multivariate models with controls  
- Several **interaction models**:
  - Children × Gender  
  - Children × Education  
  - Children × Marital status  
  - Children × Health  
  - Children × Contract type  
  - Children × Working hours  
  - Children × Age  
  - Children × Religiosity  

### **6. Marginal Effects and Plots**
- Uses `margins` and `marginsplot` to visualize how predicted life satisfaction varies across demographic groups.

---

## Thesis Document

The PDF **“Figli e felicità.pdf”** contains the full final thesis.  
It is written in Italian and includes:

- Literature review  
- Methodological framework  
- Regression results  
- Interpretation  
- Limitations and future directions  

---

## Requirements

To run the analysis you need:

- **Stata 15 or newer**
- ESS Round 9 dataset (not included due to licensing restrictions)

Before running the do-file, change the working directory:

```stata
cd "path/to/your/folder"
use "Dataset ESS"

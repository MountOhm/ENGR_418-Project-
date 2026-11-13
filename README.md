# ENGR 418 Final Project: Advanced Housing Price Prediction Pipeline

An end-to-end machine learning pipeline engineered for the City of Kelowna / Residential Valuation, utilizing rigorous data preprocessing, informative missingness analysis, and regression modeling built on an 80-column feature set.

---

## 👥 Team Members & Responsibilities
- **Denis Rotaru - Team Lead**: End-to-end Python pipeline development, data cleaning, feature engineering, and model training architecture.
- **Michael Janzen - Technical Reporting**: Exploratory Data Analysis (EDA), target distribution profiling, and report documentation.
- **Geyser Amani - Course Theory Validator**: Presentation deck assembly, performance metric logging, and GitHub repository maintenance.

---

## 🎯 Project Goals & Scope
- **Objective:** Move beyond basic tabular models by implementing a production-grade machine learning workflow for real estate valuation.
- **Key Challenges Addressed:** Handling high-dimensional data (80 columns), analyzing informative missingness rather than blindly dropping sparse features, and mitigating multicollinearity.
- **Deliverables:** A fully reproducible Google Colab notebook workflow, an automated preprocessing pipeline (`ColumnTransformer`), and an interactive model testing sandbox.

---

## 📊 Project Architecture & Pipeline
```mermaid
flowchart TD
    %% Styling
    classDef data fill:#e1f5fe,stroke:#039be5,stroke-width:2px,color:#01579b;
    classDef process fill:#f3e5f5,stroke:#8e24aa,stroke-width:2px,color:#4a148c;
    classDef model fill:#e8f5e9,stroke:#43a047,stroke-width:2px,color:#1b5e20;
    classDef evaluation fill:#fff3e0,stroke:#fb8c00,stroke-width:2px,color:#e65100;

    subgraph Data_Setup["Part 0: Data Ingestion & Understanding"]
        A["Raw Housing Data<br>(Train/Test from GitHub)"] --> B["Profile Columns<br>(Data Types: int64, float64, object)"]
        B --> C["Target Value Profiling<br>(SalePrice Distribution Plot)"]
    end
    
    subgraph Pre_Processing["Part 1: Preprocessing & Exploratory Analysis"]
        D["Identify Missing Values<br>(High-Missing KDE Densities)"] --> E["Statistical Correlation Analysis"]
        E --> E1["Pearson Correlation (r)<br>(Numeric Features vs SalePrice)"]
        E --> E2["One-Way ANOVA (F-Statistic)<br>(Categorical Features vs SalePrice)"]
        E1 --> F["Synthesize Redundant Pairs<br>(e.g. AvgRoomSize, GarageCapacityScore)"]
    end

    subgraph Baselines_Models["Part 2: Baseline Modeling & Validation Pipeline"]
        G1["Ultra-Basic Baseline V0<br>(Only Raw Numeric + Imputation)"] --> H["Cross-Validation Pipeline<br>(5-Fold CV)"]
        G2["Advanced Preprocessor Pipeline<br>(ColumnTransformer: Impute + Scale + OneHot)"] --> H
        H --> I["Linear Regression Training"]
    end

    subgraph Sandbox_Environment["Part 3: Model Interaction & Interface"]
        I --> J["Interactive Real-Time Sandbox<br>(ipywidgets sliders)"]
        J --> K["End-User Property Price Prediction"]
    end

    %% Apply Styles
    class A,B,C data;
    class D,E,E1,E2,F process;
    class G1,G2,H,I model;
    class J,K evaluation;
```

## ▶️ Running Instructions
- **Denis Rotaru**: End-to-end Python pipeline development, data cleaning, feature engineering, and model training architecture.

## 📝 Summary of Results and Reflection
- **Denis Rotaru**: End-to-end Python pipeline development, data cleaning, feature engineering, and model training architecture.


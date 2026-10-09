[Русский](README.md) | [English](README.en.md)

# Personal Computer Market Analysis

**Data Analysis · Statistics · Machine Learning**

Final project for the *Artificial Intelligence and Machine Learning Specialist* program at Tomsk State University.

<p align="left">
  <img src="https://img.shields.io/badge/Python-3.13.5-3776AB?logo=python&logoColor=white" alt="Python" />
  <img src="https://img.shields.io/badge/NumPy-2.5.3-013243?logo=numpy&logoColor=white" alt="NumPy" />
  <img src="https://img.shields.io/badge/Pandas-3.0.6-150458?logo=pandas&logoColor=white" alt="Pandas" />
  <img src="https://img.shields.io/badge/SciPy-1.18.1-8CAAE6?logo=scipy&logoColor=white" alt="SciPy" />
  <img src="https://img.shields.io/badge/Scikit--learn-1.9.1-F7931E?logo=scikitlearn&logoColor=white" alt="Scikit-learn" />
  <img src="https://img.shields.io/badge/Statsmodels-0.15.0-4051B5" alt="Statsmodels" />
  <img src="https://img.shields.io/badge/Matplotlib-3.11.2-11557C" alt="Matplotlib" />
  <img src="https://img.shields.io/badge/Seaborn-0.13.2-4C72B0" alt="Seaborn" />
</p>

---

## Results

| 1,853 | 0.784 | RUB 9,985.59 |
|:---:|:---:|:---:|
| Observations after cleaning | Price prediction model R² | MAE |

## About the Project

The client plans to enter the online market with competitive and in-demand custom-built personal computers.

The goal is to analyze the market, identify characteristics associated with computer sales and prices, and develop a price prediction model.

### Research Objectives

**1 — Analysis of Sales Factors**

Regression analysis of the relationships between sales volume, price, and computer specifications. The primary focus is on interpreting regression coefficients and assessing statistical significance rather than predicting sales for new products.

**2 — Price Prediction**

Developing a linear regression model to estimate computer prices based on their specifications.

## Data

The original dataset contains **4,500 observations and 16 columns**, including a product identifier. It describes computers listed on an online marketplace.

### Original Dataset Structure

| No. | Feature | Non-null values | Data type |
|---:|---|---:|---|
| 0 | `product_id` | 4,500 | `int64` |
| 1 | `title` | 4,500 | `str` |
| 2 | `price` | 4,499 | `str` |
| 3 | `sales` | 1,164 | `str` |
| 4 | `feedbacks` | 4,500 | `str` |
| 5 | `seller` | 4,391 | `str` |
| 6 | `seller_rating` | 4,389 | `float64` |
| 7 | `Processor` | 4,500 | `str` |
| 8 | `RAM` | 4,500 | `str` |
| 9 | `Hard drive` | 4,500 | `str` |
| 10 | `GPU` | 4,500 | `str` |
| 11 | `Operating system` | 4,500 | `str` |
| 12 | `Warranty period` | 2,648 | `str` |
| 13 | `Country of manufacture` | 2,611 | `str` |
| 14 | `Product dimensions` | 4,500 | `str` |
| 15 | `Product dimensions (with packaging)` | 4,500 | `str` |

The dataset includes prices, sales figures, feedback, seller information, technical specifications, warranty periods, and product dimensions.

Data preprocessing involved handling missing values, duplicates, and anomalies, parsing nested feature structures, and standardizing categorical values.

After cleaning, **1,853 observations** remained for the analysis.

## Methodology

The research consisted of the following stages:

- **Data preparation:** handling missing values, duplicates, and anomalies; parsing nested structures and standardizing product specifications.
- **Exploratory data analysis:** examining distributions and relationships between variables.
- **Statistical analysis:** hypothesis testing, multicollinearity assessment using VIF, and analysis of statistical associations.
- **Feature engineering:** Box–Cox and Yeo–Johnson transformations, and smoothed target encoding of categorical variables.
- **Modeling:** building regression models, interpreting coefficients, and evaluating price prediction performance.

## Modeling Results

### Price Prediction

A linear regression model was developed to estimate computer prices.

| Metric | Result |
|---|---:|
| R² on the original price scale | 0.784 |
| MAE | RUB 9,985.59 |
| RMSE | RUB 17,833.63 |
| R² on the transformed target scale | 0.891 |

The R² value of 0.891 was obtained on the transformed target scale and should not be directly compared with the R² value calculated on the original price scale.

### Factors Associated with Price

The analysis identified notable associations between computer prices and the following factors:

- GPU specifications;
- SSD and HDD capacity;
- CPU type and core count;
- RAM capacity;
- warranty period;
- seller.

### Sales Analysis

Regression analysis was used to examine statistical relationships between sales, prices, and computer specifications. This part of the research focuses on interpreting associated factors rather than developing a separate sales prediction system.

## Practical Applications

The findings can serve as an analytical basis for product assortment planning and positioning computer builds:

- assessing the relationship between technical specifications and price;
- comparing computer configurations;
- considering seller characteristics and pricing strategies;
- identifying product features to emphasize in marketplace listings.

The identified relationships are statistical associations within the analyzed sample and do not establish causality. Applying the results to other marketplaces or time periods requires additional validation.

## Technologies

| Library | Purpose |
|---|---|
| Python | Main programming language |
| Pandas, NumPy | Data processing |
| SciPy | Statistical methods and transformations |
| Statsmodels | Regression analysis and statistical interpretation |
| Scikit-learn | Model development and evaluation |
| Matplotlib, Seaborn | Data visualization |

## Project Structure

```text
pc-market-analysis/
├── data/
│   └── wb_pc_hard.csv
├── analysis.ipynb
├── README.md
├── requirements.txt
└── .gitignore
```

`analysis.ipynb` is the main notebook containing data exploration, feature preparation, statistical analysis, and modeling.

## Running the Project

The project requires Python, Visual Studio Code with the Python and Jupyter extensions, and the dataset file.

### 1. Clone the Repository

```bash
git clone https://github.com/artemsekta/pc-market-analysis.git
cd pc-market-analysis
```

### 2. Install VS Code Extensions

The extensions can be installed through the terminal:

```powershell
code --install-extension ms-python.python
code --install-extension ms-toolsai.jupyter
```

Alternatively, install **Python** and **Jupyter** through the Extensions panel in Visual Studio Code.

### 3. Create a Virtual Environment

```bash
python -m venv .venv
```

Activate the environment on Windows:

```powershell
.venv\Scripts\Activate.ps1
```

On Linux or macOS:

```bash
source .venv/bin/activate
```

### 4. Install Dependencies

```bash
python -m pip install -r requirements.txt
```

### 5. Open the Project in VS Code

```bash
code .
```

Open `analysis.ipynb`. If VS Code does not select the virtual environment automatically, click **Select Kernel** in the upper-right corner of the notebook and select the Python interpreter from `.venv`.

Run the notebook cells sequentially.

The dataset file `data/wb_pc_hard.csv` must be available at the path referenced in the notebook.

## Limitations

- The original dataset contains missing values and inconsistently formatted entries.
- The data collection period is not specified.
- The results apply to the analyzed sample and require further validation before being generalized to other settings.
- The price prediction model is intended for analytical assessment and is not a production-ready automated pricing system.
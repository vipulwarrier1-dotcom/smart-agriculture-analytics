# Smart Agriculture Analysis — Karnataka Crop Recommendation EDA

> An exploratory data analysis (EDA) of crop suitability across Karnataka's agro-climatic regions, built using Python. The project uncovers relationships between soil nutrients (N-P-K), climatic variables (rainfall, temperature, humidity, pH), and crop recommendations — broken down by district, season, soil type, and region.

\---

## Project Overview

Karnataka's agricultural landscape is highly diverse — spanning coastal belts, semi-arid plateaus, the Malnad region, and the Deccan — each with unique soil profiles and seasonal patterns. This project analyses a curated crop recommendation dataset (`karnataka\_crop\_dataset\_V2.csv`) to surface actionable agronomic insights using data visualisation.

The analysis is structured around five core questions:

1. How are crop recommendations distributed across seasons and agro-climatic regions?
2. What are the rainfall patterns by region and season?
3. Which crops are most recommended overall, and what are their soil pH and rainfall requirements?
4. How do macro-nutrient (N-P-K) profiles vary across soil types?
5. Which crops demand the highest and lowest soil nutrients — for all 39 crops and for common kitchen staples?

\---

## Dataset

|Attribute|Details|
|-|-|
|**File**|`karnataka\_crop\_dataset\_V2.csv`|
|**Rows**|21,960|
|**Unique Crops**|39|
|**Districts**|31|
|**Regions/Zones**|4 (Coastal, Malnad, North Karnataka, South Karnataka)|
|**Soil Types**|6 (Loamy, Red, Black, Sandy, Laterite, Alluvial)|
|**Seasons**|3 (Kharif, Rabi, Zaid)|

### Features

|Column|Type|Description|
|-|-|-|
|`N`|Continuous|Nitrogen content in soil (kg/ha)|
|`P`|Continuous|Phosphorous content in soil (kg/ha)|
|`K`|Continuous|Potassium content in soil (kg/ha)|
|`temperature`|Continuous|Average temperature (°C)|
|`humidity`|Continuous|Relative humidity (%)|
|`ph`|Continuous|Soil pH|
|`rainfall`|Continuous|Average rainfall (mm)|
|`soil\_type`|Categorical|Type of soil|
|`season`|Categorical|Farming season|
|`district`|Categorical|District in Karnataka|
|`region`|Categorical|Agro-climatic zone|
|`label`|Categorical|Recommended crop (target variable)|

\---

## Project Structure

```
Smart-Agri-Analysis/
│
├── karnataka\_crop\_dataset\_V2.csv   # Dataset
├── Smart\_Agri\_Analysis.ipynb       # Main Jupyter Notebook
├── README.md                       # Project documentation (this file)
└── requirements.txt                # Python dependencies
```

\---

## Key Findings

### 1\. Seasonal \& Regional Distribution

* **Kharif** (monsoon) season dominates crop recommendations across all four agro-climatic zones.
* **Zaid** (summer) crops are the least recommended — likely constrained by water availability.

### 2\. Rainfall Patterns

* **Coastal Karnataka** records the highest average rainfall, strongly favouring Kharif crops.
* North Karnataka shows the lowest average rainfall, with more balanced Rabi representation.

### 3\. Top Crops \& Soil Requirements

* The **top 5 most recommended crops** show distinct soil pH and rainfall clusters.
* **Groundnut** is the most pH-sensitive crop; **Mango** is the least.
* **Banana** prefers slightly acidic soil conditions (pH < 7).
* Most crops can be grown with low rainfall — suggesting high dependence on irrigation infrastructure.

### 4\. N-P-K by Soil Type

* **Black soil** has the lowest macro-nutrient holding capacity.
* **Laterite and Alluvial soils** show the highest average N-P-K retention.
* **Phosphorous (\~45 kg/ha)** remains remarkably consistent regardless of soil type — a notable agronomic pattern.

### 5\. Nutrient Demand Across Crops

* **Sugarcane** is the highest soil-nutrient consumer across all 39 crops.
* **Moth beans** (*Madke kalu*) absorb the least.
* Among kitchen staples and cereals: **Coconut** is the largest nutrient absorber; **Ragi** the smallest.

\---

## Visualisations

|#|Plot|Type|
|-|-|-|
|1|Distribution of Seasonal Crops by Agro-Climatic Region|Grouped Bar Chart|
|2|Average Seasonal Rainfall Across Regions|Grouped Bar Chart|
|3|Top 5 Most Recommended Crops|Horizontal Bar Chart|
|4|Rainfall vs Soil pH for Top 5 Crops|Scatter Plot|
|5|Rainfall vs Soil pH — Individual Crop FacetGrid|Small Multiples|
|6|Average N-P-K Profile by Soil Type|Grouped Bar Chart|
|7|Crop Recommendations Across Karnataka Districts|Heatmap|
|8|Crop Recommendations Across Soil Types|Heatmap|
|9|N-P-K Requirements Across All 39 Crops|Stacked Horizontal Bar|
|10|N-P-K Requirements for Kitchen Staples \& Cereals|Stacked Horizontal Bar|

\---

## Tech Stack

* **Python 3.14**
* **Pandas** — data loading, cleaning, grouping
* **NumPy** — numerical operations
* **Matplotlib** — base plotting
* **Seaborn** — statistical visualisations

\---

## Setup \& Usage

### 1\. Clone the repository

```bash
git clone https://github.com/vipulwarrier1-dotcom/smart-agri-analysis.git
cd smart-agri-analysis
```

### 2\. Install dependencies

```bash
pip install -r requirements.txt
```

Or install manually:

```bash
pip install pandas numpy matplotlib seaborn
```

### 3\. Run the notebook

```bash
jupyter notebook Smart\_Agri\_Analysis.ipynb
```

> Make sure `karnataka\_crop\_dataset\_V2.csv` is in the same directory as the notebook.

\---

## requirements.txt

```
pandas>=3.0.4
numpy>=2.5.0
matplotlib>=3.11.0
seaborn>=0.13.2
jupyter
```

\---

## Scope \& Limitations

* This analysis is **exploratory** and descriptive — no predictive model is built.
* Crop recommendations reflect **dataset distributions**, not real-time market trends, water table data, or farmer preference surveys.
* The dataset represents **structured agronomic recommendations** and may not capture regional micro-variations at the taluk or village level.
* Outliers in rainfall data (particularly for Coastal Karnataka) may disproportionately influence regional averages.

\---

## Possible Extensions

* Build a **crop recommendation classifier** (Random Forest / XGBoost) using the existing features.
* Integrate **ISRO Bhuvan / IMD rainfall geodata** to validate dataset distributions against satellite-derived actuals.
* Create an interactive **Streamlit / Dash dashboard** for farmers or extension workers.
* Add **yield data** to move from recommendation density to productivity analysis.
* Perform **clustering** (K-Means / hierarchical) to identify natural crop-soil-climate groupings.

\---

## Author

**Vipul .G. Warrier**
Data \& Learning Enthusiast | Karnataka Agricultural Data Analysis

\---

## License

This project is released under the [MIT License](LICENSE).

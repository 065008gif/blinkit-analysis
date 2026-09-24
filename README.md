\# Blinkit Sales Analysis



A Python-based exploratory data analysis of Blinkit's item and outlet sales data — covering data cleaning, KPI calculation, and visualization. Originally scoped as a Power BI dashboard requirement, rebuilt end-to-end in Python (pandas, matplotlib, seaborn) inside a Jupyter notebook.



\## Business Requirement



Conduct a comprehensive analysis of Blinkit's sales performance, customer satisfaction, and inventory distribution to identify key insights and opportunities for optimization.



\## Dataset



`blinkit\_raw\_data.csv` — 8,523 item-level sales records with the following fields:



| Column | Description |

|---|---|

| Item Fat Content | Low Fat / Regular (raw data had inconsistent labels — cleaned in notebook) |

| Item Identifier | Unique item code |

| Item Type | Product category (Snacks, Dairy, Frozen Foods, etc.) |

| Outlet Establishment Year | Year the outlet was set up |

| Outlet Identifier | Unique outlet code |

| Outlet Location Type | Tier 1 / Tier 2 / Tier 3 |

| Outlet Size | Small / Medium / High |

| Outlet Type | Grocery Store / Supermarket Type1–3 |

| Item Visibility | Display prominence ratio |

| Item Weight | Product weight (had missing values, imputed) |

| Sales | Revenue for that item-outlet combination |

| Rating | Customer rating |



\## Data Cleaning



\- \*\*Item Fat Content\*\* had 5 inconsistent labels (`Low Fat`, `low fat`, `LF`, `Regular`, `reg`) — standardized into 2 clean categories.

\- \*\*Item Weight\*\* had 1,463 missing values — imputed using the median weight per `Item Type`.

\- \*\*Item Visibility\*\* had 526 rows with a value of exactly `0` — replaced with `NaN` and imputed using the median visibility per `Item Type`.

\- Checked for duplicate rows — none found.

\- Verified data types and confirmed no other categorical columns had inconsistent labels.



\## KPIs Computed



\- Total Sales

\- Average Sales

\- Number of Items Sold

\- Average Rating



\## Charts \& Insights



\### 1. Sales by Fat Content

!\[Sales by Fat Content](Outputs/output1.png)



Low Fat items drive roughly 65% of total sales versus \~35% for Regular items.



\### 2. Total Sales by Item Type

!\[Total Sales by Item Type](Outputs/output2.png)



Fruits \& Vegetables and Snack Foods are the top-performing categories by total sales.



\### 3. Outlet Tier by Item Fat Content

!\[Outlet Tier by Fat Content](Outputs/output3.png)



Sales patterns by fat content are broadly consistent across Tier 1, 2, and 3 outlets.



\### 4. Total Sales by Outlet Establishment Year

!\[Sales by Establishment Year](Outputs/output4.png)



Sales vary by outlet founding year, with no strictly linear trend by outlet age.



\### 5. Sales by Outlet Size

!\[Sales by Outlet Size](Outputs/output5.png)



Medium-sized outlets contribute the largest share of total sales.



\### 6. Total Sales by Outlet Location Type

!\[Sales by Outlet Location](Outputs/output6.png)



Tier 3 locations lead in total sales volume among the three location tiers.



\## Project Structure

blinkit-analysis/

├── Blinkit\_Analysis.ipynb

├── Blinkit Analysis.pptx

├── blinkit\_raw\_data.csv

├── Outputs/

│ └── (chart PNGs used above)

├── .gitignore

└── README.md



\## Setup



```bash

git clone https://github.com/065008gif/blinkit-analysis.git

cd blinkit-analysis

python -m venv venv

venv\\Scripts\\activate

pip install pandas numpy matplotlib seaborn jupyter ipykernel

```



Then open `Blinkit\_Analysis.ipynb` in VS Code, select the venv kernel, and run all cells.



\## Author



Akshit Kansal


# 🗳️ Participatory Budgeting Analysis: Comparing Proportional Voting Methods

> A data-driven analysis of the **Wieliczka Green Budget 2023** (Poland), implementing and comparing 5 proportional voting algorithms to evaluate fairness, efficiency, and voter representation.

---

## 📌 Overview

Participatory Budgeting (PB) is a democratic process where citizens directly decide how to allocate part of a public budget. This project analyzes a real-world PB election and compares multiple **proportional voting methods** to understand their trade-offs in fairness, efficiency, and representation.

### Dataset

| Property | Value |
|----------|-------|
| **Location** | Wieliczka, Poland (Green Budget / Zielony Milion) |
| **Year** | 2023 |
| **Total Budget** | 1,000,000 PLN |
| **Number of Projects** | 64 |
| **Number of Voters** | 6,586 |
| **Voting Type** | Approval Voting (no maximum) |

---

## 🔬 Voting Methods Compared

| Method | Description |
|--------|-------------|
| **MES** (Method of Equal Shares) | Each voter receives an equal budget share; projects are funded when supporters can collectively afford them |
| **MES + Add1** | MES with greedy completion to maximize budget utilization |
| **Phragmén's Sequential Method** | Minimizes the maximum "load" on any voter — balances representation |
| **SPAV** (Sequential Proportional Approval Voting) | Reweights votes after each selection using d'Hondt divisors |
| **Greedy Approval** | Picks the most popular projects by vote count (non-proportional baseline) |

---

## 📊 Analysis Sections

1. **Setup & Data Loading** — Parse `.pb` pabulib format files into structured DataFrames
2. **Data Exploration** — Project costs, vote distributions, and voter behavior
3. **Visualization** — Cost vs. votes plots, approval distribution charts
4. **MES Implementation** — Full algorithm with equal budget share mechanics
5. **Add1 Completion** — Greedy post-processing to maximize budget spending
6. **Method Comparison** — Side-by-side results for all 5 voting methods
7. **Fairness Analysis**
   - Gini Coefficient & Lorenz Curve
   - Price of Fairness (efficiency vs. equity trade-off)
   - Support Threshold Analysis (minimum votes to get selected)
   - Project Size Bias (do methods favor cheap or expensive projects?)
   - Budget Utilization
8. **Cost-Effectiveness Analysis** — Cost-per-vote for selected projects
9. **Geographic Distribution** — Interactive map (Folium) of funded projects
10. **Summary & Conclusions** — Key findings and method recommendations

---

## 🧠 Key Findings

- **MES works well in practice**: It selected diverse projects representing minority voter preferences, not just the most popular ones.
- **Add1 completion is crucial**: Without it, MES leaves budget unspent. The Add1 step maximizes utilization while preserving fairness.
- **Greedy is efficient but unfair**: It maximizes total votes satisfied but concentrates satisfaction among majority voters.
- **Phragmén balances load**: Minimizes extreme inequalities in how much each voter "pays" for selected projects.
- **SPAV is a middle ground**: More proportional than Greedy, less strict than MES.

---

## 🛠️ Tech Stack

- **Python 3**
- `pandas` — data manipulation
- `numpy` — numerical operations
- `matplotlib` & `seaborn` — static visualizations
- `folium` — interactive geographic maps
- `collections` — utility data structures

---

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/your-username/participatory-budgeting-analysis.git
cd participatory-budgeting-analysis
```

### 2. Install dependencies

```bash
pip install pandas numpy matplotlib seaborn folium
```

### 3. Download the dataset

Download the Wieliczka 2023 Green Budget `.pb` file from [pabulib.org](https://pabulib.org/) and place it in the project root:

```
poland_wieliczka_2023_green-budget.pb
```

### 4. Run the notebook

```bash
jupyter notebook term_project.ipynb
```

---

## 📁 Project Structure

```
participatory-budgeting-analysis/
│
├── term_project.ipynb                        # Main analysis notebook
├── poland_wieliczka_2023_green-budget.pb     # Dataset (pabulib format)
└── README.md                                 # Project documentation
```

---

## 📚 References

- [Pabulib — Participatory Budgeting Library](https://pabulib.org/)
- [Method of Equal Shares — equalshares.net](https://equalshares.net/)
- Phragmén, L. E. (1894). *Sur une méthode nouvelle pour réaliser, dans les élections, la représentation proportionnelle des partis.*
- Aziz, H., & Lee, B. E. (2020). *The expanding approvals rule: improving proportional representation and monotonicity.*

---

## 📄 License

This project is for academic/educational purposes as part of a university term project.

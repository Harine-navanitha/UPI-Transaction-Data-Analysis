# 📊 UPI Transaction Data Analysis & Business Intelligence

**Pondicherry University — School of Management, Department of Banking Technology**  
**MBAF426 — Business Intelligence Project**

> A comprehensive 5-year analysis of India's Unified Payments Interface (UPI) transaction ecosystem using Python, Power BI, and NPCI's published statistics.

---



**Guide:** Dr. C. Punitha Devi

---

## 📁 Project Structure

```
UPI-Transaction-Data-Analysis/
│
├── README.md
│
├── data/
│   ├── UPI_Transaction_Data.csv        ← Main dataset (60 months, Apr 2019–Mar 2024)
│   └── Data_Dictionary.xlsx            ← Column definitions, units, source notes
│
├── python/
│   └── UPI_Transaction_Analysis.ipynb  ← Full EDA + visualisation notebook
│
├── powerbi/
│   └── UPI_Transaction_Dashboard.pbix  ← Power BI dashboard (see setup below)
│
├── dashboard/
│   ├── Executive_Overview.png          ← 4-panel executive dashboard
│   ├── Transaction_Trends.png          ← Volume & value trend charts
│   └── Growth_Analysis.png             ← YoY growth analysis
│
└── docs/
    └── UPI_Project_Report.pdf          ← Full project report
```

---

## 🎯 Objectives

1. Analyse 5-year UPI transaction trends (volume, value, growth rates)
2. Measure the expansion of India's banking ecosystem on UPI
3. Compare Person-to-Person (P2P) vs Person-to-Merchant (P2M) payment behaviour
4. Track average transaction value evolution over time
5. Build a Power BI dashboard for executive decision-making

---

## 📂 Dataset

| Attribute | Detail |
|-----------|--------|
| **Source** | National Payments Corporation of India (NPCI) Monthly Dashboard |
| **Period** | April 2019 – March 2024 (5 Financial Years) |
| **Records** | 60 months |
| **Columns** | 11 (see Data Dictionary) |

**Key columns:**
- `Total_Volume_Crore` — Monthly UPI transactions in Crore
- `Total_Value_Lakh_Crore` — Monthly transaction value in Lakh Crore (INR)
- `Volume_Growth_Pct` / `Value_Growth_Pct` — MoM growth rates
- `Avg_Txn_Value_INR` — Average value per transaction
- `Banks_Live_on_UPI` — Number of banks active on UPI
- `P2P_Volume_Crore` / `P2M_Volume_Crore` — Segment split

---

## 🔍 Key Findings

### 1. Explosive Transaction Growth
- UPI volume grew from **782 Crore** (Apr 2019) to **17,400 Crore** (Mar 2024)
- That is a **22x increase** in just 5 years
- Value grew from ₹14.2 Lakh Crore to ₹587.2 Lakh Crore annually

### 2. Banking Ecosystem Expansion
- Banks live on UPI: **143 → 360** (+217 banks in 5 years)
- Reflects adoption by public sector, private, co-operative and Regional Rural Banks (RRBs)

### 3. Merchant Payments Surpassing P2P
- P2M share rose from **~30% (FY20) to ~55% (FY24)**
- Driven by QR code proliferation, ONDC, and merchant digitisation
- Signals maturation of UPI beyond personal money transfers

### 4. Rising Average Transaction Value
- Average transaction: **₹182 (Apr 2019) → ₹321 (Mar 2024)**
- Users are using UPI for utilities, insurance premiums, and larger purchases

### 5. COVID-19 Accelerated Adoption
- FY2021–22 saw the sharpest YoY growth, as contactless payments surged during and after the pandemic

### 6. Policy-Driven Growth
- RBI/NPCI interventions (UPI Lite, credit on UPI, merchant interoperability) have consistently expanded the ecosystem

---

## 🛠 Tools & Technologies

| Tool | Purpose |
|------|---------|
| Python (pandas, numpy, matplotlib) | Data cleaning, EDA, visualisation |
| Power BI | Interactive dashboard, Star Schema, DAX measures |
| Excel | Data dictionary, structured reference |
| GitHub | Version control and project showcase |

---

## ▶️ How to Run

### Python Notebook
```bash
# Clone the repository
git clone https://github.com/<your-username>/UPI-Transaction-Data-Analysis.git
cd UPI-Transaction-Data-Analysis

# Install dependencies
pip install pandas numpy matplotlib openpyxl

# Open notebook
jupyter notebook python/UPI_Transaction_Analysis.ipynb
```

### Power BI Dashboard
1. Download and open `powerbi/UPI_Transaction_Dashboard.pbix` in Power BI Desktop
2. If prompted, update the data source path to your local `data/UPI_Transaction_Data.csv`
3. Refresh the dataset

---

## 📊 Dashboard Preview

### Executive Overview
![Executive Overview](dashboard/Executive_Overview.png)

### Transaction Trends
![Transaction Trends](dashboard/Transaction_Trends.png)

### Growth Analysis
![Growth Analysis](dashboard/Growth_Analysis.png)

---

## 🏦 Why This Project Matters for Banking/Fintech

UPI has become the **world's largest real-time payment system** by volume. For anyone entering the banking, fintech, or BI space:
- Understanding UPI's trajectory is essential for product, risk, and strategy roles
- P2P vs P2M segmentation directly impacts merchant acquiring and payment gateway businesses
- Average transaction value trends guide credit underwriting and BNPL strategies on UPI

---

## 📚 Data Source

National Payments Corporation of India (NPCI):  
🔗 https://www.npci.org.in/what-we-do/upi/upi-ecosystem-statistics

---

## 📄 License

This project is for academic and portfolio purposes.  
Data is based on publicly available NPCI monthly statistics.

# Power BI Dashboard — Setup Instructions

## UPI Transaction Dashboard

### How to Connect Your Data

1. Open **Power BI Desktop**
2. Click **Get Data → Text/CSV**
3. Navigate to: `../data/UPI_Transaction_Data.csv`
4. Load into Power Query Editor

### Recommended Data Model (Star Schema)

```
Fact_UPI_Transactions (central table)
  ├── Dim_Date         (Month, FY, Quarter)
  ├── Dim_Segment      (P2P, P2M)
  └── Dim_Bank         (Banks Live count)
```

### Recommended DAX Measures

```dax
-- Total Volume (Crore)
Total Volume = SUM(UPI_Transaction_Data[Total_Volume_Crore])

-- Total Value (Lakh Crore)
Total Value = SUM(UPI_Transaction_Data[Total_Value_Lakh_Crore])

-- MoM Volume Growth
MoM Volume Growth % = 
DIVIDE(
    [Total Volume] - CALCULATE([Total Volume], PREVIOUSMONTH(Dim_Date[Month_dt])),
    CALCULATE([Total Volume], PREVIOUSMONTH(Dim_Date[Month_dt]))
) * 100

-- Average Transaction Value
Avg Txn Value INR = AVERAGE(UPI_Transaction_Data[Avg_Txn_Value_INR])

-- P2M Share %
P2M Share % = 
DIVIDE(SUM(UPI_Transaction_Data[P2M_Volume_Crore]), [Total Volume]) * 100

-- YoY Volume Growth
YoY Volume Growth % = 
DIVIDE(
    [Total Volume] - CALCULATE([Total Volume], SAMEPERIODLASTYEAR(Dim_Date[Month_dt])),
    CALCULATE([Total Volume], SAMEPERIODLASTYEAR(Dim_Date[Month_dt]))
) * 100
```

### Recommended Visuals

| Page | Visuals |
|------|---------|
| Executive Overview | 4 KPI cards, line chart (volume), area chart (value) |
| Transaction Trends | Dual-axis line chart, MoM growth waterfall |
| P2P vs P2M | Stacked bar, donut chart, P2M share line |
| Banking Ecosystem | Line chart (banks), clustered bar by FY |
| Growth Analysis | YoY growth bar, heatmap by month/year |

### Filters / Slicers Recommended
- Financial Year (FY slicer)
- Month range slider
- Segment (P2P / P2M)

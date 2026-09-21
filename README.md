# 📊 PhonePe Digital Payment Analytics Dashboard | Power BI

[![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://powerbi.microsoft.com/)
[![DAX](https://img.shields.io/badge/DAX-Data_Analysis_Expressions-orange?style=for-the-badge)](https://learn.microsoft.com/en-us/dax/)
[![Power Query](https://img.shields.io/badge/Power_Query-ETL-teal?style=for-the-badge)](https://powerquery.microsoft.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)
[![Author](https://img.shields.io/badge/Analyst-Subodh_Kumar-blue?style=for-the-badge&logo=linkedin)](https://www.linkedin.com/in/subodh-kumar-3520503ba/)

> **Executive Summary:** An interactive, end-to-end Business Intelligence case study built in Microsoft Power BI analyzing **300K+ transactions**, **₹3.47B+ in total payment value**, and **108K+ unique users**. This dashboard evaluates digital payment stability, demographic adoption, service category profitability, and temporal utilization to empower fintech leaders with data-driven strategic decisions.

---

## 📷 Executive Dashboard Preview

![PhonePe Payment Analytics Dashboard](dashboard.png)

---

## 📌 Key Performance Indicators (KPIs)

| Metric | Value | Analytical Significance |
| :--- | :--- | :--- |
| **Total Transactions** | **300K+** *(288K in active period)* | Strong platform volume and payment gateway capacity |
| **Total Transaction Value** | **₹3.47 Billion** *(₹3.0B processed)* | High gross merchandise value (GMV) across digital services |
| **Unique Active Users** | **108,000+** | Broad user base adoption across rural and urban Bharat |
| **Payment Success Rate** | **96.0%** | Exceptional UPI & payment processing pipeline reliability |
| **Peak Usage Period** | **July** | Mid-year financial settlement and seasonal spending high |

---

## 🎯 Project Objective & Business Problem

Digital payment platforms process millions of transactions daily across diverse financial categories (peer-to-peer, merchant payments, bill payments, and loans). Without centralized business intelligence, leadership teams struggle with:
1. Identifying service verticals driving revenue versus high-frequency low-value drop-offs.
2. Tracking transaction failure rates in real-time to avoid customer churn.
3. Understanding demographic adoption across generational cohorts to tailor marketing spend.
4. Pinpointing temporal demand spikes between weekdays and weekends to optimize infrastructure.

**Objective:** Develop an executive-level, interactive Power BI dashboard that transforms raw transaction logs into actionable analytical insights, enabling fintech product managers and business stakeholders to monitor financial health, optimize payment routes, and drive user engagement.

---

## ❓ Business Questions Answered

1. **Transaction Health:** What is the platform's overall payment success rate, and what proportion fails?
2. **Service Contribution:** Which financial service verticals (Loans, Insurance, Money Transfer, Recharge & Bills) generate the highest financial value?
3. **Demographic Breakdown:** How is transaction volume distributed across generational age groups (Gen X, Millennials, Gen Z, Boomers)?
4. **Temporal Patterns:** How do transaction counts and monetary values fluctuate across months (January through December) and between Weekdays vs Weekends?
5. **Customer Concentration:** Who are the top individual power users by transaction value, and how much value do they represent?

---

## 🛠️ Tools & Technologies Used

- **Microsoft Power BI Desktop:** Interactive dashboard design, responsive layout, custom theme styling, and visual canvas composition.
- **Power Query (M Language):** Data cleaning, data type validation, handling missing values, custom date tables, and ETL pipelines.
- **DAX (Data Analysis Expressions):** Dynamic KPI cards, time intelligence, volume ratios, and demographic aggregations.
- **Data Modeling:** Star Schema architecture linking transaction fact tables with date, user demographic, and service dimension tables.
- **Microsoft Excel / OpenPyXL:** Raw dataset auditing and structure verification (`Phonepe-Final-Dataset.xlsx`).

---

## 📐 Data Modeling & DAX Measures

### Key DAX Formulas Implemented:
```dax
// Total Transaction Value
Total Transaction Value = SUM(Transactions[Transaction_Amount])

// Total Transactions Count
Total Transactions = COUNTROWS(Transactions)

// Payment Success Rate
Success Rate % = 
DIVIDE(
    CALCULATE(COUNTROWS(Transactions), Transactions[Payment_Status] = "Successful"),
    COUNTROWS(Transactions),
    0
)

// Month-over-Month (MoM) Growth
MoM Value Growth % = 
VAR CurrentMonthVal = [Total Transaction Value]
VAR PriorMonthVal = CALCULATE([Total Transaction Value], DATEADD('Calendar'[Date], -1, MONTH))
RETURN
DIVIDE(CurrentMonthVal - PriorMonthVal, PriorMonthVal, 0)
```

---

## 📈 Key Analytical Insights & Findings

### 1. ⚡ High Payment Reliability (96% Success Rate)
- Out of all recorded transactions, **96% executed successfully**, demonstrating strong UPI network resilience.
- The 4% failed transactions were concentrated during high-load peak hours, identifying a key target area for server auto-scaling and intelligent retry logic.

### 2. 💰 Loans Vertical Dominates Platform GMV (₹2.4 Billion)
- **Loans generated ₹2.4B**, representing over **70%** of the entire platform's transaction value.
- Insurance (₹0.5B) and Money Transfer (₹0.4B) followed, while Recharge Bills contributed high transaction frequency with minimal monetary value.
- **Strategic Takeaway:** Fintech monetization is heavily anchored in lending products; micro-credit and lending partnerships offer the highest ROI.

### 3. 👥 Gen X & Millennials Drive 74.7% of Platform Activity
- **Gen X (37.4%)** and **Millennials (37.3%)** together form the core backbone of transaction volume and value.
- **Gen Z accounts for 20.74%**, representing high daily frequency (food, transit, micro-recharges) with strong potential for long-term customer lifetime value (LTV).
- **Boomers represent 4.56%**, indicating an untapped opportunity for senior-friendly UX simplification.

### 4. 📅 Weekdays Outperform Weekends (57.85% vs 42.15%)
- Weekday transaction volume (57.85%) significantly outpaced weekend volume (42.15%).
- This reflects heavy corporate salary credits, B2B supplier settlements, utility payments, and commercial trade during business hours.

### 5. 📆 Mid-Year Spending Surge (Peak in July)
- Transactions over time revealed steady acceleration from Q1 to Q2, reaching peak transaction value in **July**, aligned with school/college fee cycles and mid-year commercial purchases.

---

## 💡 Strategic Business Recommendations

1. **Maximize Lending Upsells:** Integrate contextual micro-loan and credit line offerings during high-ticket Money Transfer operations to capitalize on the high-value lending segment.
2. **Automated Instant Retry for 4% Failures:** Deploy automated switchovers to secondary UPI handles (e.g., from bank server A to B) to recoup estimated ₹140M+ in failed transaction value.
3. **Targeted Gen Z Gamification:** Introduce cashback incentives on utility bills and merchant payments for Gen Z users to build habitual retention as their spending power grows.
4. **Weekend Engagement Campaigns:** Launch consumer weekend-exclusive rewards to boost platform activity on Saturdays and Sundays.

---

## 📂 Repository Structure

```
├── PhonePe Payment Analytics Dashboard.pbix   # Full interactive Power BI report file
├── Phonepe-Final-Dataset.xlsx                # Cleaned transaction dataset (300K+ rows)
├── dashboard.png                             # High-resolution dashboard screenshot
└── README.md                                 # Project documentation & analytical report
```

---

## 🚀 How to Run & Explore

1. Download and install [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/).
2. Clone this repository:
   ```bash
   git clone https://github.com/subodhdataworks/PhonePe-Payment-Analytics-PowerBI.git
   ```
3. Open `PhonePe Payment Analytics Dashboard.pbix` in Power BI Desktop.
4. Use the interactive slicers (**Month**, **Payment Status**) to cross-filter across all visuals dynamically.

---

## 👨‍💻 Author

**Subodh Kumar**  
*Data Analyst | Business Intelligence Specialist*  
- 📜 **Certification:** [Microsoft Certified: Power BI Data Analyst Associate (PL-300)](https://learn.microsoft.com/users/SubodhKumar-0850)  
- 💼 **LinkedIn:** [linkedin.com/in/subodh-kumar-3520503ba](https://www.linkedin.com/in/subodh-kumar-3520503ba/)  
- 🐙 **GitHub:** [@subodhdataworks](https://github.com/subodhdataworks)  
- 📧 **Email:** [subodh.dataworks@gmail.com](mailto:subodh.dataworks@gmail.com)

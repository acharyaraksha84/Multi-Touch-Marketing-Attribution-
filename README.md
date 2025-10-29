# 📈 Multi-Touch Marketing Attribution & ROI Engine

## Executive Summary
This project implemented a **Multi-Touch Marketing Attribution & ROI Engine** to monitor and optimize the true performance of marketing campaigns. The core objective was to eliminate **Last-Touch attribution bias**, which causes financial waste and strategic misalignment, by providing managers with real-time, actionable insights.

The solution integrates multi-channel touchpoint data (Web Analytics, Ad Platforms, CRM) with advanced DAX modeling and a predictive score to create an interactive Business Intelligence (BI) dashboard.

## Key Deliverables & Insights
* **Multi-Model Comparison:** Applies and compares four attribution models: **Last Touch, Linear, Time-Decay, and U-Shaped** to show how revenue credit shifts across channels.
* **Value Shift Quantification:** Features a core metric: **% Change (Attributed Revenue: U-Shaped vs. Last Touch)** to directly quantify the project's impact and show previously undervalued channels.
* **Attributed ROI Leaderboard:** Channels are ranked by **Attributed ROI** (U-Shaped model), prioritizing those that generate the highest profit based on their true contribution (e.g., **Organic Search** was identified as the top ROI channel).
* **Proactive Path Flagging:** Integrates a predictive **Conversion Likelihood Score** to immediately flag customers/paths that are **High-Value but currently Low-Likelihood-to-Convert**, triggering targeted actions to rescue 'at-risk' customer paths.
* **CLV vs. CAC Analysis:** A Scatter Plot compares Customer Lifetime Value (CLV) against Customer Acquisition Cost (CAC) for each channel to pinpoint High-Opportunity channels requiring budget scaling.

## Technical Stack
* **Tool:** Power BI (Business Intelligence Dashboard)
* **Modeling:** Advanced DAX (for Attribution Logic) and Power Query 
* **Predictive Model Goal:** Classification (e.g., Logistic Regression or Random Forest) to predict **Conversion Likelihood** (Binary Outcome) after the first 1-2 touchpoints.
* **Security:** Row-Level Security (RLS) implemented to restrict views by Region or Channel Group (protecting sensitive budget data).

## Data Engineering & Modeling
* **Data Sources:** Integrated `Touchpoint Fact Table` (core sequential records), `Cost Data` (financials), and `Customer/Channel Metadata`.
* **Data Model:** A robust **Star Schema** was constructed, with the **Touchpoints** serving as the core Fact Table.
* **Data Stitching:** An ETL process orders raw events by Customer ID and Timestamp to generate the correct Touchpoint sequence and calculate path metrics.
* **Feature Engineering:** Features for the predictive model include **Path Profile** (First/Second Touch Channel), **Time & Length**, and **Initial Spend** attributed to early interaction.

## Future Enhancements
1.  **Budget Automation & Threshold Alerts:** Automatically send alerts when a channel's Attributed ROI drops below a minimum threshold (e.g., $\text{ROI} < 1.0$).
2.  **Time-to-Conversion Prediction:** Integrate a model to estimate *when* the customer will likely convert, enabling better retargeting timing.
3.  **Model Explainability (SHAP):** Incorporate feature-level explainability to show *why* a channel received its assigned credit (e.g., "due to its position as the Second Touch and the customer's High LTV Segment").

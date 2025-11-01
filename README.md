# ServiceNow_CSM_Project3
# ServiceNow CSM | Predictive Customer Retention & Churn Alert (Yokohama PDI)

## Overview
This project simulates **Predictive Intelligence** in ServiceNow CSM.  
When a Customer Case is created/updated, the flow checks complaint keywords, **sentiment**, and **case frequency** to flag **at-risk customers** and alert managers.

## Flow Logic
1. **Trigger:** Customer Case created or updated (for every update)
2. **If (At-Risk):**
   - Short description contains `issue`, `delay`, or `complaint`
   - OR **Sentiment = Negative**
   - OR **Case Count > 3**
3. **Then (High Risk):**
   - **Customer Risk Level = High**
   - **AI Risk Notes** summarize indicators
   - *(Optional)* Send email to Account Manager
4. **Else (Low Risk):**
   - **Customer Risk Level = Low**
   - **AI Risk Notes** = no churn indicators

## Highlights
- Built on **Yokohama PDI** using **Flow Designer** (no code)
- Demonstrates **AI insights** + proactive customer retention
- Works with the same custom **Customer Case** table from CSM Projects 1–2

## Diagram
![Flow](Diagrams/Flow Diagaram.png)

## Example Tests
| Customer | Short Description | Sentiment | Case Count | Result |
|---|---|---:|---:|---|
| John Doe | Repeated complaint about billing delay | Negative | 4 | **High Risk** |
| Maria Lee | Issue with login | Negative | 2 | **Medium/Low** (configurable) |
| Alex Smith | Thanks for the help! | Positive | 1 | **Low Risk** |

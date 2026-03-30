# M&A Data Construction README

## 1. Data Source

The dataset is obtained from Refinitiv Workspace using the Deals Screener module, focusing on mergers and acquisitions (M&A) transactions.

---

## 2. Raw Data Description

The raw M&A dataset is downloaded from Refinitiv Workspace without imposing sample restrictions, covering the full available time span:

- **Time Period:** January 1962 – March 2026  
- **Universe:** Deals  
- **Asset Class:** M&A  

The set of variables included in the raw dataset follows the predefined list in the *M&A Variable Checklist*.

---

## 3. Sample Selection Criteria

The following filters are applied to construct the final analytical sample:

### (1) Deal Status

Include:
- Completed deals  
- Withdrawn deals  

This allows the construction of a treatment and control group, following the empirical strategy in Bena and Li (2014), where withdrawn deals serve as a counterfactual for completed M&A transactions.

---

### (2) Deal Size

- Rank Value Including Net Debt of Target > 5 million USD  

This restriction removes very small transactions and reduces noise in the sample.

---

### (3) Ownership Threshold

- Percentage of Shares Owned after Transaction > 50%  

This ensures that the sample includes only transactions involving a change in corporate control (i.e., majority ownership).

---

### (4) Firm Type

- Target Public Status = Public  

This restriction ensures compatibility with external datasets such as CRSP and Compustat, which primarily cover publicly listed firms.

---

### (5) Time Period

- Date Announced: 1962 Jan – 2026 March  

The sample period is restricted to ensure data consistency and alignment with available financial and innovation datasets.

---

## 4. Purpose of Sample Design

The inclusion of both completed and withdrawn deals enables a quasi-experimental design:

- Completed deals serve as the treatment group  
- Withdrawn deals serve as the control group  

This structure facilitates future difference-in-differences (DiD) analysis to study the causal effects of M&A activity.

---

## 5. Notes

- Only majority acquisitions are retained.  
- Very small deals are excluded to improve data quality.  
- The sample is designed to be mergeable with firm-level financial and market data.  
- Variable definitions and availability are documented in the *M&A Variable Checklist*.


# IPO Data README

## File Location

The IPO dataset is stored in the following directory:

`Documents/Dataset_WS/Raw_Data/IPO.xlsx`

The related M&A data folder is stored separately under:

`Documents/Dataset_WS/Raw_Data/M&A/`

---

## Data Source

The IPO data was collected from **LSEG Workspace Screener** under the **Deals** universe.

To identify IPO transactions, the more appropriate screening criteria are:

- **Issue Type** = IPO  
- **Transaction Status** = Announced + Cancelled  
- **Issuer/Borrower Nation** or **Nation of Headquarters** = United States  
- **Issue Date** = 1962–2026  

These filters are designed to produce a U.S. IPO sample that includes both completed and withdrawn offerings.

---

## Notes on Screening Logic

The IPO sample should **not** use M&A-specific filters such as:

- Rank Value Including Net Debt of Target > 5 million USD  
- Percentage of Shares Owned after Transaction > 50%  
- Target Public Status = Public  

These are appropriate for mergers and acquisitions, but not for IPO screening.

---

## Variable Checklist

For the detailed variable list and export fields, please refer to:

`IPO Variable Checklist`

This checklist contains the specific variables to verify and retain for the IPO dataset.

---

## Output File

The current exported IPO dataset is:

`Documents/Dataset_WS/Raw_Data/IPO.xlsx`



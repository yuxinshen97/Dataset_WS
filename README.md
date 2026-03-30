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


# IPO Data Construction README

## 1. Data Source

The dataset is obtained from Refinitiv Workspace (LSEG Workspace) using the Deals Screener module, focusing on equity issuance transactions, specifically initial public offerings (IPOs).

---

## 2. Raw Data Description

The raw IPO dataset is downloaded from Refinitiv Workspace under the Deals universe, covering the full available time span:

- **Time Period:** January 1962 – March 2026  
- **Universe:** Deals  
- **Asset Class:** Equity  

The set of variables included in the raw dataset follows the predefined list in the *IPO Variable Checklist*.

---

## 3. Sample Selection Criteria

The following filters are applied to construct the final analytical sample:

### (1) Issue Type

Include:
- IPO  

This restriction ensures that the sample only contains initial public offerings, excluding other equity issuance types such as seasoned equity offerings (SEOs), private placements, and other non-IPO transactions.

---

### (2) Transaction Status

Include:
- Announced  
- Cancelled  

This allows the construction of a treatment and control group:

- Announced IPOs serve as completed (successful) offerings  
- Cancelled IPOs serve as withdrawn (unsuccessful) offerings  

This structure follows the standard empirical approach in the IPO literature, where withdrawn IPOs provide a natural counterfactual.

---

### (3) Geographic Restriction

- Issuer/Borrower Nation or Nation of Headquarters = United States  

This restriction ensures consistency with U.S.-focused financial datasets such as CRSP and Compustat.

---

### (4) Time Period

- Issue Date: January 1962 – March 2026  

The sample period is restricted to ensure consistency with available financial and market data.

---

## 4. Purpose of Sample Design

The inclusion of both announced and cancelled IPOs enables a quasi-experimental design:

- Announced IPOs serve as the treatment group  
- Cancelled IPOs serve as the control group  

This structure facilitates empirical analysis of IPO success, withdrawal decisions, and the determinants of capital market access.

---

## 5. Notes

- M&A-specific filters (e.g., deal size, ownership thresholds) are not applicable to IPO data and are therefore excluded.  
- The sample focuses on U.S. IPO activity to ensure compatibility with firm-level financial datasets.  
- Additional filters (e.g., security type or exclusion of special vehicles such as REITs, ADRs, or SPACs) may be applied depending on research design.  
- Variable definitions and availability are documented in the *IPO Variable Checklist*.

---

## 6. File Location

The IPO dataset is stored at:

`Documents/Dataset_WS/Raw_Data/IPO.xlsx`


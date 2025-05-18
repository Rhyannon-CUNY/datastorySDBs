# Data story on DOGE contract terminations on Small Disadvantaged Businesses

**By:** Rhyannon Bartlett-Imadegawa    
**Affiliation:** NYCity News Service  
**Date:** May 2025

---

## Project Summary 

Using extracted data from the centralized federal procurement database, FPDS.gov, this analysis shows that small disadvantaged businesses have disproportionately had contracts terminated between January 20 and May 1 2025. This suggests DOGE's contract cancellations under the second Trump administration is impacted small disadvantaged businesses more compared to the proportion of contracts they have in federal procurement. 

**Read the full story [hyperlink]** 

---

## Data Sources
**DOGE contract termination data (excel)**
  Source: Deltek GovWinIQ  
  Access Method: [download link](https://iq.govwin.com/neo/marketAnalysis/view/Tracking-Terminated-Contracts/8224?researchTypeId=1)  
  Files located in `/data/` folder  
  Approximate volume: 1 sheet, date range spanning January 20 - May 1, 2025  

---

## Methodology

1. **Data extraction and clean up**
   Downloaded the excel file, created a new version where less relevant columns were deleted.  

2. **Filter the data**
   To filter for contract terminations that are more likely to be due to DOGE cost-saving iniatiatives rather than routine contract terminations or due to other reasons, `filtered_df` was created to inlcude only contracts where the modification reason on the FPDS system was "termination for convenience."  

3. **Analysis**
   The python groupby and query functions were used to extract data for self certified small disadvantaged businesses, which encompasses the different socio-economic categories of disadvantaged businesses according to the federal procurement system.

   This dataset was then calculated for the number of contracts that was marked as "terminated for convenience" and the sum of the amount that would have been paid to the business otherwise, `Action Amount ($K)`.

   This methodology and analysis was repeated for a dataset on subcontractors. 

---

## How to Reproduce this Analysis

1. Clone this repository:

   gh repo clone Rhyannon-CUNY/datastorySDBs


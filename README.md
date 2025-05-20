# Data story on DOGE contract terminations on Small Disadvantaged Businesses

**By:** Rhyannon Bartlett-Imadegawa    
**Affiliation:** NYCity News Service  
**Date:** May 2025

---

## Project Summary 

Using data extracted from the centralized federal procurement database, FPDS.gov, by GovWinIQ, this analysis shows that executive orders have had a disproportionate impact in terminating contracts with small disadvantaged businesses between January 20 and May 1 2025 due to executive order. The analysis shows cost-cutting and DEI-dismantling contract cancellations under the second Trump administration is affecting small disadvantaged businesses more compared to the proportion of contracts they have by value with the federal procurement. 

**Read the full story [hyperlink]** 

---

## Data Sources
**DOGE contract termination data (excel)**
  Source: Deltek GovWinIQ  
  Access Method: [download link](https://iq.govwin.com/neo/marketAnalysis/view/Tracking-Terminated-Contracts/8224?researchTypeId=1)  
  Files located in `/data/` folder  
  Approximate volume: 1 sheet for prime contractor awards, 1 sheet for subcontractor awards, date range January 20 - May 1, 2025  
  Source: SBA scorecard  
  Access Method: [download link](https://www.sba.gov/federal-contracting/contracting-data/small-business-procurement-scorecard/scorecard-details) 
  Files located in `/data/` folder  

---

## Methodology

1. **Data extraction and clean up**
   Downloaded the excel file, created a new version where less relevant columns were deleted.  

2. **Filter the data**
   To filter for contract terminations linked to the second Trump administration's executive orders, column data was converted to `/string/` data types, and searched with `/str.contains/` for terms using regex for: "EO", "EOI", and "executive order." This was intended to filter out routine contract terminations and to focus solely on executive orders linked to government efficiency, DEI and other cost-saving iniatiatives of executive orders.
   
   Dataframes were created to only include contracts terminated due to EOIs.    

3. **Analysis**
   The python pandas functions `/groupby/` and `/value_counts/` were used to analyze the share of contracts by executive order with self certified small disadvantaged businesses.  
   Self certified SDBs encompasses the different socio-economic categories of disadvantaged businesses according to the federal procurement system, and was chosen to compare the contract value data with the total federal procurement value data overall.  
   Action Amount was used to calculate the contract value terminated, as the dollar amount associated with the termination of the contract.  

---

## How to Reproduce this Analysis

1. Clone this repository:

   [Rhyannon-CUNY/datastorySDBs](https://github.com/Rhyannon-CUNY/datastorySDBs.git)


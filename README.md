# cmsc408-sp2025-hw8

Homework 8 - World Bank Indicator Analysis

## Content
1. [Homework Description](#homework-description)  
2. [Key Features](#key-features)  
3. [Database Structure and Queries](#database-structure-and-queries)  
4. [How to Install and Run the Project](#how-to-install-and-run-the-project)  
5. [Software Used](#software-used)  
6. [How to Run the Project](#how-to-run-the-project)  

## Homework Description
This project analyzes the World Bank’s WDI country dataset. We begin by filtering out the aggregate entries (regions and country groups) and creating a clean `wdi_country` table of only real countries. From there we explore the data with SQL: counting records, listing unique regions, grouping by income category, and pivoting results into 2‑D tables using CASE statements. We also correct a misclassified country’s income group and calculate percentage breakdowns to show how countries are distributed across regions and income levels. All steps are documented in `report.qmd` and rendered to HTML.

GitHub Repository: [cmsc408-sp2025-hw8-amjadm19](https://github.com/cmsc-vcu/cmsc408-sp2025-hw8-amjadm19)

## Key Features
- **Data Cleaning & Preparation**  
  - Filter World Bank aggregates; create `wdi_country` with only true countries.  
- **Basic Exploration**  
  - Row counts, first‑row previews, and unique region listings.  
- **Aggregation & Grouping**  
  - Count countries by region and income group.  
- **Pivot Tables**  
  - 2‑D views of region vs. income group with CASE statements.  
- **Data Correction**  
  - Update Venezuela’s income group to “High income.”  
- **Percentage Analysis**  
  - Compute percent‑of‑total for each region‑income pairing.  

## Database Structure and Queries
- **Tables**  
  - `world_bank_data.wdi_country` – original WDI data.  
  - `wdi_country` – local copy containing only countries.  
  - HR support tables: `countries`, `regions`, etc.  
- **Sample Queries**  
  - **Task 1:** Count all rows in WDI country table.  
  - **Task 2:** Show first 10 records of `wdi_country`.  
  - **Task 3:** List non‑countries (`Region IS NULL`).  
  - **Task 4:** Create `wdi_country` via `CREATE TABLE … SELECT`.  
  - **Task 5:** Count countries in 2020.  
  - **Task 6–7:** Unique regions and counts per region.  
  - **Task 8–9:** Filter by region (North America) and find Qatar’s region.  
  - **Task 10:** Compare two abbreviation codes.  
  - **Task 11–12:** Aggregate by income group and find missing entries.  
  - **Task 13:** Update misclassified country’s income group.  
  - **Task 14–15:** Count region‑income pairs and pivot to 2‑D table.  
  - **Task 16–17:** Identify region with most low‑income; find peers of MHL.  
  - **Task 18–21:** Generate missing combos, build percentage tables, final pivots.  

## How to Install and Run the Project
1. **Install Python**  
   - Download from [python.org](https://www.python.org/downloads/)  
2. **Install Poetry**  
   - Follow instructions at [python-poetry.org](https://python-poetry.org/docs/)  
3. **Set Up Quarto & SQLTools**  
   - Use the VCU SSG setup guide: <https://vcu-ssg.github.io/ssg-quarto-python-setup/>  
4. **Configure Database Connection**  
   - In `.env`, set your MySQL credentials for `world_bank_data` and HR schema.  

## Software Used
- MySQL (with foreign‑key checks)  
- SQLTools extension (VS Code) or phpMyAdmin  
- Quarto & Jupyter for report rendering  
- Python (for helper scripts)  

## How to Run the Project

1. Run the command: `quarto render` to build and render the project.
2. Open the generated file: `./report.html`
3. View the rendered HTML file in your browser.
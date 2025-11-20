# 💼 Adventure Works Power BI Report

## 1. Project Overview

This repository provides the foundational data model and analytical resources for a comprehensive enterprise-level sales performance analysis system. The structure is built upon a Kimball-style star schema, optimized for efficient querying, reporting, and integration with Business Intelligence (BI) platforms.

The primary objective is to enable detailed reporting on sales metrics, track performance against established targets, and facilitate deep-dive analysis across product lines, sales territories, and individual salesperson contributions.

## 2. Data Architecture and Structure

The data model consists of one central fact table and multiple surrounding dimension tables. All source files are provided in **Tab-Separated Values (TSV)** format.

### 2.1 Fact Tables

| File Name | Description | Key Relationships | Metrics / Attributes |
| :--- | :--- | :--- | :--- |
| `Sales.csv` | Transactional data detailing every sales event. | Product, Reseller, Employee, Region | Quantity, Unit Price, Sales Amount, Cost |
| `Targets.csv` | Monthly sales quota targets established for individual employees. | Employee, Date | Target Sales Amount |

### 2.2 Dimension Tables

| File Name | Description | Role |
| :--- | :--- | :--- |
| `Product.csv` | Hierarchical product information (Category, Subcategory, Color). | Contextual attributes for sales events. |
| `Reseller.csv` | Details on the third-party distributors and partners. | Contextual attributes for sales events. |
| `Salesperson.csv` | Employee details, including title and contact information. | Contextual attributes for sales events. |
| `Region.csv` | Definitions of sales territories (Region, Country, Group). | Geographical segmentation for sales reporting. |
| `SalespersonRegion.csv` | Bridge table defining many-to-many relationships between Salespeople and Territories. | Facilitates complex attribution reporting. |

## 4. Key Analytical Capabilities

The resulting data model enables critical business queries, including:

* **Performance Measurement:** Actual Sales vs. Budgeted Targets (`Sales` joined with `Targets`).
* **Geographic Analysis:** Cross-regional performance comparisons and identification of high-growth territories.
* **Salesperson Productivity:** Tracking individual contribution, especially in scenarios involving shared regions (using `SalespersonRegion.csv`).
* **Profitability Analysis:** Calculating and analyzing Gross Margin across product lines and resellers.

## 5. Visual Representation

The analytical output is typically presented in a professional dashboard format.

[Link to my Dashboard](https://app.powerbi.com/links/jtVVyyWfWb?ctid=3ea7c128-c601-4479-a003-e14d00c0b5cb&pbi_source=linkShare&bookmarkGuid=5f3630f3-5383-4070-9f2a-78991deff800)

<img width="1267" height="672" alt="Screenshot 2025-11-20 145708" src="https://github.com/user-attachments/assets/ef1ae5a0-a5b7-48b6-895f-20f37f2f1bf6" />

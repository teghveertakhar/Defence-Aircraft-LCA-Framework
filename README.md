# Defence-Aircraft-LCA-Framework

An Excel-based, scalable, and reproducible life cycle assessment (LCA) framework for frontline defence aircraft.

This repository contains a workbook developed from a dissertation case study on the **Eurofighter Typhoon**, but structured so it can be adapted to **any frontline combat aircraft** when detailed data is unavailable or partly classified.

## Purpose

The workbook provides a transparent front-end for modelling cradle-to-grave aircraft impacts across three life-cycle phases:

- **Manufacturing**
- **Operations**
- **End-of-life**

It is designed to work alongside **openLCA** and **ecoinvent**, using exported impact factors to calculate results in a structured and updateable way.

## Core features

- Modular aircraft inventory structure
- Assembly- and material-based modelling
- Parameterised operational fuel-burn model
- Support for proxy and partial data
- Explicit data-quality classification:
  - Measured
  - Estimated
  - Proxy
  - Assumed
- Automatic sensitivity and uncertainty propagation
- Alternative fuel scenario comparison
- Transparent formulas and validation checks
- Fleet-level roll-up capability for defence organisations

## Workbook file

- `defence aircraft lca framework.xlsx`

## Workbook structure

The workbook contains the following sheets:

1. `README`
2. `Aircraft_Input`
3. `Assemblies`
4. `Materials`
5. `Fuel_Scenarios`
6. `Data_Quality`
7. `OpenLCA_Factors`
8. `Calc_Materials`
9. `Calc_Manufacturing`
10. `Calc_Operations`
11. `Calc_EOL`
12. `Sensitivity`
13. `Results`
14. `Checks`
15. `Fleet_Register`

## How the workflow works

### 1. Enter aircraft-level inputs
Use `Aircraft_Input` to define the aircraft, variant, engine parameters, life, and fleet context.

### 2. Enter or estimate assembly masses
Use `Assemblies` to enter known masses, or mass shares where only partial information exists.

### 3. Enter material splits
Use `Materials` to define the composition of each assembly.

### 4. Define fuel scenarios
Use `Fuel_Scenarios` for Jet-A1 and any alternative fuel blends such as HEFA.

### 5. Import openLCA / ecoinvent factors
Paste or map exported impact factors into `OpenLCA_Factors`.

### 6. Review calculated outputs
The workbook automatically calculates:

- Material masses
- Manufacturing impacts
- Operational impacts
- End-of-life impacts
- Low / base / high ranges
- Scenario comparisons
- Fleet-level totals

### 7. Review checks
Use `Checks` to verify consistency, completeness, and data integrity.

## Method boundary

The workbook is aligned to the dissertation boundary and includes:

- Manufacturing
- Operations
- End-of-life

The following are intentionally excluded in the current framework:

- Maintenance
- Munitions / payloads
- Infrastructure

## Operational model basis

The operational phase is based on a parameterised fuel-burn model using:

- number of engines
- dry TSFC
- afterburning TSFC
- dry thrust fraction
- afterburner thrust fraction
- afterburner time fraction
- lifetime flight hours

This allows the framework to remain usable even when full mission fuel-burn data is unavailable.

## Data quality and uncertainty

Every major input should be tagged as one of the following:

- **Measured**: direct aircraft-specific value
- **Estimated**: engineering estimate based on aircraft-specific evidence
- **Proxy**: analogue from a comparable aircraft or subsystem
- **Assumed**: placeholder or rule-of-thumb where better evidence is unavailable

These classifications feed into the workbook's uncertainty logic and improve traceability.




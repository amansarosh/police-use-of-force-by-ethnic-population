# Police Use of Force and County Diversity in Washington State

## Project Overview

This project investigates the relationship between police use of force and demographic diversity across Washington State counties. By combining official police reporting data with U.S. Census demographic information, we examine whether patterns in law enforcement practices correlate with community racial composition and diversity levels — and whether those patterns hold up across multiple angles of analysis.

The findings are presented as an **interactive Quarto dashboard** covering three research questions, with visualizations for each.

---

## Research Questions

1. **How do demographic characteristics, such as a county's diversity, relate to patterns of police use of force across Washington State?**
2. **How are differences in racial and ethnic population composition across counties associated with variation in police use-of-force rates?**
3. **To what extent do policing activity levels (such as call-for-service volume) explain differences in use-of-force incidents between counties?**

---

## Datasets

### WADEPS — Washington Data Exchange for Public Safety

- **Source:** [wadeps.org](https://wadeps.org/home/dashboard/)
- **Provided by:** Washington Association of Sheriffs and Police Chiefs (WASPC)
- **Coverage:** 47 law enforcement agencies across Washington State, 2025–2026
- **Key variables:** Uses of Force, Calls for Service, County
- **Note:** Data is self-reported by agencies; definitions of "use of force" may vary across departments

### Diversity and Disparities — Brown University

- **Source:** [s4.ad.brown.edu](https://s4.ad.brown.edu/projects/diversity/index.htm)
- **Authors:** Barrett Lee, John Iceland, and Gregory Sharp
- **Funding:** National Institutes of Health, Russell Sage Foundation, Brown University
- **Coverage:** U.S. county-level racial/ethnic demographics from Census data (1980–2010)
- **Key variables:** Population shares by race/ethnicity (White, Black, Hispanic, Asian/Pacific Islander, Other), Entropy Diversity Index (`E10`)

---

## Dashboard Structure

| Tab                                | Content                                                              |
| ---------------------------------- | -------------------------------------------------------------------- |
| **1.1 Topical Overview**           | Background, research questions, ethics & limitations                 |
| **1.2 Data Context**               | Dataset descriptions and sources                                     |
| **1.3 Group Information**          | Team member profiles                                                 |
| **Graphical Overview**             | Summary value boxes + interactive bar chart of force rates by county |
| **Q1: Diversity & Force Rate**     | Scatter plot of diversity index vs. force per 100k residents         |
| **Q2: Racial Composition & Force** | Stacked bar chart of racial composition ordered by force rate        |
| **Q3: Policing Activity & Force**  | Scatter plot of call volume vs. force-per-call rate; summary table   |
| **Methods & Conclusion**           | Summary of findings, R functions used, and limitations               |

---

## Key Findings

- **Diversity index alone was a weak predictor** of use-of-force rates (correlation ≈ 0). Counties like Thurston and Adams were high-force outliers regardless of their diversity score.
- **Racial composition showed more signal** — counties with larger Hispanic population shares tended to appear higher in force rates, while counties with larger white population shares trended lower.
- **Call volume did not explain force rates** — King County handles the most calls but has a low force-per-call rate, while smaller counties like Adams and Thurston had much higher rates despite fewer calls.

---

## Limitations

- Data is **self-reported** by police departments — underreporting is possible
- Only **25 of 39 Washington counties** were included after joining both datasets
- **2010 Census demographics** were matched with 2025–2026 policing data — population composition has shifted since then

---

## How to Run

1. Clone this repository
2. Place the following files in a `data_clean/` folder:
   - `Counties.csv` (Brown University diversity data)
   - `Rate_of_Force_Data_R_1771113615253.csv` (WADEPS force data)
3. Open the `.qmd` file in RStudio and render with Quarto

**Required R packages:**

```r
install.packages(c("readr", "dplyr", "stringr", "ggplot2",
                   "knitr", "tidyr", "plotly", "scales"))
```

---

## Team

**INFO 201 B — University of Washington, Seattle**

| Name              | School                     | Email                                     |
| ----------------- | -------------------------- | ----------------------------------------- |
| Aman Sarosh       | The Information School, UW | [asarosh@uw.edu](mailto:asarosh@uw.edu)   |
| Brandon Lay       | The Information School, UW | [bndonlay@uw.edu](mailto:bndonlay@uw.edu) |
| Gabriel Aritchita | The Information School, UW | [gabe1124@uw.edu](mailto:gabe1124@uw.edu) |

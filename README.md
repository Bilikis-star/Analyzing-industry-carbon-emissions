                                # Analyzing Industry Carbon Emissions

                                       Project Overview

This project uses SQL to analyze product carbon footprints across industry groups, identifying the number of unique companies and comparing total carbon footprints using the most recent year in the dataset.

                                      ## Project Objective

* Count unique companies in each industry group.
* Calculate total carbon footprint by industry group.
* Filter records to the most recent year in the database.
* Rank industry groups from highest to lowest total carbon footprint.

                                      ## Tools and Skills

* SQL
* Aggregate functions using 'SUM()'
* Unique company counts using 'COUNT(DISTINCT)'
* Data filtering using 'WHERE' and 'MAX()'
* Grouping using 'GROUP BY'
* Sorting using 'ORDER BY'
* Numerical rounding using 'ROUND()'

                                        ## Key Findings

* Materials: recorded the highest total carbon footprint at 107,129.0 across 3 companies.
* Capital Goods: ranked second with 94,942.7 across 2 companies.
* Technology Hardware & Equipment: had the highest number of companies, with 4, and a total carbon footprint of 21,865.1.
* Food, Beverage & Tobacco: recorded a total carbon footprint of 3,161.5 across 1 company.
* Commercial & Professional Services: recorded 740.6, while Software & Services: had the lowest total at 690.0.

                                         ## Conclusion

The analysis shows substantial differences in total product carbon footprints across industry groups. Materials and Capital Goods recorded the highest totals in the dataset, while Software & Services recorded the lowest. SQL aggregation, filtering, and sorting made it possible to compare industry-level emissions and identify the groups with the largest reported footprints.

## SQL Query  
  ```sql                               
SELECT industry_group,
       COUNT(DISTINCT company) AS num_companies,
       ROUND(SUM(carbon_footprint_pcf), 1) AS total_industry_footprint
FROM product_emissions
WHERE year IN (SELECT MAX(year) FROM product_emissions)
GROUP BY industry_group
ORDER BY total_industry_footprint DESC;
```



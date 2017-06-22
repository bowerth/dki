---
layout: curriculum
title: Analytical Visualisation
byline: Definition of analytical visualisation in the Organisation's context
---

## OECDplot

{% include rmarkdown_fragment/oecdplot.html %}


## Scoping

### Use Cases

Effective visualisation helps users in reasoning about data and evidence:

- data quality check
- comparison of analytical results
- internal communication
- reporting for data dissemination (e.g. "country notes")

### Requirements

Producing visualisations for analytical purpose shall be:

- cheap: faster to create from statistical tool than exporting data to use external tool
- intuitive: native function implementation, examples, documentation
- flexible: allow user to experiment with different mappings and representations

### Current Tools

Software tools already in use by creators of data analysis:

- Graph for MS Excel: execute VBA macros on plots defined in MS Excel to standardise format (for publication)
- base plotting systems of statistical tools in use (Matlab, SAS, Stata, R etc.)
- enhanced plotting systems for specific tools, e.g. [ggplot](http://ggplot2.org/) for R

### Potential Developments

Areas where currently employed tools have shortcomings:

- produce graphics for publication together with data analysis
- cover static chart types that are not available from by MS Excel (e.g. treemap)
- interactive/dynamic content for websites (HTML + JavaScript)

<!-- See also [Algorithm Library]({{ site.url }}/algorithm) -->



























































































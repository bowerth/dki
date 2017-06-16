---
layout: curriculum
title: Analytical Visualisation
byline: Definition of analytical visualisation in the Organisation's context
---

# ggplot2 for OECD.Graph 

## Create a `legend width` parameter

- `Question`: the objective is to align the legend with the plot area, i.e. the width of the grey legend box background shall be identical to the width of the plot area?

Examples from [OECD Science, Technology and Industry Scoreboard 2015](http://www.oecd-ilibrary.org/sites/sti_scoreboard-2015-en/01/01/index.html?itemId=/content/book/sti_scoreboard-2015-en&mimeType=text/html&_csp_=8f756a767b3c534ebe0996c66bc099bd)

Figure 1 **Labour productivity growth based on hours worked, total economy level, 2001-14**

*Average annual growth rates in percentage points*

<img src="http://www.oecd-ilibrary.org/sites/sti_scoreboard-2015-en/images/graphics/g1-01.gif" />

Source: OECD, Productivity Database, http://www.oecd.org/std/productivity-stats, May 2015.

**Statlink** http://dx.doi.org/10.1787/888933272766

**Figure 2** GDP per capita growth and GDP per person employed growth in the BRIICS and the OECD, 2002-07 and 2009-14

*Average annual growth rates in percentage points*

<img src="http://www.oecd-ilibrary.org/sites/sti_scoreboard-2015-en/images/graphics/g1-02.gif" />

Source: OECD, Productivity Database, http://www.oecd.org/std/productivity-stats, May 2015. See chapter notes.

**Statlink** StatLink http://dx.doi.org/10.1787/888933272771


Based on following examples, this can be implemented using the [ggplot2 extension mechanism](https://github.com/tidyverse/ggplot2/blob/master/vignettes/extending-ggplot2.Rmd):

- [stackoverflow: How to set legend height to be the same as the height of the plot area?](https://stackoverflow.com/questions/29749661/how-to-set-legend-height-to-be-the-same-as-the-height-of-the-plot-area)
- [stackoverflow: How can I make the legend in ggplot2 the same height as my plot?](https://stackoverflow.com/questions/19214914/how-can-i-make-the-legend-in-ggplot2-the-same-height-as-my-plot/29783981#29783981)


## Create a specific look for the line symbol in legend

- `Question`: please provide additional information on the meaning of "specific look"

ggplot2 picks up the information from line type and line color, see example at [report_rs_afr_cmr.html](https://oecd-ctp.github.io/cn-rs/report_rs_afr_cmr.html)

<img src="https://oecd-ctp.github.io/cn-rs/figures/cmr/taxgdp-plot-1.svg" width="75%" />


## Display a Y axis title at a correct position

- `Question`: does this mean placing 90 degrees rotated y-axis title between main plot title and plot area?

See examples from http://dx.doi.org/10.1787/888933437487

<img src="http://rdata.work/cneo2016/articles/assets/img/eo2016-can1.svg" width="75%" />


## Adding Custom pie labels

- `Question`: please provide examples

When using the `geom_text` geom in ggplot2, the position values may need to be calculated as cumulative sum, see [ggplot, facet, piechart: placing text in the middle of pie chart slices](https://stackoverflow.com/questions/16184188/ggplot-facet-piechart-placing-text-in-the-middle-of-pie-chart-slices)

<img src="https://i.stack.imgur.com/f8VgK.png" />

This is identical for area charts when text labels shall be shown at the center

<img src="https://oecd-ctp.github.io/cn-rs/figures/cmr/taxper-area-plot-1.svg" width="75%" />

~~~
labelposition = ifelse(year==2014, cumsum(value) - 0.5*value, NA)
~~~

|tax    |cou | year|   value|taxlegend                 | labelvalue| labelposition|
|:------|:---|----:|-------:|:-------------------------|----------:|-------------:|
|1100   |ZAF | 2014| 32.0736|Personal income tax       |         32|      16.03680|
|1200   |ZAF | 2014| 17.2286|Corporate income tax      |         17|      40.68790|
|4000   |ZAF | 2014|  5.0634|Property taxes            |          5|      51.83390|
|5111   |ZAF | 2014| 24.2665|VATs                      |         24|      66.49885|
|5000X  |ZAF | 2014| 16.7262|Taxes on goods & services |         17|      86.99520|
|OTHTAX |ZAF | 2014|  4.6417|Other taxes               |          5|      97.67915|


## Implementing a radar Plot

- `Question`: is the existing extension for ggplot2 [ggradar](http://www.ggplot2-exts.org/ggradar.html) and the `radar.plot` function of the [plotrix package](https://cran.r-project.org/web/packages/plotrix/index.html) insufficient? see [radar-examples](http://boot.rdata.work/contrib/radar-example/)

<img src="http://boot.rdata.work/contrib/radar-example/fig/ggradar-examples-1.svg" width="75%" />


## Implementing a High Low Plot

- `Question`: do you mean the "High-Low Lines" Chart Element of Excel?

<img src="http://peltiertech.com/images/2015-10/2013HiLoLinesRibbon.png" />

<!-- https://cran.r-project.org/web/packages/tidyquant/vignettes/TQ04-charting-with-tidyquant.html     -->


## Creation of a second y axis for ggplot2 

- `Question`: did you consider using latticeExtra or base graphics? assuming
  that the plotting functions are not primarily designed for interactive use but
  instead receive parameters from XML templates, a graphical system that can
  work with all three graphing engines (base graphics, lattice and ggplot2) may
  be more flexible. A more detailed explanation can be found
  at
  [Why I don't use ggplot2](https://simplystatistics.org/2016/02/11/why-i-dont-use-ggplot2/).
  A technical implementation that allows unifying the themes of all three
  graphic engines is available from the pander package,
  see
  [Unify R plots with pander](https://www.r-bloggers.com/unify-r-plots-with-pander/).

~~~
evals('hist(df$hp, main = "Histogram in base R")')
~~~

<img src="https://i1.wp.com/1.bp.blogspot.com/-6NUGDPBoaOs/UEXeBEYb07I/AAAAAAAAK7k/CDKu2Ol3mm8/s320/evals-base.png" />

~~~
evals('histogram(df$hp, main = "Histogram with lattice")')
~~~

<img src="https://i1.wp.com/2.bp.blogspot.com/-y_fuvJ8_FHA/UEXeCRrEcCI/AAAAAAAAK7s/MAagxxz9sM4/s320/evals-lattice.png" />

~~~
evals('ggplot(df) + geom_histogram(aes(x = hp), binwidth = 50) + opts(title = "Histogram with ggplot2")')
~~~

<img src="https://i2.wp.com/1.bp.blogspot.com/-AoxM4iW19dY/UEXeDt1jeqI/AAAAAAAAK70/Fds45XekY30/s320/evals-ggplot2.png" />

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

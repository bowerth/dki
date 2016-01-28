---
layout: curriculum
title: Python
byline: Candidate for algorithm library language
---

## About

[Python](https://www.python.org) is "a widely used general-purpose, high-level programming language" ([en.wikipedia.org](https://en.wikipedia.org/wiki/Python_%28programming_language%29)). Commercial support is offered by [activestate.com](http://www.activestate.com/support/commercial)

Python has a quite gentle learning curve, and a long history in an extremely wide range of applications, including especially:

- the web, from running websites and webservices to building documents and charts for the web;
- Big / Smart Data, and data analysis in general, including GIS.

### Language Design

Besides, Python is per se a language that encourages writing legible code, making it easier to maintain, share and transmit, which is a key asset for the Organisation's knowledge management. Python makes it easy to write reusable code and custom libraries, which is in line with the idea to provide a common statistical toolset for the Organisation. Another key asset is that Python comes with an extremely vast set of tools - below are some examples.

The main weakness of Python would be that it is slower than compiled languages like C or Java. But this is somewhat irrelevant:

- because most Python libraries are themselves written in some compiled, fast language;
- Python has many other assets mentioned above that other languages considered as faster do not have: they tend to be way harder to learn and to write legible and maintainable code with; and if they also have a wide range of applications, they have not proven to be the most suited languages for easy-access webservices and data analysis in the scientific community;

- much more resources could be saved by streamlining data processes in the Organisation than by choosing a language for its supposed better performances.

### Ecosystem

The Python Standard Library itself is extremely rich: https://docs.python.org/3/library/index.html

Scrapy is a Python library to extract data from websites:
- website http://scrapy.org/
- commercial support http://scrapy.org/support/

PostGIS is a SQL (PostgreSQL) database specifically tailored for geographical data:
- website http://postgis.net/
- French community http://www.postgis.fr/
- Wikipedia https://en.wikipedia.org/wiki/PostGIS
- commercial support for [postgis](http://postgis.net/support) and [qgis](https://www.qgis.org/fr/site/forusers/commercial_support.html)

PostGIS can serve as a database backend for many GIS software packages, including ArcGIS and QGIS. It has Python and R bindings.

### Reporting and BI

At the other end of the tool set, there are Django and Bokeh.

Django is "a high-level Python Web framework [...] built by experienced developers, it takes care of much of the hassle of Web development." GeoDjango is the geographic web framework of choice to work with PostGIS and Django.

- Django website https://www.djangoproject.com/
- GeoDjango website https://docs.djangoproject.com/en/dev/ref/contrib/gis/
- Wikipedia https://en.wikipedia.org/wiki/Django_%28web_framework%29
- commercial support for django by [revsys.com](http://www.revsys.com/services/django) and [divio.com](http://www.divio.com/en/commercial-support)

[Bokeh](http://bokeh.pydata.org/en/latest) is "a Python interactive visualization library that targets modern web browsers for presentation". Commercial support by [continuum.io](https://www.continuum.io) ([Atish Singh](mailto:asingh@continuum.io))

Bokeh is more versatile and powerful than JavaScript libraries like D3. First, because it provides a high level interface so the code involved is much more compact; and also because it allows a lot bigger share of the workflow to remain within the same platform - Python - from data mangling to web display, including computations. No CSS, no JS involved (or very few, in specific cases).

About computations, there is between Scrapy / PostGIS and Django / Bokeh a bunch of tools to mangle and analyse the data.

### Machine Learning and Data Analysis

- [Spark](http://spark.apache.org) provides a high level interface (Python or R) to distributed Map-Reduce (Hadoop-like) jobs. Commercial support by [databricks]( https://databricks.com) or [cloudera](https://www.cloudera.com/content/www/en-us/products/apache-hadoop/apache-spark.html)
- [Scikit-learn](http://scikit-learn.org) is a Python library for machine learning:
- [Statsmodels](http://statsmodels.sourceforge.net) is a Python library for statistics and econometrics (it integrates with Stata). Commercial support by [continuum.io](https://www.continuum.io)
- [Pandas](http://pandas.pydata.org) is a Python library for data analysis and modelling, well suited for time series. Commercial support by [continuum.io](https://www.continuum.io)
- 2

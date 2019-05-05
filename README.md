# Data-Wrangling
Real-world data rarely comes clean. Using Python and its libraries, you will gather data from a variety of sources and in a variety of formats, assess its quality and tidiness, then clean it. This is called data wrangling. You will document your wrangling efforts in a Jupyter Notebook, plus showcase them through analyses and visualizations using Python (and its libraries) and/or SQL. </br>

Data wrangling is the Process of **Gathering**, **Assessing** and **Cleaning** Data before analysing it, visualisation or build predictive models using machine learning.

## Properties of Data
1. **Quality**:  Low quality data is commonly referred to as dirty data. Dirty data has issues with its content.
    - Common data quality issues include:
      1. Missing data
      2. Invalid data
      3. Inaccurate data
      4. Inconsistent data

2. **Tidiness**: Untidy data is commonly referred to as "messy" data. Messy data has issues with its structure.</br>
    [More information about Tidy Data](http://www.jeannicholashould.com/tidy-data-in-python.html)</br>
    [Jeff Leek: Non-tidy data](https://simplystatistics.org/2016/02/17/non-tidy-data/)


**Dataset**

TI am going to wrangle a dataset called **armenian-online-job-postings**. This dataset has 19,000 online job posts from 2004 to 2015 that were posted through an Armenian human resource portal. It is hosted on Kaggle.

- The issues that identified in this dataset:
    - Nondescriptive column headers
    - Missing values (i.e. NaNs)
    - Inconsistent representations of values, specifically "As soon as possible" and other similar values to "ASAP" in the StartDate column for this dataset
    - A messy (i.e. untidy) dataset

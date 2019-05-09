## Table of Content

- <b>Data-Wrangling</b>
   1. [Gather](#) 
        - [File Structure Formats]()
            - [Flat files]()
            - [HTML files]()
            - [JSON files]()
            - [HTML files]()
            - [TXT files]()
            - [Relational database files]()

   2. [Assess](#)
     
   3. Clean](#)
      
=========================

# Data-Wrangling
Real-world data rarely comes clean. Using Python and its libraries, you will gather data from a variety of sources and in a variety of formats, assess its quality and tidiness, then clean it. This is called data wrangling. You will document your wrangling efforts in a Jupyter Notebook, plus showcase them through analyses and visualizations using Python (and its libraries) and/or SQL. </br>

Data wrangling is the Process of **Gathering**, **Assessing** and **Cleaning** Data before analysing it, visualisation or build predictive models using machine learning.

## Gathering
Gathering data is the first step in data wrangling. Gathering data varies from project to project. Sometimes you're just given data, or pointed to it. Sometimes you need to search for the right data for your project. 

### File Structure Formats
- The followings are the common files
    1. Flat files (e.g. CSV and TSV)
    2. HTML files
    3. JSON files
    4. TXT files
    5. Relational database files
    
#### Flat File Structure

Flat files contain tabular data in plain text format with one data record per line and each record or line having one or more fields. These fields are separated by delimiters, like commas, tabs, or colons.

**- Advantages of flat files include:**</br>
    -They're text files and therefore human readable.
    -Lightweight.
    -Simple to understand.
    -Software that can read/write text files is ubiquitous, like text editors.
    -Great for small datasets.
**- Disadvantages of flat files include:**
    -Lack of standards.
    -Data redundancy.
    -Sharing data can be cumbersome.
    -Not great for large datasets (see "When does small become large?" in the Cornell link in More Information).
    
Flat Files in Python
Pandas has one main function for parsing flat files and it is read_csv.

#### HTML File Structure/ Web Scraping
**Web Scraping** is extracting data from website using code. This data is stored in a format called HTML. There are two ways, and they are done programmatically which is best for scalability and reproducibility. </br> 
- The two main ways to work with HTML files are:
    - Saving the HTML file to your computer (using the [Requests](https://2.python-requests.org//en/master/) library for example) library and reading that file into a [BeautifulSoup constructor](https://www.crummy.com/software/BeautifulSoup/)
    - Reading the HTML response content directly into a BeautifulSoup constructor (again using the Requests library for example)

**Beautiful Soup**
- Beautiful Soup is a Python library designed for quick turnaround projects like screen-scraping. Three features make it powerful:
    -Beautiful Soup provides a few simple methods and Pythonic idioms for navigating, searching, and modifying a parse tree: a toolkit for dissecting a document and extracting what you need. It doesn't take much code to write an application
    -Beautiful Soup automatically converts incoming documents to Unicode and outgoing documents to UTF-8. You don't have to think about encodings, unless the document doesn't specify an encoding and Beautiful Soup can't detect one. Then you just have to specify the original encoding.
    -Beautiful Soup sits on top of popular Python parsers like lxml and html5lib, allowing you to try out different parsing strategies or trade speed for flexibility.


The first thing you need to do is to make the soap. That means passing the pathto your HTML file into a file handles, then passing that fikle into the Beatutful Soup constructor; after importing the Beautiful library. 
</br>
Here is the Code...
```
from bs4 import BeautifulSoup

with open("index.html") as file:
    soup = BeautifulSoup(file, 'lxml')

soup = BeautifulSOup(""<html>data</html>)

``` 

This is a code to download one file. To download all files, we need to put this code in a loop. See ![Loop.ipynb](loop.ipynb) 

#### JSON files

#### TXT files

#### Relational database files

---------------------------------------------------

## Assessing
### Properties of Data
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


--------------------------------------------------------

## Cleaning: Improving Quality and Tidiness
**Improving Tidiness**
Improving tidiness means transforming the dataset so that each variable is a column, each observation is a row, and each type of observational unit is a table. There are special functions in pandas that help us do that.
**Programmatic Data Cleaning Process**
- The programmatic data cleaning process:
    - **Defining** means defining a data cleaning plan in writing, where we turn our assessments into defined cleaning tasks. This plan will also serve as an instruction list so others (or us in the future) can look at our work and reproduce it.
    - **Coding** means translating these definitions to code and executing that code.
    - **Testing** means testing our dataset, often using code, to make sure our cleaning operations worked.
    
   [Data Carpentry: Copying Objects vs. Referencing Objects in Python](https://datacarpentry.org/python-ecology-lesson/03-index-slice-subset/)

# Wrangling vs. EDA vs. ETL
**exploratory data analysis (EDA)**> is an analysis approach that focuses on identifying general patterns in the data, and identifying outliers and features of the data that might not have been anticipated.

**Data wrangling** is about gathering the right pieces of data, assessing your data's quality and structure, then modifying your data to make it clean. But the assessments you make and convert to cleaning operations won't make your analysis, viz, or model better, though. The goal is to just make them possible, i.e., functional.

**EDA** is about exploring your data to later augment it to maximize the potential of our analyses, visualizations, and models. When exploring, simple visualizations are often used to summarize your data's main characteristics. From there you can do things like remove outliers and create new and more descriptive features from existing data, also known as feature engineering. Or detect and remove outliers so your model's fit is better.</br>

In practice, wrangling and EDA can and often do occur together.

**ETL**
Extract-transform-load process(ETL) differs from data wrangling in three main ways:
  1. The users are different
  2. The data is different
  3. The use cases are different </br>
[Data Wrangling Versus ETL: What’s the Difference?](https://tdwi.org/articles/2017/02/10/data-wrangling-and-etl-differences.aspx) by Wei Zhang explains these three differences well

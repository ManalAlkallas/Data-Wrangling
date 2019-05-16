
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

**Source: Downloading Files from the Internet**</br>
**HTTP**, the Hypertext Transfer Protocol, is the language that web browsers (like Chrome or Safari) and **web servers** (basically computers where the contents of a website are stored) speak to each other. Every time you open a web page, or download a file, or watch a video, it's HTTP that makes it possible.</br>

- HTTP is a request/response protocol:
   - Your computer,i.e the client, sends a request to a server for some file. **GET** is the name of the HTTP **request** method (of which there are multiple) used for retrieving data.
   - The web server sends back a response. 

**Source: APIs (Application Programming Interfaces)**</br>
API can let you access data from the internet in a reasonably easy manner. TWitter, Facebook, Insttttagram all have APIs. There are tons of open sources APIs. [MediaWiki](https://www.mediawiki.org/wiki/API:Main_page#A_simple_example), which is a popular API for Wikipedia, is open source.

#### JSON files
- JSON is specially great for respresenting and accessing complicated data hierarchies. JSON is build on two key structures:
   - JSON Object: which are a collection of key value pairs. Objects are surrounded by curly braces{}. In Python, JSON objects are interpreted as Dictionaries. 
   - JSON Array: which is an ordered list of values. Square brackets denote an array[]
   
**JSON object keys must be strings. The values for both JSON objects and arrays can be any valid JSON data Type (a string, number, Boolean, object, array or null )**
   
```
JSON arrays  - Python lists
JSON objects - Python dictionaries
```
   

#### TXT files

#### Relational database files

---------------------------------------------------

## Assessing
### Properties of Data
1. **Quality**:  (content issues) Low quality data is commonly referred to as dirty data. Dirty data has issues with its content.
    - Data Quality Dimenions: 
      1. Completeness: do we have all of the records that we should? Do we have missing records or not? Are there specific rows, columns, or cells missing?
      2. Validity: we have the records, but they're not valid, i.e., they don't conform to a defined schema. A schema is a defined set of rules for data. These rules can be real-world constraints (e.g. negative height is impossible) and table-specific constraints (e.g. unique key constraints in tables).
      3. Accuracy: inaccurate data is wrong data that is valid. It adheres to the defined schema, but it is still incorrect. Example: a patient's weight that is 5 lbs too heavy because the scale was faulty.
      4. Consistency: inconsistent data is both valid and accurate, but there are multiple correct ways of referring to the same thing. Consistency, i.e., a standard format, in columns that represent the same data across tables and/or within tables is desired.
  

2. **Tidiness**: (i.e. structural issues) or "messy" data. Messy data has issues with its structure.</br>
   Tidy Data means: 
         - Each variable forms acolumn
         - Each observation forms a row
         - Each observational unit forms a table
         
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

Cleaning your data is the third step in data wrangling. It is where you fix the quality and tidiness issues that you identified in the assess step. </br>
**- Data Cleaning Process**
 The very first thing to do before any cleaning occurs is to make a **copy** of each piece of data.
      ```
      df_clean = df.copy()
      ```
**- Programmatic Data Cleaning Process**      
   1. **Define**  means defining a data cleaning plan in writing, where we turn our assessments into defined cleaning tasks. This plan will also serve as an instruction list so others (or us in the future) can look at our work and reproduce it.
   2. **Coding** means translating these definitions to code and executing that code.
   3. **Testing** means testing our dataset, often using code, to make sure our cleaning operations worked.
   
**- Logical steps for data cleaning**
      1. Address Data Quality
      **Completeness Issues**: to find the missing data if possible. **Imputing** means filling in missing data values with other values, using some appropriate method. Here is more information on the topic of imputation: [Wikipedia: Imputation](https://en.wikipedia.org/wiki/Imputation_(statistics))
      2. **Tidiness** (Structure issue): Improving tidiness means transforming the dataset so that each variable is a column, each observation is a row, and each type of observational unit is a table. 
      3. **Quality**
  
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

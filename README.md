## Table of Contents
- [Installation](#install)
- [Project Motivation](#motivate)
- [File Descriptions](#describe)
- [Licensing, Authors, and Acknowledgements](#acknowledge)
- [Results](#result)

<a id='install'></a>
### Installation
1. Python 3.6 and latest from [here](https://www.python.org/downloads/)
2. Anaconda distribution of Python from [here](https://www.anaconda.com/blog/anaconda-distribution-2022-10#).
3. Numpy version 1.21.5 and latest. You can install it using the command line. Just type `pip install numpy` and press ENTER.

<a id='motivate'></a>
### Project Motivation
This is a capstone project for data science nano degree program. It involves the application of data science and analytical skills to gather, clean, analyze, visualise the simplified version of the real Starbucks app data. The data is provided by Udacity class strictly for this project.<br>  

Three datasets are provided: portfolio, profile, and transcript. This project will investigate customers behaviours toward offers and the factors that determines the distribution of offers to customers. 

The first part is the data gathering and loading. Here, the datasets are read, then explored, cleaned with pandas, and merged to form a new dataframe. Each of the dataset had its own complexity especially the `value` column in transcript dataframe. This column contained dictionary of values. At first, I could not get the unique values until I converted the whole column to string type. Next, I checked its unique values. Here, I observed that most rows had one key and one value, while others had two keys and two values. I observed the pattern and splitted this column into various columns, then I extracted the useful columns and named them `offer_id_sent` and `reward`. Finally, I appended them to the dataframe (`new_dataframe`).

The second part is the visualisation. Here, different kinds of plots: univariate, and multivariate plots are done on the cleaned and merged data to understand trends and tell stories.<br>

The third part is a blog post on medium about the analysis. 

<a id='describe'></a>
### File Descriptions
There are two files: Starbucks_Capstone_notebook.ipynb, and data folder that contains the project data: transcript.json, portfolio.json, and profile.json.<br>

__Starbucks_Capstone_notebook.ipynb__  contains the code and viz. In the notebook, markdown cells were used to assist in walking through the thought process for individual steps.

__portfolio.json__ - containing offer ids and meta data about each offer (duration, type, etc.)
__profile.json__ - demographic data for each customer
__transcript.json__ - records for transactions, offers received, offers viewed, and offers completed

Here is the schema and explanation of each variable in the files:
__portfolio.json__

id (string) - offer id
offer_type (string) - type of offer ie BOGO, discount, informational
difficulty (int) - minimum required spend to complete an offer
reward (int) - reward given for completing an offer
duration (int) - time for offer to be open, in days
channels (list of strings)

__profile.json__

age (int) - age of the customer
became_member_on (int) - date when customer created an app account
gender (str) - gender of the customer (note some entries contain 'O' for other rather than M or F)
id (str) - customer id
income (float) - customer's income

__transcript.json__

event (str) - record description (ie transaction, offer received, offer viewed, etc.)
person (str) - customer id
time (int) - time in hours since start of test. The data begins at time t=0
value - (dict of strings) - either an offer id or transaction amount depending on the record

<a id='acknowledge'></a>
### Licensing, Authors, Acknowledgements
The data used is a simplified version of the real Starbucks app data provided by Udacity.

<a id='result'></a>
### Results
The main findings of the code can be found at the post available.  here   [here](https://medium.com/@engrnsikanabasi/how-i-analysed-the-starbucks-dataset-to-uncover-the-effectiveness-of-its-promo-offers-to-customers-68af0dd4b44b)
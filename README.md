# Project 2: Tracking User Activity Instructions

## Introduction

Project 2 will be an individual project involving Data Wrangling to load sales data from a third party sales channel with some preliminary analytics on the loaded data.  

You will be working in Cloud, specifically in Amazon Web Services, in the official course VM, in a docker cluster running one container for Anaconda (Python distro) and one container for Postgres (SQL-based relational database).   You will be writing Python, Pandas, and SQL code in a Jupyter Notebook for your analysis and will be creating data visualizations to enhance your analytics.

## Additional Experience

In this project, you will gain additional experience with:
* GitHub on the Linux command line, including branches, pull requests, etc.
* SQL queries
* Functional programming using Python and SQL
* Linux command line
* Cloud (AWS)
* VM in the cloud instead of a physical computer
* Cluster of Docker containers running inside a VM in the cloud
* Enhancing a primary dataset with a secondary dataset
* Executive summaries

## New Skills

In this project, you will gain new skills:
* Design and create a mapping table to assist with integrating 3rd party IDs with primary database IDs
* Recursive walk through a nested JSON file to help understand the structure
* Parse a nested JSON files to produce CSV files with proper parent / child table linkeage
* Design and create staging tables that can accept dirty data from CSV files
* Load dirty data into staging tables from CSV files
* Validate data in staging tables 
* Validate data in staging tables matching against primary database tables 
* Validate data in staging tables matching against secondary database tables 
* Data exploration in staging tables
* Cleansing data in staging tables 
* Preliminary analytics from staging tables

## Business Case Scenario

Assume you are a full stack data scientist at Acme Gourmet Meals (AGM).

AGM executives are considering adding a delivery option, with the hopes of increasing sales, growing the customer base, and increasing profitability.   

Management decided to do a proof of concept (POC) in the form of a three month trial run using one delivery service at the Berkeley store.  

Management chose Peak Deliveries primarily because it's a newer operation with a model that takes a percentage cut of the product pricing instead of charging customers a delivery fee.  Peak's cut is 18 %. So, for each $ 12 meal, approximately $2.16. Customers may tip the delivery driver if they wish. AGM is not given any visibility into customer tips.  (Peak is protecting its data on good tippers.)  Peak has an outstanding reputation for great, fast, and efficient deliveries, with excellent customer service.  Peak will only deliver to zip codes within a 5 mile radius of the store.

Integration with any third party sales channel always comes with its challenges.  For large companies, like McDonalds, the delivery companies are willing to integrate and modify their computer systems as needed to get the contract.  For small companies, like AGM, our only option is to use Peak's API to send and receive data.  However, that would require us to write a lot of code, which management does not want to spend money on until the POC has proven successful. Peak can provide us with a JSON file at the end of each day with detailed sales information for that day.  Management has decided to go with the daily JSON option for now for the POC. 

For products, AGM will enter products into Peak's system.  Peak will assign an ID in their system to the product.  We will need to create a mapping table to map Peak's IDs to AGM's IDs.  In AGM's case all products cost $12 and are tax exempt.  AGM will mark them as exempt from sales tax.

Regarding the customer list, AGM does not want to give out their full customer list to third parties.  Customers will have to sign up with Peak, either using the website, the app, or by telephone.  Our executives anticipate and understand that the trade off to not giving them our customer list is that we will probably have to validate and/or cleanse the customer data.  Peak will assign their customer ID to each customer.

Regarding the store list.  In this POC we will only have 1 store and it will be the Berkeley store. Peak will create a pickup location for the store and assign their own location ID to it.  Even though all data will have the same store for now, we still want to receive it so we can plan for possible future expansion to other stores and/or pickup locations.

Assume today is the day after the first day of sales.  The first day of sales was October 3, 2020.  The JSON file came in very early this morning.  You need to get started with parsing, staging, validating, etc. the file as soon as possible.  The executives are very anxious to understand how dirty the customer data is going to be and also to get some preliminary analytics.

In part 2.1, you will be creating and loading the product mapping table (objective)

In part 2.2, you will be parsing Peak's sales JSON files into CSV files (objective)

In part 2.3, you will create and load staging tables (objective)

In part 2.4, you will validate data in the staging tables using SQL (objective)

In part 2.5, parts 2.5.1 through 2.5.3, you will run SQL queries to explore cleansing of the customer data (objective)

In part 2.5, part 2.5.4, you will write an executive summary on customer data, and recommend to the executives whether or not to give customer data to Peak (subjective)

In part 2.6, you will perform some preliminary analytics on data in the staging tables to answer specific questions from executives (objective)

In part 2.7, you will write an executive summary on what you feel is the most important aspect (or aspects) that you feel the executives would want to know (subjective)

Specific details for the above will be contained in the Jupyter Notebooks 

## Grading Rubrics

Semester Weighting
* Project 2
  * 29%
* Project 2 Feedback Acknowledgement
  * 1%

Late Submissions
* Submission time will the date and time the final pull request was created
* If a student forgot to create the pull request, but their last commit was before the due date and time, they will be allowed to create a pull request with a penality of -1 in lieu of the hours based late submission penalty
* 1 second late to 24 hours late: penalty -5
* 24 to 48 hours late: penalty -10
* 48 to 72 hours late: penalty -15
* 72 to 96 hours late: penalty -20
* No submissions will be accepted after 96 hours late

Objective 
* 80% 
* Right or wrong
* GitHub procedures
* CSV files
* Parts 2.1, 2.2, 2.3, 2.4, 2.5.1, 2.5.2, 2.5.3, 2.6

Subjective 
* 20% 
* Personal opinion
* Parts 2.5.4, 2.7

**Objective Items 80%**

GitHub procedures
* Maximum deduction for GitHub procedures: -3
* Did not name the repo the name given in proper case, penalty -1
* Did not name the branch the name given in proper case, penalty -1
* Altered the main branch, penalty -1
* Did not name the Jupyter Notebooks the names given in proper case, penalty -1
* Did not check in the peak_sales_2020_10_03.json file, penalty -1
* Non-essential files were checked in, such as checkpoint files and directories, penalty -1
* More than 1 open pull reqeust, penalty -1

CSV files
* peak_product_mapping.csv
* peak_sales.csv
* peak_stores.csv
* peak_customers.csv
* peak_line_items.csv

CSV File Rubrics
* File is checked in and correct in terms of format and/or data, but not named correctly, penalty -1
* File is checked in, but not correct in terms of format and/or data, penalty -2
* Did not check in the file, penalty -3

Parts 2.1, 2.2, 2.3, 2.4, 2.5.1, 2.5.2, 2.5.3, 2.6
* Provided an answer, but answer was wrong or partially wrong, penalty -1
* Did not provide an answer, penalty -2

**Subjective Items 20%**

Grader will evaluate the quality of the executive summaries for parts 2.5.4 and 2.7.

Here are the main scores and their criteria.  Grader may award scores in between if they feel a submission was in between.

Above 15/20 is very hard and very rare to achieve.

20/20
* Absolute perfection in all aspects
* Publication quality - similar to what would be published in an industry journal
* If reviewed by a data science team prior to presentation, no minor edits would be suggested
* Both executive summaries provided

17/20
* Excellence above and beyond
* Publication quality - similar to what would be published in an industry journal
* If reviewed by a data science team prior to presentation, no more than two minor edits would be suggested
* Both executive summaries provided

15/20
* Excellence above and beyond
* Publication quality - similar to what would be published in an industry journal
* If reviewed by a data science team prior to presentation, several minor edits would be suggested, but no major edits would be suggested
* Both executive summaries provided

13/20
* Excellent work
* Very high quality
* Very strong arguments
* If reviewed by a data science team prior to presentation, several minor edits would be suggested, but no more than one major edit would be suggested
* Both executive summaries provided

10/20
* High quality
* Very strong arguments
* Both executive summaries provided

7/20
* High quality
* Strong arguments
* At least one of the executive summaries provided

4/20
* Low quality
* Weak arguments
* At least one of the executive summaries provided

0/20
* No submissions for any of the executive summaries



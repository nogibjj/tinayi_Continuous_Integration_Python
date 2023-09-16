[![CI](https://github.com/nogibjj/tinayi_week2_mini_project/actions/workflows/cicd.yml/badge.svg)](https://github.com/nogibjj/tinayi_week2_mini_project/actions/workflows/cicd.yml)

## Continuous Integration using GitHub Actions of Python Data Science Project

IDS 706 Individual Project 1

Continuous Integration using GitHub Actions of Python Data Science Project

### Goal

+ establish a CodeSpaces environment that automates the process of loading a dataset using `Pandas` and executing a `readfile` function to generate descriptive statistics on the dataset, utilizing GitHub Actions. 
  
+ create data visualizations of the dataset using `matplotlib`

+ create summary report using `Jupyter Notebook`

The workflow includes running a Makefile to perform tasks such as installation (`make install`), testing (`make test`), code formatting (`make format`) with Python Black, linting (`make lint`) with Ruff, and an all-inclusive task (`make all`). This automation streamlines the data analysis process and enhances code quality.

### Preperation

+ I used the IDS-706-Python-GitHub-template for this project. This template includes a `Makefile`, `requirements.txt`, `.devcontainer`, `.gitignore`, `GitHubActions`, and `Readme`.

+ I downloaded the `Heart Attack Analysis & Prediction Dataset` from Kaggle.

### Dataset Description

`Heart Attack Analysis & Prediction Dataset` (simplify as `heart.csv`) is a csv file containing related information of 302 randomly picked people and their respective information including age, sex, exercise induced angina, number of major vessels, chest pain type, resting blood pressure, cholestoral, fasting blood sugar, resting electrocardiographic results, and chances of heart attack.


#### [Resources](https://www.kaggle.com/datasets/rashikrahmanpritom/heart-attack-analysis-prediction-dataset) 

### Overview

This project creates a Python script using Pandas for descriptive statistics. The specific steps involve: 

+ Create `lib.py` file
  
  + Read a dataset (CSV) using `Pandas`

+ Create a Jupyter Notebook `script.ipynb`

  + import `readfile` function from `lib.py`

  + Generate summary statistics (mean, median, standard deviation)

  + Create data visualizations

+ Create a test for Jupyter Notebook
  
  + Using nbval plugin for `pytest`
    
+ Create a Phython script `script.py`
  
  + import `readfile` function from `lib.py`

  + Generate summary statistics (mean, median, standard deviation)

  + Create data visualizations

  + Save summary statistics as `html` file into `output` folder

  + Save the data visualizations as image into `output` folder

+ Create a `test_script.py` file 
  
  + Test Python script

+ Create a `test_lib.py` file 
  
  + Test library

+ Generate a summary report (PDF)
  
### Description

Step 1: In the `requirements.txt`, I added `pandas`, `matplotlib`, and `nbval`. 

<img width="695" alt="Screen Shot 2023-09-16 at 5 53 43 PM" src="https://github.com/nogibjj/tinayi_individual_project1/assets/143360909/2af4dcd0-70fa-41b8-8c40-f5732d5c3d88">

Step 2: In the `Makefile`, I include the following:
       
       + install all the requirements

       + test Jupyter Notebook and script and lib

       + Formats code with Python black
       
       + Lints code with Ruff

<img width="659" alt="Screen Shot 2023-09-16 at 6 05 06 PM" src="https://github.com/nogibjj/tinayi_individual_project1/assets/143360909/5a9dabfe-6c4c-4ebc-be67-cf31a700e1b1">

Step 3: In the `lib.py` under the mylib folder, I include:

       + a `readfile` function, which reads a CSV file.

Step 4: In the `script.ipynb`, I create a scrapbook for my Python Script. It includes:
       
       + import `readfile` function from `lib.py`

       + a 'summary' function which generates summary statistics for the numeric columns in the DataFrame heart.csv.

       + a 'median' function which calculate the median value for each column in heart.csv

       + a 'histogram' function which generate histogram for each column in heart.csv

       + a 'scatter_age_blood_pressure' function which generate scatter plot with fitted line for the 4th column (resting blood pressure) and the 1st column (age) in heart.csv

Step 5: In the `script.py`, I created a Python Script. It includes: 
       
       + import `readfile` function from `lib.py`

       + a 'summary' function which generates summary statistics for the numeric columns in the DataFrame heart.csv. 
       
         + It is saved as a `html` file in my output folder.

       + a 'median' function which calculate the median value for each column in heart.csv. 
       
         + It is saved as a `html` file in my output folder.

       + a 'histogram' function which generate histogram for each column in heart.csv. 
       
         + It is saved as a series of graphs in the `png` form in my output folder.

       + a 'scatter_age_blood_pressure' function which generate scatter plot with fitted line for the 4th column (resting blood pressure) and the 1st column (age) in heart.csv. 
       
         + It is saved in the `png` form in my output folder.

       + a `create_output_directory` function which generates output directory to save `html` and `png`

Step 7: In the `test_lib.py`, I wrote a test function `test_readfile` which checks the function in `lib.py` 

       + check that the `readfile` function successfully reads the CSV file specified by file_path and returns a non-empty Pandas DataFrame.

Step 8: In the `test_script.py`, I wrote five test functions `test_output_directory_exists`, `test_summary`, `test_median`, `test_histogram`,`test_scatter_age_blood_pressure`, which checks the output folder, the summary statistics and data visualizations of `heart.csv`.

       + check the output directory exists

       + check the mean value of the fourth column (resting blood pressure)
       
       + check the median value of the fourth column (resting blood pressure)
       
       + check the standard deviation value of the fourth column (resting blood pressure)

       + check histogram for each column

       + check scatter plot for age and resting blood pressure

Step 9: I generated Data Visualizations

+ summary statistics

<img width="1013" alt="Screen Shot 2023-09-11 at 1 12 52 AM" src="https://github.com/nogibjj/tinayi_week2_mini_project/assets/143360909/c0027011-01fa-4641-b1db-2bc16fc0b837">

+ median values

<img width="916" alt="Screen Shot 2023-09-11 at 1 13 15 AM" src="https://github.com/nogibjj/tinayi_week2_mini_project/assets/143360909/50e1b86f-4158-4333-984a-4d32e5b2fb42">

+ histogram of each column

![image](https://github.com/nogibjj/tinayi_week2_mini_project/assets/143360909/698dc927-6391-4266-8dcc-fa475a9df65a)

![image](https://github.com/nogibjj/tinayi_week2_mini_project/assets/143360909/658fd114-57b4-4d5d-a65a-a4f397e38248)

![image](https://github.com/nogibjj/tinayi_week2_mini_project/assets/143360909/aded97be-f769-47a9-81b1-4f5efe5118a5)

![image](https://github.com/nogibjj/tinayi_week2_mini_project/assets/143360909/46f27fd7-f0ab-45af-9ecd-33a0403cc631)

![image](https://github.com/nogibjj/tinayi_week2_mini_project/assets/143360909/bbe3d598-306d-4ed3-b3dc-61c8a37438a5)

![image](https://github.com/nogibjj/tinayi_week2_mini_project/assets/143360909/0ad57724-7e35-4d8a-8f8f-a50541f7a050)

![image](https://github.com/nogibjj/tinayi_week2_mini_project/assets/143360909/212788dc-c385-4953-a8d8-c8fc8cceac6f)

![image](https://github.com/nogibjj/tinayi_week2_mini_project/assets/143360909/861c299c-d037-45b4-9d0f-de29e1ca4de7)

![image](https://github.com/nogibjj/tinayi_week2_mini_project/assets/143360909/f4d65bca-c483-4866-a734-0576b5076cdb)

![image](https://github.com/nogibjj/tinayi_week2_mini_project/assets/143360909/c8c2ae73-95c9-410f-849b-4880bbcdcb66)

![image](https://github.com/nogibjj/tinayi_week2_mini_project/assets/143360909/e786fbf7-f238-48ef-9f26-705967b8843a)

![image](https://github.com/nogibjj/tinayi_week2_mini_project/assets/143360909/4f775859-6b73-4cfa-af1b-0e8bdd34b7b3)

![image](https://github.com/nogibjj/tinayi_week2_mini_project/assets/143360909/46be7348-fd3c-41c9-a608-bd1c8921c1f7)

![image](https://github.com/nogibjj/tinayi_week2_mini_project/assets/143360909/2c5310b6-e218-4727-8c7f-59072ff97f8d)

+ scatter plot for resting blood pressure and age in heart.csv

![image](https://github.com/nogibjj/tinayi_week2_mini_project/assets/143360909/31a73193-129e-47dd-ac9b-d7a87e974f84)


Step 5: I generated the summary report (PDF) from Jupyter Notebook

#### [Summary Report PDF](Summary-Report.pdf)

### Check Format and Test Approval Image

+ install code `make install`
  
<img width="1033" alt="Screen Shot 2023-09-16 at 5 28 02 PM" src="https://github.com/nogibjj/tinayi_individual_project1/assets/143360909/190bdd58-e7e7-46e6-bcbc-ef0341884c95">

+ lint code `make lint`
+ format code `make format`
+ test code `make test`

<img width="1023" alt="Screen Shot 2023-09-16 at 6 46 49 PM" src="https://github.com/nogibjj/tinayi_individual_project1/assets/143360909/3b218acf-5a3e-4577-89b7-e3b75556596b">

+ code `make all` executes install, lint, format, and test targets

<img width="1020" alt="Screen Shot 2023-09-16 at 6 47 15 PM" src="https://github.com/nogibjj/tinayi_individual_project1/assets/143360909/773f9d6f-6fe2-46a8-872d-9b9f47c1fd94">
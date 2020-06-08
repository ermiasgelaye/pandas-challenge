## PyCitySchools

![Education](Images/Education.gif)


## Background

This repository brings a python pandas solution in the education sector to analyze city's school district data. This project will help school board and mayor to make strategic decisions regarding future school budgets and priorities. This project used two datasets in csv format, one is [schools_complete.csv](PyCitySchools/Resources/schools_complete.csv) file wich includes the following informations in columns `Student ID`,`school_name`,`type`,`size`,`budget` the other dataset is [students_complete.csv](PyCitySchools/Resources) file which includes the followling information in columns `Student ID`,`student_name`,`gender`,`grade`,`school_name`,`reading_score`and `math_score`. For these analysis both datasets imported, merged, and the aggregate data diplayed in to python pandas dataframes. The project is conducted in Jupyter notebook to showcase, and communicate the analysis report the following link is created: [Jupyter Notebook Viewer](https://nbviewer.jupyter.org/github/ermiasgelaye/pandas-challenge/blob/master/PyCitySchools/.ipynb_checkpoints/PyCitySchools_starter-checkpoint.ipynb) 

## Table of Contents
* [Import Dependencies and Setup](https://nbviewer.jupyter.org/github/ermiasgelaye/pandas-challenge/blob/master/PyCitySchools/.ipynb_checkpoints/PyCitySchools_starter-checkpoint.ipynb)
* [Load, Read and Merge the Data](https://nbviewer.jupyter.org/github/ermiasgelaye/pandas-challenge/blob/master/PyCitySchools/.ipynb_checkpoints/PyCitySchools_starter-checkpoint.ipynb)
* [District Summary](https://nbviewer.jupyter.org/github/ermiasgelaye/pandas-challenge/blob/master/PyCitySchools/.ipynb_checkpoints/PyCitySchools_starter-checkpoint.ipynb)
* [School Summary](https://nbviewer.jupyter.org/github/ermiasgelaye/pandas-challenge/blob/master/PyCitySchools/.ipynb_checkpoints/PyCitySchools_starter-checkpoint.ipynb)
* [Top Performing Schools (By % Overall Passing)](https://nbviewer.jupyter.org/github/ermiasgelaye/pandas-challenge/blob/master/PyCitySchools/.ipynb_checkpoints/PyCitySchools_starter-checkpoint.ipynb)
* [Bottom Performing Schools (By % Overall Passing)](https://nbviewer.jupyter.org/github/ermiasgelaye/pandas-challenge/blob/master/PyCitySchools/.ipynb_checkpoints/PyCitySchools_starter-checkpoint.ipynb)
* [Math Scores by Grade](https://nbviewer.jupyter.org/github/ermiasgelaye/pandas-challenge/blob/master/PyCitySchools/.ipynb_checkpoints/PyCitySchools_starter-checkpoint.ipynb)
* [Reading Scores by Grade](https://nbviewer.jupyter.org/github/ermiasgelaye/pandas-challenge/blob/master/PyCitySchools/.ipynb_checkpoints/PyCitySchools_starter-checkpoint.ipynb)
* [Scores by School Spending](https://nbviewer.jupyter.org/github/ermiasgelaye/pandas-challenge/blob/master/PyCitySchools/.ipynb_checkpoints/PyCitySchools_starter-checkpoint.ipynb)
* [Scores by School Size](https://nbviewer.jupyter.org/github/ermiasgelaye/pandas-challenge/blob/master/PyCitySchools/.ipynb_checkpoints/PyCitySchools_starter-checkpoint.ipynb)
* [Scores by School Type](https://nbviewer.jupyter.org/github/ermiasgelaye/pandas-challenge/blob/master/PyCitySchools/.ipynb_checkpoints/PyCitySchools_starter-checkpoint.ipynb)
* [Observable Trends](https://nbviewer.jupyter.org/github/ermiasgelaye/pandas-challenge/blob/master/PyCitySchools/.ipynb_checkpoints/PyCitySchools_starter-checkpoint.ipynb)


### Import Dependencies and Setup

```python
# Dependencies and Setup
import pandas as pd
```
### Load, Read and Merge the Data
```python
 # File to Load (Remember to Change These)
school_data_to_load = "Resources/schools_complete.csv"
student_data_to_load = "Resources/students_complete.csv"

# Read School and Student Data File and store into Pandas DataFrames
school_data = pd.read_csv(school_data_to_load)
student_data = pd.read_csv(student_data_to_load)

# Combine the data into a single dataset.  
school_data_complete = pd.merge(student_data, school_data, how="left", on=["school_name", "school_name"])
school_data_complete.head()
```
### District Summary

* A high level analysis on the district's created on the following key metrics
  * Total Schools
  * Total Students
  * Total Budget
  * Average Math Score
  * Average Reading Score
  * % Passing Math (The percentage of students that passed math.)
  * % Passing Reading (The percentage of students that passed reading.)
  * % Overall Passing (The percentage of students that passed math **and** reading.)
  
  The summery table looks as follows:
  <style  type="text/css" >
</style>  
<table id="T_1a0abed2_9a44_11e7_bb3a_0c4de9c48691" > 
<thead>    <tr> 
        <th class="blank level0" ></th> 
        <th class="col_heading level0 col0" >Total Schools</th> 
        <th class="col_heading level0 col1" >Total Students</th> 
        <th class="col_heading level0 col2" >Total Budget</th> 
        <th class="col_heading level0 col3" >Average Reading Score</th> 
        <th class="col_heading level0 col4" >Average Math Score</th> 
        <th class="col_heading level0 col5" >% Passing Reading</th> 
        <th class="col_heading level0 col6" >% Passing Math</th> 
        <th class="col_heading level0 col7" >Overall Passing Rate</th> 
    </tr></thead> 
<tbody>    <tr> 
        <th id="T_1a0abed2_9a44_11e7_bb3a_0c4de9c48691" class="row_heading level0 row0" >0</th> 
        <td id="T_1a0abed2_9a44_11e7_bb3a_0c4de9c48691row0_col0" class="data row0 col0" >15</td> 
        <td id="T_1a0abed2_9a44_11e7_bb3a_0c4de9c48691row0_col1" class="data row0 col1" >39170</td> 
        <td id="T_1a0abed2_9a44_11e7_bb3a_0c4de9c48691row0_col2" class="data row0 col2" >$24,649,428.00</td> 
        <td id="T_1a0abed2_9a44_11e7_bb3a_0c4de9c48691row0_col3" class="data row0 col3" >81.9</td> 
        <td id="T_1a0abed2_9a44_11e7_bb3a_0c4de9c48691row0_col4" class="data row0 col4" >79.0</td> 
        <td id="T_1a0abed2_9a44_11e7_bb3a_0c4de9c48691row0_col5" class="data row0 col5" >85.8%</td> 
        <td id="T_1a0abed2_9a44_11e7_bb3a_0c4de9c48691row0_col6" class="data row0 col6" >75.0%</td> 
        <td id="T_1a0abed2_9a44_11e7_bb3a_0c4de9c48691row0_col7" class="data row0 col7" >65.2%</td> 
    </tr></tbody> 
</table> 

### School Summary

* An overview table that summarizes key metrics about each school created in the following metrics
  * School Name
  * School Type
  * Total Students
  * Total School Budget
  * Per Student Budget
  * Average Math Score
  * Average Reading Score
  * % Passing Math (The percentage of students that passed math.)
  * % Passing Reading (The percentage of students that passed reading.)
  * % Overall Passing (The percentage of students that passed math **and** reading.)

### Top Performing Schools (By % Overall Passing)

* Create a table that highlights the top 5 performing schools based on % Overall Passing. Include:
  * School Name
  * School Type
  * Total Students
  * Total School Budget
  * Per Student Budget
  * Average Math Score
  * Average Reading Score
  * % Passing Math (The percentage of students that passed math.)
  * % Passing Reading (The percentage of students that passed reading.)
  * % Overall Passing (The percentage of students that passed math **and** reading.)

### Bottom Performing Schools (By % Overall Passing)

* Create a table that highlights the bottom 5 performing schools based on % Overall Passing. Include all of the same metrics as above.

### Math Scores by Grade

* Create a table that lists the average Math Score for students of each grade level (9th, 10th, 11th, 12th) at each school.

### Reading Scores by Grade

* Create a table that lists the average Reading Score for students of each grade level (9th, 10th, 11th, 12th) at each school.

### Scores by School Spending

* Create a table that breaks down school performances based on average Spending Ranges (Per Student). Use 4 reasonable bins to group school spending. Include in the table each of the following:
  * Average Math Score
  * Average Reading Score
  * % Passing Math (The percentage of students that passed math.)
  * % Passing Reading (The percentage of students that passed reading.)
  * % Overall Passing (The percentage of students that passed math **and** reading.)

### Scores by School Size

* Repeat the above breakdown, but this time group schools based on a reasonable approximation of school size (Small, Medium, Large).

### Scores by School Type

* Repeat the above breakdown, but this time group schools based on school type (Charter vs. District).

As final considerations:

* Use the pandas library and Jupyter Notebook.
* You must submit a link to your Jupyter Notebook with the viewable Data Frames.
* You must include a written description of at least two observable trends based on the data.
* See [Example Solution](PyCitySchools/PyCitySchools_starter.ipynb) for a reference on the expected format.

## Observable Trends
You must include a written description of three observable trends based on the data.


### Copyright

Trilogy Education Services © 2019. All Rights Reserved.

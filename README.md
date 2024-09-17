### ECE 2112: Advanced Computer Programming and Algorithms
---
# **Experiment 4: Data Wrangling and Data Visualization**
### Submitted by: **Jihan Harvey C. Casiedo**
#### Section: 2ECE-A
---
### **Background of the Experiment**
##### Data wrangling is the process that involves converting raw data into a cleaner format, making it appropriate, valuable and useful for data analytics. Data visualization, on the other hand, is the graphical representation of any information or data. It provides a wat of understanding trend, outliers and pattern in data
---
### **Objectives of the Experiment**
##### This experiment aims for students to identify the codes and functions needed in cleaning and visualizing data and be able to apply and use the different codes and functions in creating a Python program that will be used in data wrangling and data visualization
---
### **Instructions**
##### Download the ECE Board Exam 2 dataset found on this link: bit.ly/ECEBoardExamDataset and write a Python script/code in the Jupyter Notebook to do the given problems. You may submit your Jupyter notebook in the dedicated submission bin. 
ECE BOARD EXAM PROBLEM: Using data wrangling and data visualization technique with storytelling, analyze the data and present different (i) data frames; and (ii) visuals using the dataset given

---

### **Problem 1**
##### Create the following data frames based on the format provided: 
##### a. Filename: Instru = [“Name”, “GEAS”, “Electronics >70”]; where track is constant as Instrumentation and hometown Luzon
b. Filename: Mindy = [ “Name”, “Track”, “Electronics”, “Average >=55”]; where hometown is
constant as Mindanao and gender Female

---
### **Problem 1 Code**
##### Import the pandas library and load the xslx file ECE Board Exam 2

``` js
import pandas as pd
boards = pd.read_excel('board2.xlsx')
boards
```
##### *Result:*
![image](https://github.com/user-attachments/assets/752df47b-a341-433c-81e4-83f70b359aa4)

---
#

##### For a. Filename: Instru = [“Name”, “GEAS”, “Electronics >70”]; where track is constant as Instrumentation and hometown Luzon:

We will create a data frame that shows the Name, GEAS Grade and Electronics Grade of students from Luzon who are in the Instrumentation Track and has a score greater than 70 for Electronics

``` js
Instru = boards.loc[
    (boards['Track'] == 'Instrumentation') & (boards['Hometown'] == 'Luzon') & (boards['Track'] == 'Instrumentation') & (boards['Electronics'] > 70),
    ['Name', 'GEAS', 'Electronics']]
Instru
```
##### *Result:*
![image](https://github.com/user-attachments/assets/e8a1be69-7760-41c4-b227-14cf3321a1d5)
---
#

##### For b. Filename: Mindy = [ “Name”, “Track”, “Electronics”, “Average >=55”]; where hometown is constant as Mindanao and gender Female:
We will create a data frame that shows the Name, Track and Electronics Grade of students from Mindanao who have an average grade for Math, GEAS, Electronics and Communications greater than or equal 55.

``` js
boards['Average'] = boards[['Math', 'Electronics', 'GEAS', 'Communication']].mean(axis=1)
Mindy = boards.loc[
    (boards['Hometown'] == 'Mindanao') & (boards['Gender'] == 'Female') & (boards['Average'] >= 55),
    ['Name', 'Track', 'Electronics', 'Average'],]
Mindy
```
##### *Result:*
![image](https://github.com/user-attachments/assets/40a93555-d507-4ee4-84ef-a686c2dfb17c)
---

### **Problem 2**
##### Create a visualization that shows how the different features contributes to average grade. Does chosen track in college, gender, or hometown contributes to a higher average score?

---
### **Problem 2 Code**
##### Import the Matplotlib library to create data visualizations that show how different features contribute to average grade

``` js
import matplotlib.pyplot as plt 
```

---
##### Comparing the track to the average grade we use the function plt.figure to indicate the size of the graph and plt.bar to indicate the variables to be compared

#### **Track and Average Grade Relationship**
``` js
plt.figure(figsize=(10,6))
plt.bar(boards['Track'],boards['Average'])
```
##### *Result:*
![image](https://github.com/user-attachments/assets/ac29fe01-7245-40b6-8ca8-3da60eca9c12)
---
#### **Gender and Average Grade Relationship**
``` js
plt.figure(figsize=(10,6))
plt.bar(boards['Gender'],boards['Average'])
```
##### *Result:*
![image](https://github.com/user-attachments/assets/d9dd0372-4001-43ac-8db3-56f6b266d7f4)
#### **Hometown and Average Grade Relationship**
``` js
plt.figure(figsize=(10,6))
plt.bar(boards['Gender'],boards['Average'])
```
##### *Result:*
![image](https://github.com/user-attachments/assets/2eaf2b8e-3bb1-4657-bfc1-b009f95a1b64)



### **Conclusion**
##### This experiment allows students to explore the functions for cleaning and visualizing data. By applying the understanding of the functions, students will be able to effectively transform raw data into a cleaner and usable format and create visualizations.

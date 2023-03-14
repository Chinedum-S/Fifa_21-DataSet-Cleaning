# Fifa_21-DataSet-Cleaning
Cleaning a very messy fifa 21 dataset as part of a #Datacleaningchallenge

As a data analyst it always very rare to come across a very well structured, clean and accurate data set to work with. It is the job of a data analyst to load, clean, transform and analyse any form of data provided for an analysis. Hence the need for a lot of practice as beginner or intermediate data analyst.
I was lucky to have stumbled upon the #Datacleaningchallenge on twitter and without a doubt I hoped on the challenge.

# DATA BACKGROUND
The data provided was an extract of a library of players from the Fifa 21 video game in csv format as derived from kaggle. It contained 18,980 rows and 77 columns. The data is publicly avaialble and more details including the data dictionary can be gotten via this link.

# TOOL OF CHOICE
I am using Microsoft Excel as my preferred tool of cleaning, because of it's versatitly, it's GUI and low-code demand and most importantly; it's what I am most comfortable using.

# DATA CLEANING STEPS/PROCESS

In data cleaning there are no defined steps or process to follow, but here is how I tackled the challenge

# A) Data Importing
    
      The data came in a CSV format and it was opened directly with excel to have a quick overview and scan of the data so as to determine the columns the possibly needs cleaning. Upon this scan the following were discovered;
      1. The Name,LongName, clubs, value, wage ,IR and release clause column all had special characters which were ureadable
      2. The OVA column header also had special characters
      
   This problem was tackled by importing the csv file using the power query editor in excel, and changing the file orgin to **"65001: Unicode (UTF-8)"**
   Voila!! all the special characters were corrected
  ![image](https://user-images.githubusercontent.com/127835654/224968284-fd812272-1d6d-40c6-b5fe-9e3922443047.png)


![image](https://user-images.githubusercontent.com/127835654/224967651-7cea45e3-c8c2-4b53-945d-4d8713c67a4c.png)


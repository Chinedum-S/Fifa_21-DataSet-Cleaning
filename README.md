# Fifa_21-DataSet-Cleaning
Cleaning a very messy fifa 21 dataset as part of a #Datacleaningchallenge

As a data analyst it always very rare to come across a very well structured, clean and accurate data set to work with. It is the job of a data analyst to load, clean, transform and analyse any form of data provided for an analysis. Hence the need for a lot of practice as beginner or intermediate data analyst.
I was lucky to have stumbled upon the #Datacleaningchallenge on twitter and without a doubt I hoped on the challenge.

# DATA BACKGROUND
The data provided was an extract of a library of players from the Fifa 21 video game in csv format as derived from kaggle. It contained 18,980 rows and 77 columns. The data is publicly avaialble and more details including the data dictionary can be gotten via this link.

# TOOL OF CHOICE
I am using Microsoft Excel as my preferred tool for cleaning, because of it's versatitly, it's GUI and low-code demand and most importantly; it's what I am most comfortable using.

# DATA CLEANING STEPS/PROCESS

In data cleaning there are no defined steps or process to follow, but here is how I tackled the challenge

# A) Data Importing
    
The data came in a CSV format and it was opened directly with excel to have a quick overview and scan of the data so as to determine the columns that could possibly need cleaning. Upon this scan the following were discovered;
      1. The Name,LongName, clubs, value, wage ,IR and release clause column all had special characters which were ureadable
      2. The OVA column header also had special characters
      
   This problem was tackled by importing the csv file  into excel by using the power query editor Under the Data Tab ->> From Text/CSV in Get & Transform Data group, and changing the file orgin to **"65001: Unicode (UTF-8)"** then Load the data
   Voila!! all the special characters were corrected.

 A1) ![image](https://user-images.githubusercontent.com/127835654/224968284-fd812272-1d6d-40c6-b5fe-9e3922443047.png)


 A2)  ![image](https://user-images.githubusercontent.com/127835654/224967651-7cea45e3-c8c2-4b53-945d-4d8713c67a4c.png)

*Importing via power query is also means of having a back up of the original file as it is basically a copy

# B) CHECK FOR DUPLICATE and BLANKS SPACES
   *As a personal rule of thumb I always create a new column at the beginning of a dataset and assign a number to each row. This is done to keep the order of the data intact when sorting, filtering and manipuating,  so that the data can be arranged the same way the original file was gotten.
 
B1. The conditional formatting tool was deployed to check and highlight duplicate cells and then a filter was created To isolate affected cells, it was then discovered that there were no duplicate IDs and therefore all entries were unique.

B2. A scan on the club column revealed that the there were preceeeding and receeding blank spaces, this was corrected using the clean function (=clean(cell_reference))

# C) REMOVAL OF EXTRA CHARACTERS AND SHAPE
 C1. The column W/F, SM and IR contained a Star shape, this was removed by using the Text to Columns tool under the Data Tools group in the Data Tab, the star was used as the delimeter and was not imported, alternatively fixed width can be used since the max was 5 and a single would evenly split the column
 
 
 BEFORE:  ![image](https://user-images.githubusercontent.com/127835654/224986454-5ce6a0d9-f491-4892-9dc8-35bc85f96f0b.png)   AFTER:   ![image](https://user-images.githubusercontent.com/127835654/224986676-f0cd1d10-3767-49de-b3ea-b03880c7b9e6.png)
 


 
 
 C2. The contract column also contains a tilde sign "~" which did not sit right with me and I decided to change the symbol to a regular hyphen "-" which made more sense, this was done using the REPLACE function (=REPLACE(K2,6,1,"-") and =REPLACE(K2,6,1,"0")

BEFORE:  ![image](https://user-images.githubusercontent.com/127835654/224989488-fea1a14e-9ab8-481f-a2eb-dc9dac6a941e.png)   AFTER:   ![image](https://user-images.githubusercontent.com/127835654/224991057-7321f283-109d-4baf-ba78-36e335d7e89b.png)




 
 # D) CONVERSION! CONVERSION! CONVERSION!
 I am always of the opinion that no column should be deleted or entirely changed without a given business task or assignment in this case we were just given a dataset to clean and therefore I felt the need not to delete, completely alter or seperate columns unless intructed otherwise.
 However some columns needed conversions, e.g the Height,Weight, Value, Wage, Release clause and Hits Columns
 
 #HEIGHT 
    
   The height column contained some cells with the height in 'cm' while other some other cells had the height in 'foot' in order to regularize this column, the columns with foot had to be converted to cm as they were the minority in terms of ratio; this was done by splitting the cells using "," as the delimeter and eliminating the suffixed (") the split columns were then multiplied by 30.48 and 2.54 respectively and the results were added and rounded to get the value in cm 
  e.g 6'2" ->> |6| |2| ->> |6 * 30.48|2 * 2.54| ->> |182.88|5.08| ->> |SUM(A1,B1)| ->> |187.96|
  
 


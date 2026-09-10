# 2ECEB-ECE2112-PA-3

**Made by: Lanz Joseph S. Pelayo || 2ECE-B**

# Introduction
This repository contains an explanation of the code for the programming assignment, which the author has made available for viewing. Specifically, the contents of this repository aim to address Programming Assignment #3, which comprises 3 problems, for the 2026-2027 academic year in ECE 2112. This aims to help viewers explain how the author used the program's functions to make it work, drawing on the author's knowledge of Python Data Analysis from module 3.

# 0. Preliminary Setup:

The following commands were used in this problem to create an overall function used in the program:

• `import pandas as pd` - Command used to import the Python Data Analysis into the program in order to use the functions of the pandas Library by using pd as a shortcut. 

• `pd.read_csv` - Command used to read the CSV file inserted in the compiler/notebook and introduce it to the program, allowing the data within the csv file to be read and imported into the program

By using these commands, this allows us to introduce the Cars CSV and store it in a variable named `cars` while also introducing the pandas library

```python
import pandas as pd #--> Importing Pandas library to the notebook
cars =  pd.read_csv('cars.csv') #--> Readin the cars csv inserted to the notebook and stored it in a variable named cars.
```

# A. POSITIONAL AND LABEL-BASED SLICING
After loading cars, complete the following operations. \
a. Display the shape and complete list of column names of cars. \
b. Using positional slicing, create cars 6 to 10 containing rows 6 through 10 of the dataset, where \
the first data row is row 1. \
c. From cars 6 to 10, display only the columns Model, mpg, cyl, hp, and gear, in that order. 

The following functions were used in this problem to create a unique function:

• `.shape`- A built-in function within the Pandas Library to measure the shape of a dataframe or series variable, it usually measures how many rows and columns a dataframe has. It outputs (X,Y), where X is the number of Rows and Y is the number of columns.

Example: 
`cars.shape` --> (32,12) Meaning, 32 Rows and 12 Columns

• `.iloc[x,y]` - Integer Location, A built-in function within the Pandas Library, which outputs the value at specific rows X, where it can use a slice 
operation to take multiple rows and specific Y values, where it can also be sliced from a dataframe or series variable stated before the dot. It can mostly 
accept index-based inputs within the X and Y values.

Example:
`cars.iloc[5:10]` ---> Extracts the dataframe data from Cars to output the rows from index 5 to 9; it also outputs all of the columns in rows 5 to 9.

•`.loc[[M],[N]` - Label Location,A built-in function within the Pandas Library, which outputs the value at specific rows X and Y of the said variable 
before the dot. where it can be used with slicing and even names of specific rows and columns that are wished to be output.

`cars.loc[:, ['Model','mpg','cyl','hp','gear']]` --> outputs every row within the dataframe, but only specific names of the stated columns are output.

With the functions mentioned above, the author created a program that chose the cars from 6 to 10 by using `cars.iloc[]` from index 5-10 through slicing in 
In order to obtain the said row. Afterward, by creating a parenthesis between the `cars.iloc`, `cars.loc` was to extract all of the rows from 6-10 created 
by the integer location function and choose specific columns of to display Model, mpg, cyl, hp, and gear, in that order, of the said rows. By using these 
commands and storing it to cars_6_to_10, it automatically saves as a dataframe rather than an element, therefore obtaining the data from cars 6 to 10 with 
specific columns extracted. Additionally, `.shape` was used, and typing cars themselves allowed us to see cars' rows and columns alongside their shape, which is
32 rows and 12 columns.

```python
cars #---> Allows to print the cars without actually printing it
cars.shape #---> outputs as 32,12, which allows to show what is the shape of the cars dataframe is

cars_6_to_10 = (cars.iloc[5:10]).loc[:, ['Model','mpg','cyl','hp','gear']] #---> extracts the cars from rows 6-10 from index 5 to 10 with all of the data
#from iloc. But in loc, it extracts all of the rows of cars from the iloc, which is 6-10, but only extracts specific columns stated in the code, where it's then
#stored in the variable
cars_6_to_10 #--> prints the chosen cars without using the print function.
```

# B. MODEL LOOKUP
Use Boolean indexing on the Model column to answer both requests.\
a. Display the complete row for Toyota Corolla.\
b. For Pontiac Firebird, display only Model, mpg, hp, and wt\

The following methods and functions were used in this problem to create a unique function:


•`.loc[[M],[N]` - Label Location, A built-in function within the Pandas Library, which itout puts the value at specific rows X and Y, where it can be used with slicing and even names of specific rows and columns that are wished to be output.

• Boolean Indexing - A type of method used to extract portions of data based on the said conditions within either rows or columns. These conditions can be based on numbers within the columns, and if they are equal to the said name.

Example: `cars.loc[cars['Model' ]== 'Toyota Corolla']` --> Shows the entire row of the Toyota Corolla Column


With the functions mentioned above, the author created a program that allows us to take specific cars, such as the Toyota Corolla and Pontiac Firebird, 
while also choosing specific columns on it. The author used `.loc` to select the rows and columns specified in the requirements. But in order to 
take the specific cars without using row indexing, the author used boolean indexing  and equalized it to the same letters and capitalization of the Pontiac 
and the Toyota as it is case sensitive. This allows us to get the row of the Toyota Corolla and all of the columns within it; moreover, this also allows us
to retrieve the Pontiac Firebird data by extracting the row and specific columns with its elements, thanks to `.loc`

```python

toyota = cars.loc[cars['Model' ]== 'Toyota Corolla'] #--> Using a certain condition where the model is equal to Toyota Corolla, it allows the author to
# extract the row of the Toyota Corolla.
toyota #--> print sand shows the toyota dataframe variable
pontiac = cars.loc[cars['Model'] == 'Pontiac Firebird',['Model','mpg','hp','wt']] # Using a certain condition where the model is equal to Pontiac Firebird, it
# allows the author to extract the row of the Pontiac while also setting up certain columns and its elements to be shown according to the requirement.
```

# C. MULTI-MODEL SUBSETTING
Create a DataFrame named selected cars containing only the records for three models: Datsun 710,
Lotus Europa, and Ferrari Dino.
For these records, retain only Model, mpg, cyl, hp, and gear. Select the rows by their model values
rather than by row numbers. Display selected cars and its shape.


The following methods and functions were used in this problem to create a unique function:

•`.loc[[M],[N]` - Label Location, A built-in function within the Pandas Library, which itout puts the value at specific rows X and Y, where it can be used with slicing and even names of specific rows and columns that are wished to be output.

• Boolean Indexing - A type of method used to extract portions of data based on the said conditions within either rows or columns. These conditions can be based on numbers in the columns and whether they match the specified name.

• `.shape`- A built-in function within the Pandas Library to measure the shape of a dataframe or series variable, it usually measures how many rows and columns a dataframe has. It outputs (X,Y), where X is the number of Rows and Y is the number of columns.

With the functions mentioned above, it allowed us to take specific cars with their rows and specific columns. Using `.loc`, it allows the author to acquire the
3 models with the conditions that they are equal to the said cars stated in the columns. The author used the OR `|` command in order to get the multiple car
models without uisng integer based location. Afterward, using the `.loc` command, the author could access specific columns and their elements.
This allows the author to extract all of the rows and columns with specific models and columns and store it a dataframe variable named `selected_cars`.
Finally with the `.shape` command, it allow us to retrieve the shape of the `selected_cars` variables.

``` python
selected_cars = cars.loc[(cars['Model'] == 'Datsun 710') | #--> makes the condition to extract the row Datsun 710 and follows and or value to allow other conditions
                        (cars['Model'] == 'Lotus Europa') | #--> makes the condition to extract the row Lotus Europa
                        (cars['Model'] == 'Ferrari Dino'),   #--> makes the condition to extract the row Ferrari Dino
                        ['Model', 'mpg', 'cyl', 'hp', 'gear']] #--> Shows only specific columns
selected_cars #--> Shows the selected cars
selected_cars.shape #--> shows the number of rows and columns aka shape of the variable.
```
Thank you for Reading!\
9/09/2026 - Submitted ipynb File\
9/09/2026 - Submitted first README file




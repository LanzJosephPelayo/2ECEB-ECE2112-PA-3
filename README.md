# 2ECEB-ECE2112-PA-3

**Made by: Lanz Joseph S. Pelayo || 2ECE-B**

# Introduction
This repository contains an explanation of the code for the programming assignment, which the author has made available for viewing. Specifically, the contents of this repository aim to address Programming Assignment #3, which comprises 3 problems, for the 2026-2027 academic year in ECE 2112. This aims to help viewers explain how the author used the program's functions to make it work, drawing on the author's knowledge of Python Data Analysis from module 3.

#0. Preliminary Setup:

The following commands were used in this problem to create an overall function used in the program:

• `import pandas as pd` - Command used to import the Python Data Analysis into the program in order to use the functions of the pandas Library by using pd as a shortcut. 

• `pd.read_csv` - Command used to read the csv file inserted in the compiler/notebook and introduce it to the program, allowing the data within the csv file to
be read and import to the program


#A. POSITIONAL AND LABEL-BASED SLICING
After loading cars, complete the following operations.
a. Display the shape and complete list of column names of cars.
b. Using positional slicing, create cars 6 to 10 containing rows 6 through 10 of the dataset, where
the first data row is row 1.
c. From cars 6 to 10, display only the columns Model, mpg, cyl, hp, and gear, in that order.

The following methods were used in this problem to create a unique function:

• `.shape`- A built-in function within the Pandas Library to measure the shape of a dataframe variable, it usually measures how many rows and columns does a 
dataframe has. It outputs (X,Y), where X is the number of Rows and Y is the number of columns.

Example: 
`cars.shape` --> (32,12) Meaning, 32 Rows and 12 Columns

• `.iloc[x,y]` - Integer Location, A built-in function within the Pandas Library, which outputs the value at specific rows X, where it can use a slice operation to take multiple rows and specific Y values where it can also be sliced from a dataframe variab;le.. It can mostly accept indexed based inputs within the X and Y values.

Example:
`cars.iloc[5:10]` ---> Extracts the dataframe data from Cars to output the rows from index 5 to 9, it also outputs all of the columns in rows 5 to 9.

•`.loc[[M],[N]` - Label Location,A built-in function within the Pandas Library, which itout puts the value at specific rows X and Y, where it can be used with slicing and even names of specific rows and columns that are wished to be output.

`cars.loc[:, ['Model','mpg','cyl','hp','gear']]` --> outputs every rows within the dataframe but only specific names of the stated columns were only ouputed.





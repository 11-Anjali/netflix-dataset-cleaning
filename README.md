# Guide to data cleaning

Save the column names in a list cause you’re going to work with it later, feel free to leave out useless ones

#### Problem 1 : missing values

Look for data that you’re missing and how much data you’re missing. Why ? idk. Jk, so your analysis won’t be unreliable cuz you’ve dealt with inconsistent data already

SO if the column has too much missing data, you have two options **calculate approximate values** and ****fill the missing values **(imputation)** or **drop those columns entirely.** If columns with more missing values are not important drop them else we’ll see

Check datatype of all columns, remove trailing spaces from strings

#### Problem 2 : NaN values

`NaN` means Not a Number in pandas. It is a special floating-point value that is different from `NoneType` in Python. `NaN` values can be annoying to work with, especially when you want to filter them out for plots or analysis.

Replace NaN with “” or “None” or “Fah” or any string.

#### Problem 3 : mixed values

This is the trickist to deal with, there can be multiple ways to approach this 

In our dataset : 

Dates being XX January XXXX which is a mix of  numbers and string you can choose to drop it or separate it into 3 different columns to make things easier

Duration column : It has 2 different type of data, it represents different concepts. 90 mins for movies and season 1, season 2 for shows. Two ways to handle this would be : 

1. Make two separate datasets, for movies and shows respectively
2. Split int and string (duration and unit): 90 → min ,  2 → seasons
    
    I went with option 2 as we already have a type column which tells us weather it’s a show or a movie, splitting a column would be easier and would preserve more information.
    

#### Problem 4 : Check for corrupted values

Beyond potentially missing values, there could be “unique” values that you can run into once you perform analysis. You can easily obtain unique values of a column using Python’s built-in function, `unique`.

# **ECE 2112_PA3**
### **Coded by: Vince Fredrick C. Dela Cruz (2ECE-A)**
This repository contains the Programming Assignment 3 for ECE 2112. The goal of this experiment/programming assignment is to use a .csv file and load it in a Pandas data frame to apply our knowledge in Pandas by solving programming problems such as label-based slicing, looking up data by using boolean indexing, and subsetting.

## **Initial Instructions:**
### Download the cars.csv dataset which is required for this experiment. The dataset contains a variety of vehicles and its variables.
### • Load the .csv file into a DataFrame and name it cars.
### • Use Pandas subsetting, slicing, indexing, and Boolean conditions for this experiment. **Do not manually type any requested table or answer.**
### • Do not modify values in cars; create a new DataFrame or Series for each requested subset.
### • Preserve the row order of the source dataset unless stated otherwise.
### • Makes sure to display the requested result/s in an executed notebook cell.
After doing the following, we can start solving the provided problems!

## **A. POSITIONAL AND LABEL-BASED SLICING**
Firstly, display the shape and the whole list of column names of cars. After that, use positional slicing to extract the data from rows 6 to 19 (label this as cars_6_to_10), with the first row being  row 1. (From this, make sure to ONLY display the columns Model, mpg, cyl, hp, and gear in that order)

**Requirement:** The row selection in part (b) must use iloc; the column selection in part (c) must
use column labels.

Example:
```python
cars = pd.read_csv('cars.csv')
car_names = cars[['Model']]
#Using positional slicing, create cars 6 to 10 containing rows 6 through 10 of the dataset, where the first data row is row 1
cars_6_to_10 = cars.iloc[[6,7,8,9,10]] # splices the list and grabs these rows.
cars_6_to_10 = cars_6_to_10[['Model', 'mpg', 'cyl', 'hp', 'gear']] # picks the specific data we want to grab from the list

cars_6_to_10.index = range(1, len(cars_6_to_10) + 1) # so the data row starts at 1
```
The expected output would be:
```python
car_names # this would produce a list of ONLY the car models from the .csv file

car_names.shape # shows the number of rows and columns of the car models

cars.shape # shows the number of rows and columns of the dateset in the .csv file

cars_6_to_10 # produces a list of the models and its variables from row 6 to 10
```

## **B. MODEL LOOKUP**
Using Boolean indexing (call it by the model to answer both requests), display the whole row for the Toyota Corolla, and the Pontiac Firebird (but only its Model, mpg, hp, and wt). Store the results in toyota and pontiac, respectively.

Example:
```python
toyota = cars.loc[(cars['Model']=='Toyota Corolla')] # takes the whole row of the model
pontiac = cars.loc[(cars['Model'] == 'Pontiac Firebird'), ['Model', 'mpg', 'hp', 'wt']] # takes these specific columns from a row
```
The expected output would be: 
```python
toyota # shows the entire row of the Toyota Corolla

pontiac # shows only the model name, mpg, hp, and wt of the Pontiac Firebird.
```

## **C. MULTI-MODEL SUBSETTING**
Createa a DataFrame that's named selected_cars that only contains the data for three models, specifically: Datsun 710, Lotus Europa, and Ferrari Dino. (Only get its Model, mpg, cyl, hp, and gear by selecting their rows by their model)

**Requirement:**
The final DataFrame must contain exactly three rows and five columns.

Example:
```python
m1 = cars.loc[(cars['Model']=='Datsun 710') | (cars['Model']=='Lotus Europa') | (cars['Model']=='Ferrari Dino')] # gets multiple rows
selected_cars = pd.DataFrame(m1, columns = ['Model','mpg','cyl', 'hp', 'gear']) # creates the new data frame
```
The expected output would be: 
```python
slected_cars # shows the model name, mpg, cyl, hp, and gear of the cars: Datsun 710, Lotus Europa, and the Ferrari Dino

selected_cars.shapee # shows the rows and columns of the list selected_cars, which is expected to have three rows and five columns.
```

# **Thank you!##

# Employee_Profile

# Prerequisites
Python 3.x
R (with required packages installed: readr, utils)

# Import Data
Run the Python script import_data.py to import the provided CSV file into your Jupyter Notebook.

python import_data.py

# Create Employee Function
Develop a Python function that accepts an employee's name as input and returns their details.

from employee_functions import get_employee_details

# Data Processing with Dictionary
Process the salary data using a Python dictionary.

from employee_functions import process_data_with_dictionary

# Error Handling
Implement error handling in your code to address potential issues gracefully.

try:
    # Your code that might raise exceptions
except Exception as e:
    print("An error occurred:", e)
    
# Export Employee Details
Export an employee's details to a CSV file and save it within a zipped folder named "Employee Profile."

from employee_functions import export_employee_details

# Unzip and Display Data with R
Use R to unzip the folder created in step 5 and display the data.

# Load necessary libraries
library(readr)
library(utils)

# Specify the path to the zip file
zip_file <- "Employee_Profile.zip"

# Specify the folder where you want to extract the contents
extract_folder <- "Employee_Profile"

# Create the folder if it doesn't exist
if (!file.exists(extract_folder)) {
  dir.create(extract_folder)
}

# Unzip the folder
unzip(zip_file, exdir = extract_folder)

# Now, read the CSV file inside the extracted folder
csv_file <- paste0(extract_folder, "/John Doe_details.csv")  # Adjust the filename as needed

# Read the CSV file into a data frame
employee_data <- read_csv(csv_file)

# Display the data
print(employee_data)

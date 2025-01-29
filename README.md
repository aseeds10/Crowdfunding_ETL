# Crowdfunding ETL Mini Project
By Arielmy M. & Kanha B.

## Table of Contents
- [Project Overview](#project-overview)
- [Technologies Used](#technologies-used)
- [Installation](#installation)
- [Features](#features)
- [Code Snippets](#code-snippets)
- [Acknowledgments](#acknowledgments)

---

## Project Overview  
This project focuses on building an ETL (Extract, Transform, Load) pipeline using Python, Pandas, and Python dictionary methods to process crowdfunding data. The goal of the project was to extract data from multiple sources, transform it to fit a defined structure, and load the transformed data into a PostgreSQL database for future use. We also added a noSQL alternative.

The team created four CSV files representing the processed data and designed an Entity Relationship Diagram (ERD) and table schema to visualize the relationships between data entities. Additionally, an optional visualization (pie charts) was created to analyze an interesting component of the resulting dataframe.

---

## Technologies Used
- **Python**: Used for scripting and data manipulation.
- **Pandas**: For data cleaning, transformation, and CSV file creation.
- **PostgreSQL**: Relational database for loading and storing transformed data.
- **Matplotlib**: For data visualization (optional pie charts).
- **Pymongo**: For MongoDB integration (optional for NoSQL database).
- **JSON, Numpy, Re**: For data parsing, numerical operations, and regular expressions.

---

## Installation  
1. Clone the repository to your local machine:
   ```bash
   git clone https://github.com/aseeds10/Crowdfunding_ETL.git
   ```
2. Install the required dependencies:
   ```bash
   pip install matplotlib pandas re json numpy
   ```
3. For **PostgreSQL** users:
   - Ensure PostgreSQL is installed on your system.
   - Import tables in the order defined by the schema due to table relationships.
4. For **MongoDB** users:
   - Install the **pymongo** package to use the NoSQL functionality.
   - Import the data using the `NOSQL_analysis.ipynb` file. Make sure you navigate to approriate cd in terminal.

---

## Features
- **ETL Pipeline**: Extracts, transforms, and loads crowdfunding data into a structured format.
- **CSV Data**: The transformed data is saved into four separate CSV files.
- **PostgreSQL Integration**: Loads data into a relational PostgreSQL database for future analysis.
- **MongoDB Integration**: Loads data into a noSQL (MongoDB) database for future analysis.
- **Entity Relationship Diagram (ERD)**: Designed a visual schema to map out the relationships between data tables.
- **Visualization**: Created pie charts to visualize an interesting component of the dataframe.

---

## Code Snippets  

### Extract and Transform Data  
This code snippet extracts data and transforms it into a structured format.  
```python
import pandas as pd

# Read JSON or other input files
data = pd.read_json('data.json')

# Perform data cleaning and transformation
data['cleaned_column'] = data['raw_column'].apply(some_transformation_function)
```

### Load Data into PostgreSQL  
This code demonstrates how to load data into a PostgreSQL database.  
```python
import psycopg2

# Establish database connection
conn = psycopg2.connect("dbname=test user=postgres password=secret")
cursor = conn.cursor()

# Insert data into the database
for index, row in transformed_data.iterrows():
    cursor.execute("""
        INSERT INTO table_name (col1, col2)
        VALUES (%s, %s)
    """, (row['col1'], row['col2']))
    
conn.commit()
conn.close()
```

### Optional Visualization: Pie Chart  
This snippet generates a pie chart to visualize a specific component of the dataset.  
```python
import matplotlib.pyplot as plt

# Sample data for pie chart
data = [25, 30, 45]
labels = ['Category A', 'Category B', 'Category C']

# Plot pie chart
plt.pie(data, labels=labels, autopct='%1.1f%%')
plt.title('Category Distribution')
plt.show()
```

---

## Acknowledgments  
Special thanks to Xpert Learning Assistant for assistance debugging.  
The dataset used in this project was provided as part of the *ETL Mini Project* from Rutgers Data Science Bootcamp.  

## datafun-06-eda

# Overview
Project 6: a customed EDA

## External Dependencies

- jupyterlab
- pandas
- pyarrow
- matplotlib
- seaborn

## Version Control with Git
 - Send to gGitHub
 ''' git add .
     git commit -m "comment"
     git push origin main"'

 - Retreive from GitHub
 ''' git checkout main
     git pull --rebase origin'''

### 1. Environment Setup

1. **Create** and **activate** the project virtual environment.
        '''python3 -m venv .venv
           source .venv/bin/activate'''
2. Install all required packages into your local project virtual environment from requirements.txt file
    ''' python3 -m pip install -r requirements. txt
3. Add a **.gitignore** file to your project with useful entries. Use [.gitignore](.gitignore) example.

### 2. Project Start
1. Create the Notebook: In the VS Code Explorer, create a new file i.e., ldooley_eda.ipynb. Ensure it has a .ipynb extension.
2. data to use for project
       https://github.com/mwaskom/seaborn-data/blob/master/titanic.csv
4. Verify your new notebook is open for editing. If needed, view the project files in VS Code Explorer and double-click the notebook file to open it for editing.  
5. Select a kernel : .venv python 3.12.2
6. Add a Markdown cell at the top of your notebook with the introduction (include the title, author, date and the purpose of the project).

### 3. Import Dependencies 
Add a Python cell next with the import statements for the libraries you will use in the project. Follow conventional package import organization and alias. Import each package just once near the top of the file. Be sure you have INSTALLED any external packages (outside the Python Standard Library) into your active project virtual environment first.

Jupyter Notebook / Python cell example:

'''import matplotlib.pyplot as plt
   import pandas as pd
   import seaborn as sns'''

execute cell to make sure imports are working properly. After running there should be no error messages.  * imports are good*


### 4. Exploratory Data Analysis
Perform a unique exploratory data analysis project using the tools and skills covered previously.

Step 1. Data Acquisition
 To read from the Seaborn dataset, use sns.load_dataset() function and pass in the 'Titanic' (the name without .csv) to populate our DataFrame. Print out the first few rows for refrence. 

Jupyter Notebook / Python cell example:

'''# Load the dataset into a pandas DataFrame - adjust this process for your custom data 
df = sns.load_dataset('titanic')'''   #make sure not to capitalize Titanic.
'''# Inspect first rows of the DataFrame
print(df.head())'''

Step 2. Initial Data Inspection
Display the first 10 rows of the DataFrame, check the shape, and display the data types of each column using df.head(10), df.shape, and df.dtypes.

Jupyter Notebook / Python cell example:

'''print(df.head(10))
   print(df.shape)
   print(df.dtypes)'''

Step 3. Initial Descriptive Statistics
Use the DataFrame describe() method to display summary statistics for each column.

Jupyter Notebook / Python cell example:

'''print(df.describe())'''

Step 4. Initial Data Distribution for Numerical Columns
Choose a numerical column and use df['column_name'].hist() to plot a histogram for that specific column. To show all the histograms for all numerical columns, use df.hist().

Jupyter Notebook / Python cell example:

'''# Inspect histogram by numerical column
   df['fare'].hist()'''

'''# Inspect histograms for all numerical columns
   df.hist()'''

'''# Show all plots
   plt.show()'''

Afterwards, use a Markdown cell to document your observations.

Step 5. Initial Data Distribution for Categorical Columns
Choose a categorical column and use df['column_name'].value_counts() to display the count of each category. Use a loop to show the value counts for all categorical columns.

Jupyter Notebook / Python cell example:

'''# Inspect value counts by categorical column
   df['sex'].value_counts()'''

'''# Inspect value counts for all categorical columns
   for col in df.select_dtypes(include=['object', 'category']).columns:
    
    # Display count plot
    sns.countplot(x=col, data=df)
    plt.title(f'Distribution of {col}')
    plt.show()'''

'''# Show all plots
   plt.show()'''

Afterwards, use a Markdown cell to document your observations.

Step 6. Initial Data Transformation and Feature Engineering
Use pandas and other tools to perform transformations. Transformation may include renaming columns, adding new columns, or transforming existing data for more in-depth analysis.

For this project, you must:

Rename at least one column.
Add at least one column

Step 7. Initial Visualizatio

Goal: The questions you are exploring.
        1. how many passenger in each class survived 
        2. The ages of the surviving passengers 
        3. The number of women, child, or men that survived.  
      Chart Type: Tell us what kind of chart you choose to illustrate this goal.
        1. countplot
        2. histogram
        3. countplot
Chart: Display the chart.

Story: Use Markdown cell(s) to document your observations and insights.

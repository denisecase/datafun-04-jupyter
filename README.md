# Specification for Project 4 Jupyter Notebook

## Overview

Project 4 uses a combination of Python and Markdown
to create an initial data story in a Jupyter Notebook.
The project includes a project virtual environment with
popular libraries for data analytics including pandas, matplotlib, and seaborn,
and introduces a common process for starting exploratory data analysis projects.

## Deliverable Names

- GitHub Repository:  **datafun-04-jupyter**
- Documentation:      README.md
- Notebook:           **yourname_eda.ipynb**

Create a new GitHub repository with a README.md.
Clone the project down to your machine, open in your favorite IDE,
and create a new Jupyter Notebook with the specified name.

## Version Control with Git

Use Git for version control.
In your README.md, document the steps of  initializing a new project in GitHub,
creating a Jupyter Notebook, and managing notebook versions with Git.
Explain the process for creating the repository in both places, and document
your workflow and commands as you edit, add, commit, and push to GitHub.

## Objective

Develop a Jupyter Notebook that demonstrates skills with Jupyter,
notebooks, working with Python and Markdown cells, and interactive execution.

## Requirements

### 1. Environment Setup

1. Create and activate a project virtual environment.
1. Install all required packages into your local project virtual environment.
1. After installing the required dependencies, update or generate your requirements.txt file.
1. Document the process and commands you used in your README.md.
1. Add a .gitignore file to your project with useful entries.

Windows example:

```Powershell
py -m venv .venv
.\.venv\Scripts\Activate.ps1
py -m pip install jupyterlab pandas matplotlib seaborn
py -m pip freeze > requirements.txt
```

Mac example:

```bash
python3 -m venv .venv
source .venv/bin/activate
python3 -m pip install jupyterlab pandas matplotlib seaborn
python3 -m pip freeze > requirements.txt
```

### 2. Project Start

Make sure Jupyter is installed and working in your project virtual environment.
Document the process and commands you used in your README.md.

For example, set up Jupyter using VS Code:

1. Install the Jupyter Extension: If not already installed, add the Jupyter extension to VS Code. This extension provides rich support for working with Jupyter notebooks.
2. Open the Project Folder: Open your project folder in VS Code.
3. Select the Python Interpreter: From the command palette (Ctrl+Shift+P), select "Python: Select Interpreter" and choose the interpreter from your virtual environment.

Then create, open, and start a new notebook:

1. Create the Notebook: In the VS Code Explorer, create a new file e.g., yourname_eda.ipynb. Ensure it has a .ipynb extension.
2. Open the Notebook: Double-click the notebook file to open it in the notebook editor.
3. Add a Markdown cell at the top of your notebook with a title, author, date and the purpose of the project.

### 3. Import Dependencies

Add a Python cell next with the import statements for the libraries you will use in the project.
Organize your project imports following conventions.

### 4.  Data Acquisition

Use the Iris dataset available in the Seaborn library. The Iris dataset is a well-known dataset in data science and machine learning, often used for various classification tasks and basic data exploration.

For example:

```python
import seaborn as sns
import pandas as pd

# Load the Iris dataset into DataFrame
df = sns.load_dataset('iris')

# Inspect first rows of the DataFrame
print(df.head())
```

### 5. Basic Data Exploration

First, use pandas to perform the basic data exploration tasks as the initial steps of
any data analysis project.

Step 1. Load Data into DataFrame

Load the data into a pandas DataFrame.
Use the pd read functions such as pd.read_csv() or pd.read_excel() as appropriate.

Step 2. Inspect Data w/head(), shape, and dtypes

Display the first 10 rows of the DataFrame, check the shape, and display the data types of each column using df.head(10), df.shape, and df.dtypes.

Step 3. Describe Summary Statistics

Use the DataFrame describe() method to display summary statistics for each column.

Step 4. Display Histograms for Numeric Columns

Choose a numerical column and use df['column_name'].hist() to plot a histogram for that specific column.

For example:

```python
import pandas as pd
import matplotlib.pyplot as plt

# Load data into DataFrame
df = sns.load_dataset('iris')

# Inspect data with head(), shape, and dtypes
print(df.head(10))
print(df.shape)
print(df.dtypes)

# Describe summary statistics
print(df.describe())

# Inspect histograms for numerical columns
df['column_name'].hist()
plt.show()
```

### 6. Data Transformation

Use pandas and other tools to perform transformations as needed.
Transformation may include renaming columns, adding new columns,
or transforming existing data for more in-depth analysis.
For example:

```python
# Renaming a column
df.rename(columns={'sepal_length': 'Sepal Length'}, inplace=True)

# Adding a new column
df['Sepal Area'] = df['Sepal Length'] * df['sepal_width']
```

### 7. Data Visualization

Create a variety of chart types using seaborn and matplotlib to showcase different aspects of the data.
There is a guided example in the resources section at the end of this document.
For example:

```python
sns.pairplot(df, hue='species')
plt.show()
```

### 8. Storytelling and Presentation

Interpret the visualizations and statistics to craft a narrative around your findings.
Present your findings in a logical and engaging manner.

## Notebook Design

- Begin your notebook with a project summary including the title, author, date, and project's purpose. This provides an immediate understanding of the notebook's objective.
- Ensure your code and presentation are neat, well-organized, and follow good coding practices. This includes proper variable naming, consistent code style, and logical organization of code cells.
- Use Markdown features effectively for formatting, such as section headings, bullet points, and emphasis (bold/italic), to enhance readability.

## Notebook Structure and Documentation

Once the notebook runs without errors, focus on how the notebook content is structured and documented.
Organize your notebook into well-defined sections, each with a clear purpose and header.
Use Markdown cells to provide context, explain your analysis, and share findings. This makes your notebook informative and engaging.
Comment your code cells to explain the purpose and functionality of the code. This is especially important for complex or non-obvious code segments.

## Notebook Execution

Run your notebook entirely to ensure it executes without errors. This includes checking all code cells and ensuring all data visualizations render as expected.
Confirm that your notebook renders correctly on GitHub after pushing, as this ensures your work is viewable by others.

## Evaluation Criteria

- Functionality: The project should be functional and meet all requirements.
- Documentation: The project should be well-written and well-documented.
- Presentation: The project should be presented in a clear and organized manner.
- Professionalism: The project should be submitted on-time and reflect an original, creative effort.

See rubric for additional information.

## Resources

- See [JUPYTER.md](JUPYTER.md) for Jupyter Notebook keyboard shortcuts and recommendations.
- See [MARKDOWN.md](MARKDOWN.md) for Markdown syntax and recommendations.
- See [Plotting graph For IRIS Dataset Using Seaborn And Matplotlib](https://www.tutorialspoint.com/plotting-graph-for-iris-dataset-using-seaborn-and-matplotlib)
- See [Seaborn Tutorial](https://seaborn.pydata.org/tutorial.html)

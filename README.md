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

## External Dependencies

This project requires the following external modules, so a virtual environment is recommended.

- pandas
- matplotlib
- seaborn

## Version Control with Git

- Create a new GitHub repository named `datafun-04-jupyter`.
- Clone the repository to your local machine.
- Document the steps and commands in your README.md.
- Document your workflow and commands as you edit, add, commit, and push changes to the GitHub repository.

## Objective

Develop a Jupyter Notebook that demonstrates skills with Jupyter and guided exploratory data analysis.

## Requirements

### 1. Environment Setup

1. **Create** and **activate** the project virtual environment.
1. Install all required packages into your local project virtual environment.
1. After installing the required dependencies, update or generate a  **requirements.txt** file.
1. Add a **.gitignore** file to your project with useful entries.
1. Document the steps and commands in your README.md.

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

```python
import matplotlib.pyplot as plt
import pandas as pd
import seaborn as sns
```

### 4.  Exploratory Data Analysis

Perform exploratory data analysis (EDA) using pandas and other tools as needed.
We will use the Seaborn library to load the Iris dataset.
Review the dataset here: [iris.csv](https://raw.githubusercontent.com/plotly/datasets/master/iris.csv) or see the local copy provided [iris.csv](iris.csv).

#### Step 1. Data Acquisition

Use the Iris dataset available in the Seaborn library.
The Iris dataset is a well-known dataset in data science and machine learning, often used for various classification tasks and basic data exploration.
Load the data into a pandas DataFrame.
Use the pd read functions such as pd.read_csv() or pd.read_excel() as appropriate.
For example:

```python
# Load the Iris dataset into DataFrame
df = sns.load_dataset('iris')

# Inspect first rows of the DataFrame
print(df.head())
```

#### Step 2. Initial Data Inspection

Display the first 10 rows of the DataFrame, check the shape, and display the data types of each column using df.head(10), df.shape, and df.dtypes.
For example:

```python

print(df.head(10))
print(df.shape)
print(df.dtypes)
```

#### Step 3. Initial Descriptive Statistics

Use the DataFrame describe() method to display summary statistics for each column.
For example:

```python
print(df.describe())
```

#### Step 4. Initial Data Distribution for Numerical Columns

Choose a numerical column and use df['column_name'].hist() to plot a histogram for that specific column.
To show all the histograms for all numerical columns, use df.hist().
For example:

```python
# Inspect histogram by numerical column
df['sepal_length'].hist()

# Inspect histograms for all numerical columns
df.hist()

# Show all plots
plt.show()
```

Afterwards, use a Markdown cell to document your observations.

#### Step 5. Initial Data Distribution for Categorical Columns

Choose a categorical column and use df['column_name'].value_counts() to display the count of each category.
Use a loop to show the value counts for **all** categorical columns.
For example:

```python
# Inspect value counts by categorical column
df['species'].value_counts()

# Inspect value counts for all categorical columns
for col in df.select_dtypes(include=['object', 'category']).columns:
    # Display count plot
    sns.countplot(x=col, data=df)
    plt.title(f'Distribution of {col}')
    plt.show()

# Show all plots
plt.show()
```

Afterwards, use a Markdown cell to document your observations.

#### Step 6. Initial Data Transformation and Feature Engineering

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

#### Step 7. Initial Visualizations

Create a variety of chart types using seaborn and matplotlib to showcase different aspects of the data.
There is a guided example in the resources section at the end of this document.
For example:

```python
sns.pairplot(df, hue='species')
plt.show()
```

After each visualization, use Markdown cells to document your observations and insights.

#### Step 8. Initial Storytelling and Presentation

Present your notebook with an opening that introduces yourself and your topic.
Use Markdown section headings to introduce each step.
Interpret the visualizations and statistics to narrate a clear and compelling data story.
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

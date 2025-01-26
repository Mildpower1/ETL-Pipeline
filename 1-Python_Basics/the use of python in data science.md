## The following Python basics should be known beforehand:
- Data Structure (List, Dictionary, Tuple and Sets)
- Conditions statements (if...else)
- Looping techniques (for loop and while loop)
- Functions
- Object-oriented Programming (OOP Python)
- Working with files (Open, read, write, append and close)
- Version control with Git tracking
- Local integrated development environments IDEs (Jupyter Notebook, PyCharm)
---
## Libraries:
Some of the most popular libraries of Python are:

- **Numpy** for scientific computing
- **Pandas** for data manipulation and analysis.
- **Matplotlib** for visualizing data.
- **Scikit-learn** to train machine learning models.

- And many more!
---
## Pandas
Pandas introduces the DataFrame class. A DataFrame is in the form of a matrix whose rows and columns each have an index. The main features of pandas are:

- data recovery from files (CSV, Excel tables, etc.)
- handling this data (deletion / addition, modification, statistical visualization, etc.)
---
## Data Loading
- **Read CSV file:** 
```python 
      df = pd.read_csv('filename.csv')
```
- **Read CSV with specific delimiter:** 
```python 
      df = pd.read_csv('filename.csv', delimiter=';')
```    
- **Read Excel file:** 
```python 
      df = pd.read_excel('filename.xlsx')
```      
- **Read from SQL Database:** 
```python 
      df = pd.read_sql(query, connection)
```      
- **Chunking large files:** 
```python 
      pd.read_csv('large_file.csv', chunksize=1000)
```      
- **Iterating through data chunks:** 
```python
        for chunk in pd.read_csv('file.csv', chunksize=500); process(chunk)
```
---
## Data Inspection
- **Display top rows:** 
```python 
      df.head()
```      
- **Display bottom rows:** 
```python
      df.tail()
```      
- **Display data type:** 
```python
      df.dtypes
```      
- **Summyry statistics:** 
```python
      df.describe()
```      
- **Display index, columns, and data:** 
```python
      df.info()
```      
---
## Data Cleaning
- **Check for missing values:** 
```python
      df.isnull().sum()
```      
- **Fill missing values:** 
```python
      df.fillna(value)
```
- **Drop missing values:** 
```python
      df.dropna()
```      
- **Rename columns:** 
```python
      df.rename(columns={'old_name': 'new_name'})
```      
- **Drop columns:** 
```python 
      df.drop(columns=['collumn_name'])
```   
---
## Data Transformation
- **Apply function:** 
```python
      df['column'].apply(lambda x: function(x))
```      
- **Group by and aggregate:** 
```python
      df.groupby('column').agg({'column': 'sum'})
```      
- **Group by multiple columns:** 
```python
      df.groupby(['col1', 'col2']).mean()
```      
- **Aggregate using multiple functions:** 
```python
      df.groupby('col').agg(['mean', 'sum'])
```      
- **Transform function:** 
```python
      df.groupby('col').transform(lambda x: x - x.mean())
```      
- **Pivot tables:** 
```python
      df.pivot_table(index='column1', values='column2', aggfunc='mean')
```      
- **Merge dataFrames:** 
```python 
      pd.merge(df1, df2, on='column')
```      
- **SQL-like joins:** 
```python
      pd.merge(df1, df2, how='left', on='col')
```      
- **Concatenate dataFrames:** 
```python
      pd.concat([df1, df2])
```      
- **Concatenating along a different axis:** 
```python 
      pd.concat([df1, df2], axis=1)
```      
- **Lambda function:** 
```python
      df.apply(lalmbda x: x+1)
```      
- **Pivot longer/wider format:** 
```python 
      df.melt(id_vars=['col1'])
```      
- **Stack/Unstack:** 
```python
      df.stack(), df.unstack()
```      
- **Cross tabulations:** 
```python
      pd.crosstab(df['col1'], df['col2'])
```      
---
## Data Visualization Integration
- **Histogram:** 
```python
      df['column'].hist()
```      
- **Boxplot:** 
```python
      df.boxplot(column=['column1', 'column2'])
```      
- **Scatter plot:** 
```python
      df.plot.scatter(x='col1', y='col2')
```      
- **Line plot:** 
```python
      df.plot.line()
```      
- **Bar chart:** 
```python
      df['column'].value_counts().plot.bar()
```      
- **Custom plotting:** 
```python
      import matplotlib.pylot as plt; df.plot(); plt.show()
```      
 
- **Customize plot style:** 
```python
      plt.style.use('ggplot')
```      
- **Histogram using bins specification:** 
```python
      df['column'].hist(bins=20)
```      
- **Boxplot grouped by category:** 
```python
      df.boxplot(column='num_column', by='cat_column')
```      
---
## Statistical Analysis
- **Correlation matrix:** 
```python
      df.corr()
```      
- **Covariance matrix:** 
```python
      df.cov()
```      
- **Value counts:** 
```python 
      df['column'].value_counts()
```      
- **Unique values in column:** 
```python
      df['column'].unique()
```      
- **Number of unique values:** 
```python
      df['column'].nunique()
```      
---
## Indexing and Selection
- **Select column:** 
```python
      df['column']
```      
- **Select multiple columns:** 
```python
      df[['col1', 'col2']]
```      
- **Select rows by position:** 
```python 
      df.iloc[0:5]
```      
- **Select rows by lable:** 
```python
      df.loc[0:5]
```      
- **Conditional selection:** 
```python 
      df[df['column']> value]
```      
- **Query function:** 
```python
      df.query('column'> value')
```      
- **Filtering using isin:** 
```python
      df[df['column'].isin([value1, value2])]
```      
- **Creating multiIndex:** 
```python
      df.set_index(['col1', 'col2'])
```      
- **Slicing on multiIndex:** 
```python
      df.loc[(slice('index1_start', 'index1_end'), slice('index2_start', 'index2_end))]
```      
---
## Data Formatting and Conversion
- **Convert data types:** 
```python
      df['column'].astype('type')
```      
- **String operations:** 
```python
     df['column'].str.lower()
```     
- **Datetime conversion:** 
```python
      pd.to_datetime(df['column'])
```      
- **Setting index:** 
```python
      df.set_index('column')
```      
---
## Handling Time Series Data
- **Set datetime index:** 
```python
      df.set_index(pd.to_datetime(df['date']))
```      
- **Resampling data:** 
```python
      df.resample('M').mean()
```      
- **Rolling window operations:** 
```python
      df.rolling(window=5).mean()
```      
---
## File Export
- **Write to csv:** 
```python
      df.to_csv('filename.csv')
```      
- **Write to excel:** 
```python
      df.to_excel('filename.csv')
```      
- **Write to SQL Database:** 
```python
      df.to_sql('table_name', connection)
```      
---
## Data Exploration Techniques
- **Profile report using pandas-profiling:**
```python
      from pandas-profiling import profileReport; profileReport(df)
```      
- **Pairplot using seaborn:** 
```python
      import seaborn as sns; sns.pairplot(df)
```      
- **Heatmap for correlation using seaborn:**
```python
      sns.heatmap(df.corr(), annot=True)
```      
---  
## Data Merging Techniques
- **Outer join:** 
```python
      pd.merge(df1, df2, on='column', how='outer')
```      
- **Inner join:** 
```python
      pd.merge(df1, df2, on='column', how='inner')
```      
- **Left join:** 
```python
      pd.merge(df1, df2, on='column', how='left')
```      
- **Right join:** 
```python
      pd.merge(df1, df2, on='column', how='right')
```      
---
## Dealing using Duplicates
- **Finding Duplicates:** 
```python
      df.duplicated()
```      
- **Removing Duplicates:** 
```python
     df.drop_duplicates()
```
---
## Custom Operations using Apply
- **Custom apply functions:** 
```python
      df.apply(lambda rom:custom_func(row['col1'], row['col2'), axis=1]
```      
---
## Performance Tuning
- **Using swifter for faster apply:**
```python
      import swifer; df['column'].swifter.apply(lambda x: func(x))
```      
- **Parallel processing using dask:** 
```python
      import dask.dataframe as dd; ddf= dd.from_pandas(df, npartitions=10)
```      
---  
## Data Normalization and Standardization
- **Min-Max Normalization:** 
```python
      (df['column'] - df['column'].min()) /(df['column'].max() - df['column'].min())
```      
- **Z-score standardization:** 
```python
     (df['column'] - df['column'].mean()) /(df['column'].std()
```     
---
## Working with JSON and XML
- **Reading JSON:** 
```python
      df = pd.read_json('filename.json')
```      
- **Reading XML:** 
```python
      df = pd.read_xml('filename.xml')
```      
- **Writing to JSON:** 
```python
      df.to_json('filename.json')
```
---
## Dealing with Missing Data
- **Interpolate missing values:** 
```python
      df['column'].interpolate()
```      
- **Forward fill missing values:** 
```python
      df['column'].ffill()
```      
- **Backward fill missing values:** 
```python
      df['column'].bfill()
```      
---
## Working with External Data Source
- **Reading data from HTML:** 
```python
      dfs = pd.read_html('http://example.com')
```
- **Connecting to a SQL database:**
```python  
      from sqlalchemy import create_engine
      engine = create_engine('sqlite:///db.sqlite')
      df = pd.read_sql('SELECT * FROM tabel_name', engine)
```



    

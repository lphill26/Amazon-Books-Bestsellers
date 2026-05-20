# Problem Statement
    An analysis on amazons best selling books based on their genre, price, user ratings and user reviews. 

# Data Cleaning
    a) Load the data using Pandas library: df = pd.read_csv('bestsellers.csv')
    b) Exploratory Analsis: df.head(), df.info(), df.describe()
    c) Checking for null values: df.isna().sum()
    d) Checking for duplicates: df.duplicated().sum()

# Percentile Distributions of Numerical Columns
    df['numerical column'].quantile([0.25, 0.5, 0.75])

# Analysis of Categorial Columns
    a) df['categorial column'].value_counts()
    b) df['categorial column'].nunique()

# Comparsions Across Categories
    a) Grouping the best selling book names by the price
        df.groupby('Name')['Price'].agg(['mean', 'median', 'count'])

    b) Grouping the best selling book names by the reviews
        df.groupby('Name')['Reviews'].agg(['mean', 'median', 'count'])
    
    c) Grouping the best selling book names by the user ratings
        df.groupby('Name')['User Rating'].agg(['mean', 'median', 'count'])

    d) Grouping the genre types by reviews
        df.groupby('Genre')['Reviews'].agg(['mean', 'median', 'count'])

    e) Grouping the genre types by price
        df.groupby('Genre')['Price'].agg(['mean', 'median', 'count'])

    f) Asociation between best selling books and their genres
        pd.crosstab(df['Name'], df['Genre'])

# Visualization

    a) Histogram of the number of reviews per book: df['Reviews'].hist()
    b) Bar chart of genre type of book: df['Genre'].value_counts().plot(kind='bar')
    c) Boxplot grouped by the genre and price: df.boxplot(column='Price', by='Genre')
    d) Scatter plot of the user ratings and price: df.plot.scatter(x='User Rating', y='Price')
    e) Correlation Heat Map: df.corr(numeric_only=True).style.background_gradient(cmap='coolwarm')

# Results
    a) There are 310 non fiction books and 240 fiction books making a total of 550 books.
    b) The year 2015 had the most best selling books at 5. 
    c) The book WONDER was a best selling book in 2015 with the most User Reviews at 21625. 
    d) The Book Wrecking Ball (Diary of a Wimpy Kid Book 14) had the most User Ratings at 4.9. 
    e) The genre Non Fiction had the most best selling books, highest reviews, and cost the most.
    f) The lower the price of book, the high user satisfaction rating. 

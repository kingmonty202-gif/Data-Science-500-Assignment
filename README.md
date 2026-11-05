# Data-Science-500-Assignment

https://github.com/kingmonty202-gif/Data-Science-500-Assignment.git

Data Science 500 Assignment
1. Project overview

This project is an end-to-end data science workflow on Books to Scrape, a practice website for web scraping. It scrapes all 1 000 books, cleans the data, explores price, rating and genre patterns with charts, and builds a Linear Regression model to estimate book price.

2. Files in this submission
File	Description
Book_Market_Analytics.ipynb	Jupyter Notebook with the full pipeline: scraping, cleaning, visualisation, modelling and interpretation
raw_books.csv	Raw scraped data (1 000 rows, 8 columns), created by the notebook
clean_books.csv	Final cleaned dataset (1 000 rows, 12 columns), created by the notebook
Book_Market_Analytics_Report.pdf	Professional project report (exported from the Word version)
README.md	This file
3. Requirements
Python 3.9 or newer
Jupyter Notebook or JupyterLab
An internet connection (for scraping)

Install the libraries:

pip install requests beautifulsoup4 pandas matplotlib scikit-learn notebook
4. How to run the project
Put Book_Market_Analytics.ipynb in a folder of your choice.
Open it with Jupyter (jupyter notebook).
Run all cells from top to bottom (Kernel > Restart & Run All).
The scraping step takes a few minutes. For a quick test, set MAX_PAGES = 2 in the scraping cell. The full run uses MAX_PAGES = 50.
When it finishes, raw_books.csv and clean_books.csv appear in the same folder as the notebook.

Note: the notebook saves files with relative paths, so the CSV files are created wherever the notebook is run.

5. Notebook structure
Data acquisition: uses requests and BeautifulSoup to loop through all 50 catalogue pages, then opens each book page for category, stock quantity and description.
Data cleaning: removes duplicates, fills missing descriptions, converts price to a number, converts star ratings (One to Five) to 1 to 5, extracts stock quantity, and tidies the text fields.
Visualisation: price histogram, ratings count, price by rating box plot, top genres by count, average price by genre, scatter plots, and a correlation heatmap.
Predictive modelling: Linear Regression with an 80/20 train-test split, evaluated with MAE, RMSE and R-squared against a baseline.
Conclusions: summary of insights, limitations and recommendations.
6. Dataset description (clean_books.csv)
Column	Meaning
title	Book title
category	Genre (as listed on the website)
price	Price in GBP
rating	Star rating as a word (One to Five)
rating_num	Star rating as a number (1 to 5)
availability	Stock status text (In stock / Out of stock)
in_stock	1 if in stock, 0 if not
quantity	Number of copies available
title_length	Number of characters in the title
description_length	Number of characters in the description
description_words	Number of words in the description
description	Cleaned (lower case) book description
7. Key results
1 000 books were collected, with only 2 missing descriptions and no duplicates.
Prices range from £10.00 to £59.99 (mean £35.07) and are spread fairly evenly.
Price has almost no relationship with star rating, stock quantity, title length or description length (all correlations within 0.03 of zero).
Travel and Fantasy are the most expensive genres on average; Food and Drink, Thriller and Mystery are the cheapest.
The Linear Regression model scored R-squared = -0.022 and MAE = £12.69, against a baseline MAE of £12.66, so it does not predict price better than guessing the average.
8. Limitations
Books to Scrape is a practice site, so its prices appear to be close to random rather than driven by real market factors.
Only simple features were used; author, publisher and format are not available.
"Default" and "Add a comment" are website placeholder labels, not true genres.
Linear Regression captures only straight-line relationships.
9. References
Books to Scrape (2026) Books to Scrape. Available at: https://books.toscrape.com
Hunter, J.D. (2007) 'Matplotlib: a 2D graphics environment', Computing in Science & Engineering, 9(3), pp. 90-95.
McKinney, W. (2010) 'Data structures for statistical computing in Python', Proceedings of the 9th Python in Science Conference, pp. 56-61.
Pedregosa, F. et al. (2011) 'Scikit-learn: machine learning in Python', Journal of Machine Learning Research, 12, pp. 2825-2830.
Richardson, L. (2007) Beautiful Soup documentation. Available at: https://www.crummy.com/software/BeautifulSoup/

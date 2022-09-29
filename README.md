# edgar-stock-analysis
Gathering company data using edgar and yfinance and then using machine learning to analyze the data

Overall Goal:

Get recommendations for companies which will perform well on a 2-5+ year timescale to invest in.

Overview:

All public company fundametal financial data from 1994 is stored in an SEC database named Edgar. They have mutliple ways to access data. The easiest way is via an API, however that only retieves data from 2009. This is what the current code uses, next steps for the code include retriving all the stored years of data from xbrl or raw text files.

This Edgar data can then be combined with any desired source of stock price data. An easy free source is yahoo finance, via the yfinance library. 

Once the data is gathered, aggregated and cleaned up, it can then be analyzed in any way desired. Curretly the data is analyzed via linear regression with some feature engineering, however no strong trends are seen using this method of analysis. Next steps are to use more advanced algorithms, potentially a neural network coupled with more data.

Structure:

Getting the fundamental data from Edgar is split into two files, one 'get-revenue-income-price.ipynb' which gets the revenue, income and stock price (from yfinance), and another which adds on the PE ratio 'add-pe-ratio.ipynb' (the first file was getting a bit long and getting all the stock price data for so many tickers is relatively slow and doing it multiple times should be avoided if possible).

To transfer data between files, and avoid refetching of data from Edgar and yfinance, the data is stored as a csv at the end of each file, so it can then be accessed from other files.

The 'code' files have the jupyter notebooks, and the 'supporting' files have the csvs and any other relevant data files.

The linear regression is again split into two files, one to preprocess the data 'preprocessing-for-linear-regression.ipynb' and another to actually perform the linear regression 'linear-regression.ipynb.

Output:

See the output images folder for the current ouput of the analyses.

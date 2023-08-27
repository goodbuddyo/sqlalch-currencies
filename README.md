# SQLAlch-Currencies README

This SQLAlch-Currencies app demonstrates the use of Python and the Click package to create a CLI for returning crypto currency investment info stored in a SQLite DB. The currency, date and current price data is provided with the assistance of a free but limited api from CoinGecko https://www.coingecko.com/ 

The SQLAlch-Currencies app is based an awesome Pluralsight tutorial by Douglas Starnes who pateiently explains how the app works, line by line. https://www.pluralsight.com/

Part 1 of this app (SQLAlch-Currencies) uses only SQL statements to populate an SQLite DB. 

In a separate, part 2 app (SQLAlch-Currencies-2) a separate SQLite DB will be populated using the SQLAlchemy ORM and Core API. Comparing both SQL and SQLAlchemy methods helps demonstrate some of the pros and cons of both methods.


### SQLAlch-Currencies Getting Started

After cloning the SQLAlch-Currencies repo, cd to the folder, create a venv and install the requests and click packages.

$ python -m venv venv
$ source venv/bin/activate
(venv) $ python -m pip install requests 
(venv) $ python -m pip install click

The other imported packages are already part of the Python Standard Library

  click 
  sqlite3
  datetime
  csv


----------------------------------
CLI request examples: 

A simple test
Request the current price of the default crypto currency: bitcoin in usd  
(venv) $ python get_price.py

Request the current price of specific crypto currencies by specifying coin_id and currency
(venv) $ python main.py show-coin-price --coin_id=ethereum --currency=gbp

Add an investment to the db, specify coin_id, currency and amount
(venv) $ python main.py add-investment --coin_id=bitcoin --currency=usd --amount=1

Calculate the total value of a crypto currency you own (as listed in the db)
in the currency specified
(venv) $ python main.py get-investment-value --coin_id=bitcoin --currency=usd

Import multiple crypto currency investments into the db from a .csv file.
(venv) $ python main.py import-investments --csv_file investments.csv

----------------------------------

This CLI provides only a limited number of commands to demonstrate the use of SQL for populating an SQLite db.

The Part 2 app SQLAlch-Currencies-2 will demonstrate additional commands using SQLAlchemy
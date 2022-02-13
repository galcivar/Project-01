# Twitter's Impact on Cryptocurrency

### This project aims to find correlations between Tweets and the price fluctuations of cryptocurrency.

Below are questions we would like to research:

1. How does Twitter impact cryptocurrency prices?
   - How are top accounts correlated with price fluctuations?
   - Is it worth tracking accounts to inform investment decisions?
2. Should investors use Twitter to analyze cryptocurrency price movement?

Here are the criteria we used for this project:

- Timeframe: With Twitter's API limitations, we were only able to retrieve 7 days worth of data.
- Coins: Bitcoin, Ethereum, Solana

---

## Technologies

This project leverages python 3.9 and Jupyter lab notebook was used to run all analysis.

We used the following datasets to gather information:

- [CoinGecko API](https://www.coingecko.com/en/api/documentation) - it is an independently sourced collection of crypto data that includes metrics, such as live prices, trading volume, exchange volumes, trading pairs, historical data, contract address data, crypto categories, crypto derivatives, images and more.
- [Twitter API](https://developer.twitter.com/en/docs/twitter-api) - it is a set of programmatic endpoints that can be used to understand or build the conversation on Twitter. This allows you to retrieve, engage with, or create a variety of different resources including Tweets, users, spaces, direct messages, etc.

---

## Installation Guide

Before running the application first import the following libraries and dependencies.

Instsall Tweepy

```python
pip install tweepy
```

Install CoinGecko

```python
pip install pycoingecko
```

Imports

```python
import tweepy
from dotenv import load_dotenv
import os
import json
import pandas as pd
import hvplot.pandas
from datetime import datetime, timedelta
import time
from bokeh.models.formatters import DatetimeTickFormatter
from pycoingecko import CoinGeckoAPI
```

---

## Data Collection

To make the API calls, make sure to have your Twitter API Keys loaded and set the CoinGecko variable as the following:

```python
cg = CoinGeckoAPI()
```

Next, set up dictionaries to capture all terms associated with each coin

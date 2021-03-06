# Alternative-Bars
Generate Alternative Bars in real-time leveraging Alpaca API. User can generate bars like tick bars, volume bars and dollar bars.

This project was inspired by the book [Advances in Financial Machine Learning](https://www.amazon.co.uk/Advances-Financial-Machine-Learning-Marcos/dp/1119482089).

## Installation
The algorithm was tested on the Alpaca Trade API version mentioned the requirements file and is considered as the stable version for this project.
 
```bash

pip install -r requirements.txt
```

## Usage

To generate Alternative user first need to have a Alpaca API either from a Paper Trading account or a Brokerage account. If you don't have one you can open a paper trade account  for free by visiting [Alpaca.market]([alpaca.market) and signing up.

### 1) Setting up the config file

User first need to set-up the [config file](https://github.com/Harkishan-99/Alternative-Bars/blob/master/config.cfg) with there Alpaca API credentials.

```python
[alpaca]
api_key = "enter your api key here without quotes"
api_secret = "enter your api secret here without quotes"
base_url = https://paper-api.alpaca.markets
```

### 2) Getting Bars

```python
from bars import get_tick_bars, get_volume_bars, get_dollar_bars

#assets for receiving the event-driven bars
symbols = ['AAPL','TSLA','AMZN']
#setting static threshold for individual stocks for different bars
tick_bar_threshold = {'AAPL':1000,'TSLA':1000,'AMZN':1000}
volume_bar_threshold = {'AAPL':50000,'TSLA':5000,'AMZN':50000}
dollar_bar_threshold = {'AAPL':2000000,'TSLA':2000000,'AMZN':2000000}

#setup for receiving tick bars for given thresholds
get_tick_bars(symbols, tick_bar_threshold, 'sample_datasets')
#setup for receiving volume bars for given thresholds
get_volume_bars(symbols, volume_bar_threshold, 'sample_datasets')
#setup for receiving tdollar bars for given thresholds
get_dollar_bars(symbols, dollar_bar_threshold, 'sample_datasets')
```

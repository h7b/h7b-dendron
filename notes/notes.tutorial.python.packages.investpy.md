---
id: r3925ifilsti58022929u3t
title: Investpy
desc: 'Investpy'
updated: 1671231099465
created: 1654297491068
---
# Investpy

- [Investpy](https://github.com/alvarobartt/investpy) is a Python package to retrieve financial and cryptocurrencies related data from [Investing.com](https://www.investing.com/)
- [Documentation](https://investpy.readthedocs.io/index.html)
- Status: replaced by [investiny](https://github.com/alvarobartt/investiny)

## Usage

## Multiple stocks in a single website request

ref: [issue 488](https://github.com/alvarobartt/investpy/issues/488)

Query historical data for multiple stocks in a single website request

```python
import time
stocks = ["A", "B"]
for stock in stocks:
    data = investpy.get_stock_historical_data(stock=stocks, 
                                            country='XXX',
                                            from_date='01/01/2020',
                                            to_date='01/01/2021')
   time.sleep(5)
```
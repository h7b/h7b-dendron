---
id: r3925ifilsti58022929u3t
title: Investpy
desc: ''
updated: 1654299778645
created: 1654297491068
---
# [Investpy](https://github.com/alvarobartt/investpy)

- Investpy is a Python package to retrieve financial and cryptocurrencies related data from [Investing.com](https://www.investing.com/)
- [Documentation](https://investpy.readthedocs.io/index.html)

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
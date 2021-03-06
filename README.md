# Crypto Currencies Stocks

Crypto currencies stocks (ccs) is Python package for communication with stocks which are traiding with crypto currencies. This library has two levels:

* basic stock's API

* unificated API (build over basic API)

Instalation
===========

This package is part of pypi.  Command for instalation is:

```bash
    $ pip intall ccs
```

Documentation
=============
Full documentation is [here](http://cryptocurrenciesstocks.readthedocs.io). This documentation is still under construction.


Examples of using basic API
===========================

Tickers
-------
```python
str_response = ccs.bitfinex.public.ticker("btcusd")
str_response = ccs.bittrex.public.getMarketSummary("btc-ltc")
str_response = ccs.cexio.public.ticker("BTC", "USD")
# ...
```

Trades
------
```python
str_response = ccs.bitfinex.public.trades("btcusd")
str_response = ccs.bitstamp.public.transactions("btcusd")
str_response = ccs.kraken.public.getRecentTrades("XBTEUR")
# ...
```

Orderbook
---------
```python
str_response = ccs.bitfinex.public.orderbook("btcusd")
str_response = ccs.btce.public.depth("btc_usd")
str_response = ccs.okcoincom.public.depth("btc_usd")
# ...
```
Examples of using unificated API
================================

Unificated Ticker
-----------------
```python
import ccs

stock = ccs.constants.BITFINEX
cur1 = ccs.constants.BTC
cur2 = ccs.constants.USD

ticker = ccs.ticker(stock, cur1, cur2)

# Available atributes and methods
ticker.high()
ticker.low()
ticker.ask()
ticker.bid()
ticker.timestamp()
ticker.dt() # datetime
ticker.volume24h()
ticker.spread()
str(ticker)
```

Unificated Trades
-----------------

```python
trades = ccs.trades(stock, cur1, cur2)

# Available atributes and methods
len(trades)
str(trades)

for trade in trades:
  trade.tid()
  trade.price()
  trade.amount()
  trade.type()
  trade.timestamp()
  trade.dt()

```

Unificated Orderbook
--------------------

```python
orderbook = ccs.orderbook(stock, cur1, cur2)

# Available atributes and methods
for order in orderbook.asks():
  order.price()
  order.amount()

```


Supported stocks
================

| Stock      | Link                      |
|------------|---------------------------|
| Bitfinex   | https://www.bitfinex.com/ |
| Bitstamp   | https://www.bitstamp.net/ |
| Bittrex    | https://bittrex.com/      |
| Btcc       | https://www.btcc.com/     |
| Btce       | https://btc-e.com/        |
| Bter       | https://bter.com/         |
| Cex.io     | https://cex.io/           |
| Kraken     | https://www.kraken.com/   |
| Okcoin.com | https://www.okcoin.com/   |
| Okcoin.cn  | https://www.okcoin.cn/    |
| Poloniex   | https://poloniex.com/     |



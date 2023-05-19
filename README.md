<h2 align="center">⭐️Binance Trader (RC 3) (WINDOWS LINUX MAC)⭐️</h2>
    
<h4 align="center">⭐️ DO YOU TIRED OF BEAR MARKET ? USE BOTS FOR 24H TRADES ⭐️</h4>
    
<h4 align="center">⭐️ This is an experimental bot for auto trading the binance.com exchange ⭐️</h4>
      
## UPDATE NEW VERSION 2022
   
    - MACD indicator (buy/sell)
    - Stop-Loss implementation
    - Working modes
      - profit: Find defined profit, buy and sell. (Ex: 1.3% profit)
      - range:  Between target two price, buy and sell. (Ex: <= 0.00100 buy - >= 0.00150 sell )
      
    
![Screenshot](https://github.com/seeememagaiin/BINANCE-Auto-Trader-MACD-indicator-buy-sell-2022/blob/main/img/example.png)

## Configuration

1. [Signup](https://www.binance.com/) for Binance
2. Go API Center, [Create New](https://www.binance.com/) Api Key

5. Get an API and Secret Key, insert into `app/config.py`

        API key for account access
        api_key = ''
        Secret key for account access 
        api_secret = ''

        [API Docs](https://www.binance.com/restapipub.html)

6. Optional: Modify recv_window value (not recommended)

7. Optional: run as an excutable application in Docker containers


## Requirements

    sudo pip install requests

    Python 3
        import os
        import sys
        import time
        import config
        import argparse
        import threading
        import sqlite3

## Usage (trading module)

    python trader.py --symbol XVGBTC

    Example parameters

    # Profit mode (default)
    python trader.py --symbol XVGBTC --quantity 300 --profit 1.3
    or by amount
    python trader.py --symbol XVGBTC --amount 0.0022 --profit 3

    # Range mode
    python trader.py --symbol XVGBTC --mode range --quantity 300 --buyprice 0.00000780 --sellprice 0.00000790
    or by amount
    python trader.py --symbol XVGBTC --mode range --amount 0.0022 --buyprice 0.00000780 --sellprice 0.00000790

    --quantity     Buy/Sell Quantity (default 0) (If zero, auto calc)
    --amount       Buy/Sell BTC Amount (default 0)
    --symbol       Market Symbol (default XVGBTC or XVGETH)
    --profit       Target Profit Percentage (default 1.3)
    --stop_loss    Decrease sell price at loss Percentage (default 0)
    --orderid      Target Order Id (default 0)
    --wait_time    Wait Time (seconds) (default 0.7)
    --increasing   Buy Price Increasing  +(default 0.00000001)
    --decreasing   Sell Price Decreasing -(default 0.00000001)
    --prints       Scanning Profit Screen Print (default True)
    --loop         Loop (default 0 unlimited)

    --mode         Working modes profit or range (default profit)
                   profit: Profit Hunter. Find defined profit, buy and sell. (Ex: 1.3% profit)
                   range: Between target two price, buy and sell. (Ex: <= 0.00000780 buy - >= 0.00000790 sell )

    --buyprice     Buy price (Ex: 0.00000780)
    --sellprice    Buy price (Ex: 0.00000790)

    Symbol structure;
        XXXBTC  (Bitcoin)
        XXXETH  (Ethereum)
        XXXBNB  (Binance Coin)
        XXXUSDT (Tether)

    All binance symbols are supported.

    Every coin can be different in --profit and --quantity.
    If quantity is empty --quantity is automatically calculated to the minimum qty.

    Variations;
        trader.py --symbol TBNBTC --quantity 50 --profit 3
        trader.py --symbol NEOBTC --amount 0.1 --profit 1.1
        trader.py --symbol ETHUSDT --quantity 0.3 --profit 1.5
        ...

## Usage (balances module)

    python balance.py

## Run in a Docker container

    docker build -t trader .

    docker run trader



## License

Code released under the [MIT License](https://opensource.org/licenses/MIT).

---

# money printer

## Installation
    $ git clone https://github.com/assassinen/grid_client.git
    $ cd grid_client

## Settings 
* change the settings for the bot `settings/grid_settings.json`:
```yaml
[
  {
    "py/object": "models.settings.GridSettings"
    "API_KEY": "your_API_KEY_for_bitmex",       # set your API_KEY
    "GRID_DEPTH": 5,                            # maximum number of orders                               
    "GRID_SIDE": "buy",                         # direction of orders to open a position
    "ORDER_SIZE": 50,                           # lot size
    "ORDER_SPREAD": 10,                         # profit value from each order
    "ORDER_STEP": 30,                           # price difference between orders
    "START_STEP": 5,                            # the difference in the price of the first order and the market price
    "FREQUENCY_RATE": 0.05,                     # the multiplicity of rounding prices
    "REVERSE_SIDE": "sell",                     # direction of orders to close a position
    "SYMBOL": "XBTUSD",                         # trading instrument
    "active": false,                            # set true to the robot worked
    "strategy": "average_price"                 # trading strategy name
  }
]
 ```
* change the settings for the exchange `settings/exchange_settings.json`:
```yaml
[
  {
    "py/object": "models.settings.ExchangeSettings",
    "API_KEY": "your_API_KEY_for_bitmex",                 # your API KEY
    "API_SECRET": "your_API_SECRET_for_bitmex",           # your API_SECRET   
    "API_URL": "/api/v1/",                                # API version
    "BASE_URL": "https://testnet.bitmex.com",             # exchange url (e.g https://www.bitmex.com, https://www.deribit.com)
    "EXCHANGE": "bitmex",                                 # exchange name (e.g bitmex, deribit)
    "LOOP_INTERVAL": 5
  },
]
```

## Getting started
Download [Docker Desktop](https://www.docker.com/products/docker-desktop) for Mac or Windows. [Docker Compose](https://docs.docker.com/compose) will be automatically installed. On Linux, make sure you have the latest version of [Compose](https://docs.docker.com/compose/install/). 

## Run the bot:
    $ docker-compose up -d
    
## To see the logs:
    $ docker-compose logs -f
    
## To update the container:
    $ docker-compose pull

## Stop the bot:
    $ docker-compose stop
    
## Example logs:
```
$ docker-compose logs -f
Attaching to gridclient_money_printer_1
money_printer_1  | 2019-09-13 09:00:28,233 - average_price.7w566cLl - positions: {'average_price': 0.0, 'size': 0.0}
money_printer_1  | 2019-09-13 09:00:28,234 - average_price.7w566cLl - open_orders: [{'price': 176.8, 'orderQty': 10, 'side': 'buy'}]
money_printer_1  | 2019-09-13 09:00:28,234 - average_price.7w566cLl - last_trade_price: 179.2
money_printer_1  | 2019-09-13 09:00:28,234 - average_price.7w566cLl - last_order_price: 179.2
money_printer_1  | 2019-09-13 09:00:28,234 - average_price.7w566cLl - existing_orders_price: [176.8]
money_printer_1  | 2019-09-13 09:00:28,234 - average_price.7w566cLl - design_orders_price: []
money_printer_1  | 2019-09-13 09:00:28,234 - average_price.7w566cLl - grid calculated: {'price': 174.2, 'orderQty': 10, 'side': 'buy'}
money_printer_1  | 2019-09-13 09:00:28,234 - average_price.7w566cLl - reverse calculated: {}
money_printer_1  | 2019-09-13 09:00:28,450 - orders_manager.7w566cLl - Canceling 1 orders:
money_printer_1  | 2019-09-13 09:00:28,450 - orders_manager.7w566cLl -  buy 10 @ 176.80
money_printer_1  | 2019-09-13 09:00:28,663 - orders_manager.7w566cLl - Creating 1 orders:
money_printer_1  | 2019-09-13 09:00:28,872 - orders_manager.7w566cLl -  buy 10 @ 174.20
````
# Сontacts
email: assassinen@ya.ru

# money printer
Money printer is a bot designed for cryptocurrency trading. The bot is able to trade on www.deribit.com and www.bitfinex.com. In order to use the bot you need To:
1. Clone or Download the repository.
2. Register a new user
3. Create new access tokens
4. To configure the bot (Settings):
    * set active to true in settings/bot_settings.json
    * set TOKEN in settings/bot_settings.json
    * set API_KEY in settings/bot_settings.json
    * set API_SECRET in settings/bot_settings.json
5. Start trading (Run the bot)


## Download
    * press `Clone or download`
    * unzip the archive on your local computer

## Clone
    $ git clone https://github.com/assassinen/money_printer.git
    $ cd money_printer

## Register a new user
      open http://45.141.102.133:5000/docs#/operations/users_new
      set "Username"
      set "Password"
      press "Set API Request"

## Create new access tokens
      open http://45.141.102.133:5000/docs#/operations/tokens_new
      set "Username"
      set "Password"
      press "Set API Request"
      сopy access_token in TOKEN field to settings/bot_settings.json

## Settings 
* change the settings for the bot `settings/bot_settings.json`:
```yaml
[
  {
    "py/object": "models.settings.Settings",
    "API_KEY": "your_API_KEY_for_bitmex",               # set your API_KEY
    "API_SECRET": "your_API_SECRET_for_bitmex",         # set your API_SECRET
    "TOKEN": "your_grid_bot_server"                     # set your grid-bot-server access_token
    "API_URL": "v2",                                    # API version
    "BASE_URL": "https://api.bitfinex.com/",            # exchange url (e.g https://www.bitfinex.com, https://www.deribit.com)
    "EXCHANGE": "bitfinex",                             # exchange name (e.g bitfinex, deribit)
    "LOOP_INTERVAL": 10,                                # refresh rate in seconds
    "GRID_DEPTH": 100,                                  # maximum number of orders
    "GRID_SIDE": "buy",                                 # direction of orders to close a position
    "ORDER_SIZE": 0.0005,                               # lot size
    "ORDER_SPREAD": 1000,                               # profit value from each order
    "ORDER_STEP": 500,                                  # price difference between orders
    "SYMBOL": "tBTCUSD",                                # trading instrument
    "active": true,                                     # set true to the robot worked
    "strategy": "trades_price"                          # trading strategy name
  }
]
 ```

## Run the bot:
Download [Docker Desktop](https://www.docker.com/products/docker-desktop) for Mac or Windows. [Docker Compose](https://docs.docker.com/compose) will be automatically installed. On Linux, make sure you have the latest version of [Compose](https://docs.docker.com/compose/install/). 

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
money_printer_1  | 2019-09-13 09:00:28,233 - trades_price.7w566cLl - positions: {'average_price': 0.0, 'size': 0.0}
money_printer_1  | 2019-09-13 09:00:28,234 - trades_price.7w566cLl - open_orders: [{'price': 176.8, 'orderQty': 10, 'side': 'buy'}]
money_printer_1  | 2019-09-13 09:00:28,234 - trades_price.7w566cLl - last_trade_price: 179.2
money_printer_1  | 2019-09-13 09:00:28,234 - trades_price.7w566cLl - last_order_price: 179.2
money_printer_1  | 2019-09-13 09:00:28,234 - trades_price.7w566cLl - existing_orders_price: [176.8]
money_printer_1  | 2019-09-13 09:00:28,234 - trades_price.7w566cLl - design_orders_price: []
money_printer_1  | 2019-09-13 09:00:28,234 - trades_price.7w566cLl - grid calculated: {'price': 174.2, 'orderQty': 10, 'side': 'buy'}
money_printer_1  | 2019-09-13 09:00:28,234 - trades_price.7w566cLl - reverse calculated: {}
money_printer_1  | 2019-09-13 09:00:28,450 - orders_manager.7w566cLl - Canceling 1 orders:
money_printer_1  | 2019-09-13 09:00:28,450 - orders_manager.7w566cLl -  buy 10 @ 176.80
money_printer_1  | 2019-09-13 09:00:28,663 - orders_manager.7w566cLl - Creating 1 orders:
money_printer_1  | 2019-09-13 09:00:28,872 - orders_manager.7w566cLl -  buy 10 @ 174.20
````

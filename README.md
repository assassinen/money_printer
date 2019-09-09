# grid_client

## settings
### set "active" to true for run bot in settings/grid_settings.json
### set API_KEY in settings/grid_settings.json
### set API_KEY in settings/exchange_settings.json
### set API_SECRET in settings/exchange_settings.json

## start:
### docker-compose up

## sample output
##### MacBook:grid_client$ docker-compose up
##### Recreating grid_client_grid_client_1 ... done
##### Attaching to grid_client_grid_client_1
##### grid_client_1  | 2019-09-09 15:26:10,701 - strategy.average_price.PECVYbnc5MVY - INFO - existing_orders_price: [10311.0]
##### grid_client_1  | 2019-09-09 15:26:10,701 - strategy.average_price.PECVYbnc5MVY - INFO - design_orders_price: []
##### grid_client_1  | 2019-09-09 15:26:10,701 - strategy.average_price.PECVYbnc5MVY - INFO - grid calculated: {'price': 10326, 'orderQty': 50, 'side': 'Buy'}
##### grid_client_1  | 2019-09-09 15:26:10,702 - strategy.average_price.PECVYbnc5MVY - INFO - reverse calculated: {}
##### grid_client_1  | 2019-09-09 15:26:10,703 - managers.orders_manager.PECVYbnc5MVY - INFO - Canceling 1 orders:

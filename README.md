# Deribit-simple-market-maker
## Using api:
### Authorization:
:
```python
deribit = deribit_interface.Deribit(test=True, 
	client_ID=<client_ID>,
 	client_secret=<client_secret>)
```
### 
Order creation:
`` `python
deribit.make_order(side='sell',
  instrument_name=<instrument_name>,
  amount=<amount>,
  price=<price>,
  post_only=True)
```

More examples in the file market-maker.py 
                        
##
A simple market maker bot for the exchange Deribit (API over WebSocket)

### What the bot does:

1. Places orders from both sides at the best bid / ask prices (does not fill in empty spaces).

2. Waiting for one of the orders to be executed.

3. If one of the orders is executed, then an opposite order is placed with a volume of x2 from the original one (to cover the current position and enter a new one).

3.1. If the price moves away from the order price, the order is updated to the current prices.


The strategy and its parameters can be changed in the market-market-maker.py file.

CAUTION! The bot in its original form consistently brings a loss, without changing the strategy, you will lose money.



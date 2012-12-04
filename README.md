This is a collection of python tools that I have
created to analyze my own stock porfolio and various 
strategies. Use at your own peril.

Data Schema

Stock Database: information relating to stocks themselves

Corporate events:
id symbol ex_date pay_date event_id

event_id can map to any of 
dividend
split
spin-off

dividend: 
(amount, currency)
.2100 Cash.USD

splits
         (needed, get, lose_original, odd lot payout (per share) currency 
2:1 split 1 1 0 15 Cash.USD
1:2 split 2 1 1 13 Cash.CAD
3:2 split 2 1 0 11 Cash.USD

spin-off
5 1 EGL 0 1.54 Cash.USD (needed, get, get_symbol, odd lot payout, currency
1 1 DIV 1 5.30 Cash.USD (this is when a stock gets renamed)
 
other tables:
symbol table:
(symbol) (exchange) (Currency)
HEI  AS   EUR   

Exchange Rates (denominated by USD)

EUR .70
CAD .94
AUD .91
GBP .58

Quotes
actual quote on the day, adjusted quote (inverse of what yahoo/google do where they always match adjusted to today and adjust backwards, this table will adjust forwards. Also need a lock bit (can't be overwritten by incorrect data), and a ratio multiplier.





LastCheckup

Options
This contains option data, like strike and share ratio, delta will be cached here as well




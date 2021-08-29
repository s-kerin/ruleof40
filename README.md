# ruleof40
Wrapper API for the [ruleof40.trade](https://ruleof40.trade/) webapp.  Returns the current and historic list of Rule of 40 stocks and includes scores and relevant dates etc.

Has this project saved you time and/or money?  Consider buying me a coffee with the sponser link on the Github homepage.

## Features
* Get the current Rule of 40 list
* Get historic Rule of 40 data:
    * At any date since 2010-01-01
    * The full Rule of 40 history of any symbol since 2010-01-01

### Install
Use the following pip command:
```
pip install ruleof40
```

## Methods & Classes
```
get_current(cookies=None)
```
Returns the current list of Rule of 40 stocks, including their Rule of 40 score 

```
get_hist_per_date(date:datetime = None, cookies=None)
```
Returns the list of Rule of 40 stocks for the given date

```
get_hist_per_symbol(symbol:str, cookies=None)
```
Returns the Rule of history for the given symbol since 2010-01-01.

### Notes
- Recorded dates **ALL** apply to the **START** of the trading day on that date


## Examples

```
from ruleof40 import ruleof40 as r40
from datetime import datetime, date
import pandas as pd

current = r40.get_current()
print(current)

histdate = r40.get_hist_per_date(datetime(2021, 1, 1, 0, 0))
print(histdate)

histsym = r40.get_hist_per_symbol('ADBE')
print(histsym)
```

# Lunchbot-Python
A Python package for interracting with the @Nero2k Lunchbot API, an API that provides the weekly lunch menu of the Eatery Kista Nod restaurant.

The package fully parses menu attributes into Python objects and is very easy to use.

### Installation

Installation is done via:

`pip install eatery-python`

### Quickstart

For a more detailed guide with more code examples, please refer to the the [official documentation](https://lunchbot-python.albins.website).

There is also an image quickstart example and a compact example of the code below, but that is also available in the official documentation linked above.

```python
"""Websocket/API example
This example shows you the "standard" way of getting the week
menu, which will return a parsed list of Day objects. The Day class is implemented with this API
NOTE: Want to do this with less code?
Check the compact example."""
from eatery_nod import EateryNod #Import the library
menu = EateryNod.Menu() #Create a menu object
menu.initialize() #Initialize (this is only required when using WebSockets)
print("Retrieving menu...") #Print out the status
week_menu = menu.get_menu() #Get the menu
for day in week_menu: #Loop through all the days in the menu
    menu_items_str = "\n".join(day.menu_items) #Format the menu items to a pretty string as they are returned as a list
    print(day.day_name_sv) #Print out the day name (in Swedish)
    print(menu_items_str) #Print out the menu items
    print("Day information:") #Print out a nice divider
    print("Date: " + str(day.day_date)) #Print out the day date
    print("Dessert served?: " + str(day.dessert_served)) #Print out if dessert is served (this will print either True or False)
    print("Pancakes served?: " + str(day.pancakes_served)) #Print out if pancakes are served (this will print either True or False)
    print("Hamburgers served?: " + str(day.burgers_served)) #Print out if hamburgers are served (this will print either True or False)
    print("---------------------------------------------------") #Print out a divider line
last_retrieved = menu.last_retrieved["json"] #Get when the menu was last retrieved
print("Menu retrieved: " + str(last_retrieved)) #Print out when the menu was last retrieved.
```
### Changelog

See the "Releases" tab and the documentation.

### More documentation

All functions, variables, and attributes of the code are documented. You can find it on the official library documentation, which is provided by [GitBook](https://gitbook.com) and hosted on https://lunchbot-python.albins.website.

(no code has been uploaded yet, it's just the initial repository that has been created)

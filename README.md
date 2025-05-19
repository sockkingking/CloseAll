Close all orders EA bot
Desciption: The EA bot is using to close all the open orders at 05:01 am GMT+7 everyday, bot will scan every 500ms to check right time and open orders.
Programming language: mql5
Plan:
- Bot-name: CloseAll
- Strategy:
    - step: Every 500ms, check if current time hour is greater than equal 05:00:58 am in timezone GMT+7
        - if true: move to next step
        - else: re-check again
    - step: Check if there are open orders
        - if true: close all the orders
        - else: do nothing
    
Implementation Plan:
1. EA Initialization
    + Set up a timer to trigger every 500ms.
2. OnTimer() Logic
    + Check if the current time is at or after 05:00:58 AM.
    + If so, check for open orders.
    + If there are open orders, close them all.
3. Order Closing Logic
    + Loop through all open orders and close each one.
4. Cleanup
    + Properly handle deinitialization (stop timer).

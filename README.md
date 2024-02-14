# Wiki Trade EA

## Introduction
Welcome to the Wiki Trade EA! This is an automated trading software designed for the Forex market. It is developed by the Forex Robot Easy Team and you can find more information about us on our website [forexroboteasy.com](https://forexroboteasy.com).

Please note that ForexRobotEasy is not the official developer of this product. We are only providing you with a sample code that can work as described in this product. To find the official developer of this product, we recommend using MQL5.

## Code Overview
The code provided here is a simplified version to demonstrate the basic functionality of the Wiki Trade EA. Let's go through the code step by step:

### Define the Symbol and Timeframe
```csharp
string symbol = 'EURUSD';
ENUM_TIMEFRAMES timeframe = PERIOD_M15;
```
Here, we define the symbol as 'EURUSD' and the timeframe as 15 minutes.

### Define the Entry and Exit Conditions
```csharp
double takeProfit = 50; // take profit in pips
double stopLoss = 20; // stop loss in pips
```
We define the take profit and stop loss levels in pips.

### Define the Order Type
```csharp
ENUM_ORDER_TYPE orderType = ORDER_TYPE_BUY; // buy order
```
We define the order type as a buy order.

### Calculate the Entry Price
```csharp
double entryPrice = SymbolInfoDouble(symbol, SYMBOL_ASK);
```
We calculate the entry price using the current ask price of the symbol.

### Calculate the Take Profit and Stop Loss Levels
```csharp
double tpPrice = entryPrice + takeProfit * SymbolInfoDouble(symbol, SYMBOL_POINT);
double slPrice = entryPrice - stopLoss * SymbolInfoDouble(symbol, SYMBOL_POINT);
```
We calculate the take profit and stop loss levels based on the entry price and the number of pips specified.

### Open the Trade
```csharp
int ticket = OrderSend(
    symbol,           // symbol
    orderType,        // order type
    0.1,              // lot size
    entryPrice,       // entry price
    0,                // slippage
    slPrice,          // stop loss
    tpPrice,          // take profit
    'Wiki Trade EA',  // comment
    0,                // magic number
    0,                // expiration
    clrNONE           // arrow color
);
```
We open the trade using the OrderSend() function with the specified parameters.

### Check if the Trade was Opened Successfully
```csharp
if(ticket > 0){
    // Trade opened successfully
    Print('Trade opened successfully. Ticket: ', ticket);
}
else{
    // Failed to open trade
    Print('Failed to open trade. Error code: ', GetLastError());
}
```
We check if the trade was opened successfully by checking the value of the ticket. If the ticket is greater than 0, it means the trade was opened successfully. Otherwise, an error occurred.

### Close the Trade
```csharp
bool closeTrade = OrderClose(ticket, OrderLots(), Bid, 5, clrNONE);
if(closeTrade){
    // Trade closed successfully
    Print('Trade closed successfully');
}
else{
    // Failed to close trade
    Print('Failed to close trade. Error code: ', GetLastError());
}
```
We close the trade using the OrderClose() function with the specified parameters. We check if the trade was closed successfully and print the appropriate message.

## Product Description
The Wiki Trade EA is an automated trading software designed for the Forex market. It provides traders with the ability to enter and exit trades based on predefined conditions. With this software, traders can define their desired take profit and stop loss levels to manage their risk effectively.

This software is developed by the Forex Robot Easy Team, a reputable team in the Forex industry. We have a proven track record of creating high-performance Forex software. For detailed reviews and trading results of this product, please visit our website [here](https://forexroboteasy.com/forex-robot-review/wiki-trade-ea-review-high-performance-forex-software/).

Please note that ForexRobotEasy is not the official developer of this product. We are only showing you a sample code that can work as described in this product. To find the official developer of this product, we recommend using MQL5.

## Conclusion
Thank you for choosing the Wiki Trade EA! We believe that this automated trading software will help you in your Forex trading journey. Should you have any questions or concerns, please feel free to reach out to our team through our website [forexroboteasy.com](https://forexroboteasy.com). Happy trading!

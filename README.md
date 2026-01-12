# The Turtle Strategy

This indicator identifies breakouts and then looks for a suitable candle to enter the trade. It is based on the classic [Turtle Trading](https://www.investopedia.com/articles/trading/08/turtle-trading.asp) rules and focuses on trend breakouts and risk management.

All code is created and maintained by [Timo Anttila](https://github.com/timoanttila). If you have suggestions or ideas, feel free to get in touch. The Turtle Strategy script is built for [TradingView](https://www.tradingview.com/), a popular platform for technical analysis and trading.

Day trading involves significant risk, and most traders lose money. Only trade with money you can afford to lose, and always test your strategy in a simulator first. This content is for educational and informational purposes only and is not investment advice. Always do your own research and backtest before making any trading decisions.

No strategy is perfect, and all traders experience losses.

---

The [Turtle Strategy indicator](./Turtle.pine) is based on the famous Turtle Trading experiment led by Richard Dennis in 1983. Dennis trained a group of beginners using a simple breakout strategy, and together they earned over $175 million. The experiment showed that trading skills can be learned through clear rules and discipline.

This indicator applies those same core ideas to today’s markets. It looks for strong trend breakouts using recent highs and lows, allows multiple entries as the trend continues, and manages risk with initial stop-loss levels based on the [Average True Range (ATR)](https://www.investopedia.com/terms/a/atr.asp).

## How does it work

The indicator watches price for breakouts above recent highs or below recent lows. When price breaks one of these levels, it generates an entry signal. It uses a 20-bar lookback period for entries and a 10-bar lookback period for exits. These settings can be adjusted by the user.

Once a trend is established, the indicator can generate additional entry signals as price moves further in your favor by a set ATR distance. Exit signals occur when price reaches the ATR-based stop or when price breaks against the trend using the exit lookback period. Each new entry recalculates the ATR-based stop-loss to reflect the latest position.

## ATR-based risk management

ATR determines both your stop loss distance and the spacing between pyramid entries. You control the ATR calculation length (default 20 periods), the exit stop multiplier (default 2.0), and the entry spacing multiplier (default 1.0). Larger multipliers give trades more room but increase risk per position.

You decide how many entries to take per trend using the maximum entries setting (default is `2`). Setting this to `1` means you only take initial breakouts, while higher values let you add to winners as they develop. The `Only Longs` option restricts the indicator to bullish trades only if you prefer directional trading. This option saves you from many unnecessary losses with assets like `XAUUSD` and `NAS100`.

You should not risk more than 2% of your account balance per trade idea.

## Clear visual signals

Entry signals are shown as triangles for the first trend entry and crosses for additional entries. Exit signals are marked with an `X`. All markers are designed to be clear and easy to see without cluttering the chart.

### Alerts

The indicator includes alert conditions that can notify you when trading opportunities appear.

- **New Trend**: Triggers when the first entry of a new trend occurs.
- **All Entries**: Triggers on every entry signal, including both initial entries and additional pyramid entries.

## Daily reference levels

On intraday charts (4H and lower), the indicator shows yesterday’s high (PDH), yesterday’s low (PDL), and today’s open price. These levels update automatically each day and often act as important support and resistance during the current trading session.
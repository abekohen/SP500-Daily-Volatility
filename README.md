# SP500-Daily-Volatility

Using Quandl and SP500 rolling lead month futures as a proxy for SP500 index, use data science to determine whether circuit breakers work as intended or exacerbate the prevailing trend.

The Securities and Exchange Commission (SEC) is charged with maintaining orderly markets. The CFTC has a similar role in commodities markets which include futures on the SP500 index. 

In the last thirty years trading has evolved from computers assisting human traders to traders monitoring algorithmic trading strategies. Since computers can process multiple tasks very rapidly, and show no emotion, and can trade at a granularity of micro-seconds, volatility can explode at a rapid rate, from human error in coding algorithms, error in input data, and in general the creation of positive feedback loops.

After the Crash of 1987, President Reagan appointed the Brady Commission to report on the causes of the crash and to make recommendations on how to mitigate future crashes. 

One outcome was to halt program trading (then defined as the near-simultaneous trading of 15 or more stocks with a value of over $1 million) when the Dow Jones Industrial Index moves up or down 50 points from the previous day's close. As the markets moved up, 50 points was deemed to narrow and it was replaced by larger bands. Over time other circuit breakers were introduced, and one of the latest manifestations is the Limit Up / Limit Down (LULD) rule in individual securities which halts trading for 5 minutes. But as anyone who has ever driven a car when the light turns yellow, we know that certain drivers will race through the light and finishing the traversal when the light has already turned red. Traders often increase trading activity as the circuit breaker is impending, which exacerbates the prevailing trend.

The choice of which securities or commodities to use is important. The SP500 futures public data goes back to 1982. The SPY ETF was born on 1/22/1993. The ES (e-mini) future was created in the mid 90s. The rolling ES would make a better proxy for the index due to its higher volume traded than the SP future, which also had a change in notional value by changing its multiplier from $500 to $250. SPY has the advantage of being continuous (no rolling contract needed), but it has a few shortcomings. SPY has a much lower notional value, hence at moments of extreme volatility the futures contract lead and the SPY follows. Furthermore, with the SPY we would be missing data for the all important Crash of 1987 as well as the smaller crash of 1989.



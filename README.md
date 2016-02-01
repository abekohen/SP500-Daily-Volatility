# SP500-Daily-Volatility and Circuit Breakers

Using Quandl and SP500 rolling lead month futures as a proxy for SP500 index, use data science to determine whether Securities and Exchange Commission (SEC) and/or FINRA circuit breakers work as intended or exacerbate the prevailing trend.

WHY IS THIS IMPORTANT?

The SEC is charged with maintaining orderly markets. The CFTC has a similar role in commodities markets which include futures on the SP500 index. 

In the last thirty years trading has evolved from computers assisting human traders to traders monitoring algorithmic trading strategies. Since computers can process multiple tasks very rapidly, show no emotion, and can trade at a granularity of micro-seconds, volatility can explode at a rapid rate, from human error in coding algorithms, error in input data, and from the creation of positive feedback loops.

After the Crash of 1987, President Reagan appointed the Brady Commission to report on the causes of the crash (see the graph in this github collection, and see its unusually large magnitude) and to make recommendations on how to mitigate future crashes. 

One outcome was to halt program trading (then defined as the near-simultaneous trading of 15 or more stocks with a value of over $1 million) when the Dow Jones Industrial Index moves up or down 50 points from the previous day's close. Why program trading? Because it was a convenient scapegoat and required no data science to verify. The real causes were Portfolio Insurance and computers not equipped to handle the volume of transactions. 

Portfolio Insurance turned out to be a massive positive feedback loop, which meant increased selling as the market crashed. It was the brainchild of Leland-Obrien-Rubinstein, a firm set up by three Berkeley Business School professors. (Full disclosure: Both Hayne Leland and Mark Rubinstein were my professors at Cal.)

As the markets eventually moved up, 50 points in the Dow was deemed to narrow and it was replaced by larger bands. Over time other circuit breakers were introduced, and one of the latest manifestations is the Limit Up / Limit Down (LULD) rule in individual securities which halts trading for 5 minutes. But as anyone who has ever driven a car when the light turns yellow knows that certain drivers will race through the light and finish the traversal when the light has already turned red. Traders often increase trading activity as the circuit breaker is impending, which exacerbates the prevailing trend.

The choice of which securities or commodities to use is important. Several instruments are available. Each has pros and cons.

The SP500 (SP) futures public data goes back to 1982. So it has the longest track record, but it is no longer the dominant trading instrument that it was in the 1980s. The ES (e-mini) future was created in the mid 90s. The rolling ES would make a better proxy for the index due to its higher volume traded than the SP future. Furthermore, SP had a change in notional value by halving its multiplier from $500 to $250, thus requiring 2 contracts traded vs the older 1.

The SPY ETF was born on 1/22/1993.  SPY has the advantage of being continuous (no rolling contract needed), but it has a few shortcomings. SPY has a much lower notional value, hence at moments of extreme volatility the ES futures contract lead and the SPY follows. 

Ideally, we would choose a blend of SP and ES over different periods, but we also have to be cognizant of paradigm shifts which effect the level of volatility. The first is the change in trading of stocks from increments of "one bit" or 12.5 cents, to increments of 1 cent. This dampens volatility, all else being equal. Second, is the explosion of exchanges, from 1987 when all stocks traded on the New York Stock Exchange (NYSE), American Stock Exchange (AMEX), and NASDAQ, to today where there are about 14 exchanges and about 36 Alternative Trading Systems (ATS). Third is the proliferation of ultra fast computers, which can react in microseconds, as well as execerbate volatile situations.

Next steps:

1. Get access to both SP and ES daily data. This would require paying for data from the Chicago Mercantile Exchange. (I know of no public web site from which to scrape it.)
2. Get access to SPY data. This can be scraped from yahoo finance. http://finance.yahoo.com/q/hp?s=SPY+Historical+Prices
3. Scrape exchange documents for when different breakers and breaker levels were put in place and when they were removed. If not available online. It may require some human research.
4. Ideally, try to get minute data or better yet, tick-by-tick data. This might be both expensive to get and would require huge amounts of storage, and would be a true BIG DATA project.
5. Bin data by circuit breaker type and circuit breaker level.
6. Be cognizant of paradigm shift dates, to avoid correlation => causality.

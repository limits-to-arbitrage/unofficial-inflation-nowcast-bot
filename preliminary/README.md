# Preliminary

### Background
While a hedge fund analyst during a bout of inflation, market participants fixated on CPI releases. The idea was that inflation surprises would drive markets (e.g., through changes in expectations of the magnitude and/or timing of Fed tightening), and that the key to trading these releases was having accurate, real-time estimates of CPI inflation. In response, Twitter was inundated with posts by research firms which claimed to have the sought-after *better mousetrap*. The reality tended to be that their inflation models were nowhere near as accurate as Cleveland Fed nowcasts, despite the fervent hype (and paywalls).

### Historical fit
#### Accessing historical nowcasts
At the time of writing, the simplest way to access historical nowcasts is by navigating to the [nowcasts page](https://www.clevelandfed.org/indicators-and-data/inflation-nowcasting) and accessing historical data by `Year-Month` pair.

From the FAQ section of the page:

> **How do I compare the model's historical nowcasts with the actual data?**
> 
> The charting tool on the nowcasting website allows you to plot a sequence of nowcasts for previous months or quarters along with the actual inflation release (for simplicity, we display the first available data release corresponding to the quarter or month being nowcasted). This allows the user to see how close or far the model’s nowcasts were compared with what was actually released by the statistical agency (the BLS or the BEA). Typically, nowcasts early in the month or quarter are less precise than nowcasts made later in the month or quarter, because the early nowcasts are based on less information than later nowcasts.

Where the "charting tool" looks like:

![Cleveland Fed nowcast charting tool for monthly (year-over-year) inflation](https://github.com/limits-to-arbitrage/unofficial-inflation-nowcast-bot/blob/main/assets/nowcast_charting_tool.PNG)

These historical nowcasts were accessed and stored using Selenium and a [Python script](https://github.com/limits-to-arbitrage/unofficial-inflation-nowcast-bot/blob/main/code/preliminary-code/historical_nowcasts_script.py) that loops through each `Year-Month` pair available, downloads and cleans the respective CSV files, and then merges them all into a [consolidated CSV file](https://github.com/limits-to-arbitrage/unofficial-inflation-nowcast-bot/blob/main/data/historical_nowcasts.csv).

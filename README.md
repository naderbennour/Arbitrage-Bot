## Introduction
This bot was created for a hackathon competition where it competed against other team's bots in a simulated trading environment. The stocks and ETFs used in the competition were fictional, with no real fundamentals to base trades on. The market consisted of 4 stocks and 2 ETFs, and the bot aimed to stay market neutral to avoid taking directional positions.

To maximize profits, the bot used a hybrid strategy combining arbitrage and market making. The arbitrage strategy involved identifying opportunities to long ETFs and short stocks (or vice versa) in equal sizes to take advantage of price discrepancies. The market making strategy involved adding more competitive bids and asks to the order book for a particular asset, with the goal of increasing liquidity and capturing the spread.

In addition to these strategies, the bot also implemented a risk management strategy to ensure it was not overexposed to any one asset or market.

Note: Some of the functions in the code that were originally connected to the event's API have been removed and had their names changed to protect the integrity of the competition in case it is repeated in the future.

## Team
* [Tomás Barbosa](https://github.com/barbosa7)
* [Nader Bennour](https://github.com/naderbennour)
* [Vicente Almeida](https://github.com/almeidavc)


## How we built it
Our algorithm is written in Python and is based on the idea of market-making.

We place orders for asks and bids to try and catch the spread, at the same time we are also trading arbitrage. Our arbitrage bot logically hedges all of his trades, but as a market marker trading in a market with low liquidity we had to take up the less loved side of the trade in non-neutral positions. In this scenario, we take advantage of our arbitrage bot, when it finds an opportunity for a trade it will only open one side of the trade in order to help us achieve market neutrality. This is our goal since we believe our edge is in capturing the spread and not in our ability to predict where the market is going.

We believe our algorithm is resilient to different market conditions, and we are confident it will hold up well when markets get very busy.

## Challenges we ran into
It was a challenge for us to evaluate the correct degree of risk and the correct parameters for our script. We wanted to maximise our profits but also have a consistent strategy which was relatively risk averse. Our way of doing this was by regularly changing the size of our total positions and how much of that was unhedged, as this is how our bot analyses risk. 

We ran into a few challenges when building our algorithm. First, we had to make sure that we properly hedged our trades. We also had to account for the 100 lot limit for the combined "hedged" position.

## Accomplishments that we're proud of
We are proud of our algorithm's performance and profitability. We are also proud of our ability to properly hedge our trades and keep our position within the 100 lot limit.

## What we learned
We learned a lot about market-making and risk management. We also learned how to build an algorithm that is resilient to different market conditions.

## What's next for schmup
We plan on continuing to refine our algorithm and making it even more resilient to different market conditions.

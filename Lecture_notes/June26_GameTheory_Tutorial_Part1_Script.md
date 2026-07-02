# IEDA 1250 Tutorial Script

**Tutorial:** Introduction to Game Theory (1/2)  
**Date:** June 26, 2026  
**TA:** Wu Hongfan  
**Recommended length:** 35-40 minutes  

This version is scoped to the first half of game theory. It intentionally leaves mixed strategies, graphical solution, LP formulation, and Cournot competition mostly for the second game theory tutorial.

## Slide 1: Title

Good afternoon everyone. My name is Wu Hongfan. Today we will have the first tutorial on game theory for IEDA 1250.

Since this is Game Theory part one, I will focus on the basic language and the first solution methods: payoff tables, best responses, Nash equilibrium, dominated strategies, and saddle points in zero-sum games.

The later topics, especially mixed strategies, graphical methods, LP formulation, and Cournot competition, can naturally continue in the second game theory tutorial.

## Slide 2: Today's Scope

Here is today's scope.

By the end of this tutorial, you should be able to identify players, strategies, and payoffs; read a payoff matrix correctly; check whether a strategy profile is a Nash equilibrium; remove dominated strategies; and test for a saddle point in a zero-sum game.

I want to emphasize that today's focus is not heavy algebra. The key is learning how to think strategically and how to read the table.

## Slide 3: What Makes a Situation a Game?

A game is a decision situation where each player's payoff depends on the actions of more than one decision maker.

There are four basic ingredients: players, strategies, payoffs, and information or timing. Players are the decision makers. Strategies are the actions they can choose. Payoffs measure how good each outcome is. Information and timing tell us whether players move at the same time and what they know.

In this course, we usually assume rationality, self-interest, and common knowledge. That means players try to maximize their own payoffs, and everyone understands the game structure.

## Slide 4: Why Game Theory?

Compared with linear programming and integer programming, game theory has one important difference.

In LP and IP, we usually model one decision maker who optimizes under constraints. In game theory, several decision makers optimize at the same time. My best decision depends on what you do, and your best decision depends on what I do.

This is why game theory is useful for pricing competition, auctions, political campaigns, traffic routing, and firms choosing locations.

## Slide 5: Prisoner's Dilemma

Let us start with the Prisoner's Dilemma.

There are two prisoners. Each prisoner can either stay silent or betray. The entries in the table are payoffs. The first number is Prisoner A's payoff, and the second number is Prisoner B's payoff.

Here the payoffs are negative because they represent years in prison. Larger is still better. So zero is better than minus two, minus two is better than minus five, and minus five is better than minus ten.

## Slide 6: Best Response Thinking

A best response is the best strategy for one player, given the other player's strategy.

Look at Prisoner A. If B stays silent, A compares minus two from staying silent with zero from betraying. Since zero is larger, A prefers to betray.

If B betrays, A compares minus ten from staying silent with minus five from betraying. Since minus five is larger, A again prefers to betray.

The same logic applies to B. So both players choose betray.

## Slide 7: Nash Equilibrium

This leads to Nash equilibrium.

A Nash equilibrium is a strategy profile where no single player can improve by changing only their own strategy.

In simple words: I am doing my best given what you are doing, and you are doing your best given what I am doing.

In the Prisoner's Dilemma, both betray is the Nash equilibrium. If one prisoner is already betraying, the other prisoner does not want to switch to silent.

## Slide 8: Equilibrium Can Be Inefficient

A very important point is that equilibrium does not mean the outcome is socially best.

In this table, both staying silent gives each prisoner minus two. Both betraying gives each prisoner minus five. So both prisoners would prefer the silent-silent outcome.

But silent-silent is not stable. If B stays silent, A wants to betray. If A stays silent, B wants to betray.

So the Nash equilibrium is stable, but inefficient.

## Slide 9: Beach Kiosk Game

Now let us look at a less mathematical example from the lecture.

Imagine a 200-meter beach. Two vendors choose where to locate their kiosks. Customers go to the nearest vendor. Each vendor wants to attract as many customers as possible.

The question is: where will the vendors locate if both think strategically?

## Slide 10: Beach Kiosk Equilibrium Intuition

If one vendor locates at 50 meters and the other at 150 meters, they split the beach evenly.

But this is not stable. Each vendor wants to move a little closer to the center to capture more customers. This pressure continues until both vendors locate at the center, or immediately next to each other at the center.

The lesson is similar to the Prisoner's Dilemma: the equilibrium may be stable for the firms, but it may not be best for customers. Customers at the ends of the beach now walk farther.

## Slide 11: How to Read a Payoff Matrix

Before solving games, we must read payoff matrices correctly.

The row player chooses a row. The column player chooses a column. In each cell, the first number is the row player's payoff, and the second number is the column player's payoff.

The most common mistake is comparing the two numbers inside the same cell. Do not do that. These payoffs belong to different players.

When we find the row player's best response, we compare the row player's payoffs across rows while holding the column fixed. When we find the column player's best response, we compare the column player's payoffs across columns while holding the row fixed.

## Slide 12: Finding Nash Equilibrium in a 2-by-2 Game

Here is a simple two-by-two game.

To find pure-strategy Nash equilibria, use best responses.

For each column, ask: which row gives Player 1 the highest payoff? Then for each row, ask: which column gives Player 2 the highest payoff?

A cell is a Nash equilibrium if both players are choosing best responses in that cell.

## Slide 13: 2-by-2 Game Solution

If Player 2 chooses L, Player 1 prefers U because 3 is larger than 1.

If Player 2 chooses R, Player 1 prefers D because 2 is larger than 0.

If Player 1 chooses U, Player 2 prefers L because 2 is larger than 0.

If Player 1 chooses D, Player 2 prefers R because 3 is larger than 1.

Therefore, there are two pure-strategy Nash equilibria: U,L and D,R.

## Slide 14: Dominated Strategies

Now we move to dominated strategies.

A strategy is dominated if another strategy is always at least as good and sometimes strictly better, regardless of what the opponent does.

For a row player who maximizes, larger row payoffs are better. So a row is dominated if another row is greater than or equal to it in every column and strictly greater in at least one column.

For a column player in a zero-sum table for Player 1, smaller entries are better, because the column player wants to reduce Player 1's payoff.

## Slide 15: Exercise

Let us practice using this table from the lecture exercises.

Assume the entries are payoffs to Player 1. Player 1 maximizes, and Player 2 minimizes.

Take about one minute to look for dominated rows or columns.

If students need a hint, say: compare Column S4 with Column S2. Since Player 2 minimizes, a column with smaller numbers is better for Player 2. Also compare Row S1 with Row S3.

## Slide 16: Exercise Solution

One possible elimination order is shown here.

First, Column S4 is dominated by Column S2, so remove Column S4.

Then Row S1 is dominated by Row S3, and Row S2 is also dominated by Row S3. After reducing the table, Row S5 is dominated by Row S3. Then Column S3 is dominated by Column S5 in the reduced table.

The main point is not to memorize this exact order. The main point is that every elimination must be justified using the table that remains at that moment.

## Slide 17: Zero-Sum Games

Now let us introduce zero-sum games.

In a zero-sum game, one player's gain is exactly the other player's loss. So we only need one payoff table. The entries are payoffs to Player A.

Player A wants to maximize the payoff. Player B wants to minimize Player A's payoff.

The value of the game is the expected payoff to Player A when both players use optimal strategies.

## Slide 18: Saddle Point Test

For a zero-sum game, the first method to try is the saddle point test.

For each row, calculate the row minimum. This tells us the worst payoff Player A can guarantee by choosing that row. Player A chooses the row with the largest row minimum. Here the largest row minimum is 12.

For each column, calculate the column maximum. This tells us the worst case for Player B if Player B chooses that column. Player B chooses the column with the smallest column maximum. Here the smallest column maximum is also 12.

Since maximin equals minimax, there is a saddle point.

## Slide 19: Saddle Point Result

The saddle point is A1, B3, and the value of the game is 12.

This cell is the minimum in Row A1 and the maximum in Column B3.

If A chooses A1, B cannot reduce A below 12. If B chooses B3, A cannot increase above 12. So neither side wants to change unilaterally.

This is a pure-strategy solution.

## Slide 20: When There Is No Saddle Point

Sometimes maximin and minimax are not equal.

In this example, maximin is minus 2, while minimax is 2. Since they are different, there is no pure-strategy saddle point.

When this happens, pure strategies are not enough. We then need mixed strategies, where players choose strategies with probabilities.

That is the natural next topic for the second game theory tutorial.

## Slide 21: Today's Checklist

Here is the checklist for today's tutorial.

First, identify players, strategies, and payoffs. Second, read the payoff matrix correctly. Third, use best responses to check Nash equilibrium. Fourth, remove dominated strategies when possible. Fifth, for zero-sum games, try the saddle point test before thinking about mixed strategies.

This checklist is a good starting point for homework problems.

## Slide 22: Mini Quiz

Let us do a quick check.

Question one: Can a Nash equilibrium be inefficient? Yes. Prisoner's Dilemma and the beach kiosk example both show this.

Question two: In a zero-sum game, what does Player B want to do to Player A's payoff? Player B wants to minimize it.

Question three: What equality must hold for a saddle point? The largest row minimum must equal the smallest column maximum.

Question four: Why should we not compare the two payoffs inside the same cell? Because they belong to different players. We compare one player's own payoffs across that player's available choices.

## Slide 23: Summary

Today we introduced the basic language and the first solution methods in game theory.

Game theory studies strategic decision making. Nash equilibrium means no player wants to deviate alone. An equilibrium can be stable but inefficient. Dominated strategies help us simplify payoff tables. In zero-sum games, a saddle point gives a pure-strategy solution.

If no saddle point exists, then mixed strategies are needed. That will be the natural continuation for Game Theory part two.

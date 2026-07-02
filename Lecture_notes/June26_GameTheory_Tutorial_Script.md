# IEDA 1250 Tutorial Script

**Tutorial:** Introduction to Game Theory (1/2)  
**Date:** June 26, 2026  
**TA:** Wu Hongfan  
**Suggested length:** about 60 minutes  

This script is written to be spoken aloud. You can shorten the Cournot part if the class discussion takes longer than expected.

## Timing Plan

- Slides 1-7: basic concepts and Prisoner's Dilemma, about 10 minutes.
- Slides 8-11: dominated strategies, about 10 minutes.
- Slides 12-17: zero-sum games and saddle points, about 10 minutes.
- Slides 18-26: mixed strategies and graphical method, about 18 minutes.
- Slides 27-31: LP formulation and Cournot model, about 8 minutes.
- Slides 32-35: method selection, common mistakes, mini quiz, summary, about 4 minutes.

## Slide 1: Title

Good afternoon everyone. My name is Wu Hongfan. Today we will have the first tutorial on game theory for IEDA 1250.

In the lecture, Professor Yang introduced the motivation for game theory, Nash equilibrium, zero-sum games, mixed strategies, and the Cournot competition model. In this tutorial, I will not repeat every lecture slide. Instead, we will focus on how to solve typical questions: how to read a payoff table, how to eliminate dominated strategies, how to test for a saddle point, and how to use the graphical method for mixed strategies.

The goal is practical. After this tutorial, when you see a game theory problem in homework or an exam, you should know which method to try first.

## Slide 2: Plan for Today

Here is the plan for today.

First, we translate a story into the language of game theory: players, strategies, and payoffs. Second, we find Nash equilibria using best responses and dominated strategies. Third, we focus on zero-sum games, because many homework-style questions are zero-sum payoff tables. We will use the saddle point test and mixed strategies. Finally, we connect the methods to the problem set style.

Please notice the target at the bottom. I do not expect you to memorize many definitions. The more important skill is to look at a payoff table and decide: should I use dominance, saddle point, graphical method, or linear programming?

## Slide 3: What Makes a Situation a Game?

A game is a decision situation where one person's payoff depends not only on their own action, but also on what other decision makers do.

There are four basic ingredients. First, players: these are the decision makers. Second, strategies: these are the possible actions or plans. Third, payoffs: these measure how good each outcome is for each player. Fourth, information and timing: for example, do players move at the same time, or does one player observe the other first?

In this course, we usually assume rationality, self-interest, and common knowledge. Rationality means players try to choose the best option according to their payoffs. Self-interest means each player maximizes their own payoff, not the opponent's payoff. Common knowledge means everyone understands the game structure, and everyone knows that everyone understands it.

This is a simplified model of real behavior, but it is useful because it gives us a clean way to predict stable outcomes.

## Slide 4: Example: Prisoner's Dilemma

Let us start with the Prisoner's Dilemma, because it shows the main idea of game theory very clearly.

There are two prisoners. Each prisoner has two strategies: remain silent or betray. The numbers in each cell are payoffs. Here the payoffs are negative because they represent years in prison. A payoff of zero is better than minus two, and minus two is better than minus five.

The first number is Prisoner A's payoff, and the second number is Prisoner B's payoff. For example, if A stays silent and B betrays, then A gets minus ten and B gets zero. That means A receives ten years and B goes free.

The interesting point is that both prisoners would prefer the outcome where both stay silent compared with both betray. But the question in game theory is not only which outcome is socially better. The question is: which outcome is stable when each person acts individually?

## Slide 5: Best Response Thinking

To answer that, we use best response thinking.

A best response is the best strategy for one player, given what the other player does. We hold the other player's action fixed and compare the player's own payoffs.

Look at Prisoner A first. If B stays silent, A compares minus two from staying silent with zero from betraying. Zero is larger, so A prefers to betray. If B betrays, A compares minus ten from staying silent with minus five from betraying. Minus five is larger, so A again prefers to betray.

Therefore, betray is A's best response no matter what B does. Because the game is symmetric, the same logic applies to B. B also prefers to betray no matter what A does.

This is why both prisoners betray, even though both staying silent would make both of them better off.

## Slide 6: Nash Equilibrium

This leads to the definition of Nash equilibrium.

A Nash equilibrium is a strategy profile where no single player can improve by changing only their own strategy. Another way to say it is: I am doing my best given what you are doing, and you are doing your best given what I am doing.

The word "single" is important. In a Nash equilibrium, we do not ask whether everyone can move together and become better off. We only ask whether one player can improve by deviating alone.

In the Prisoner's Dilemma, both betray is the Nash equilibrium. If A betrays, B does not want to switch from betray to silent, because B would go from minus five to minus ten. If B betrays, A does not want to switch either. So the outcome is stable.

But it is not efficient. Both prisoners would be better off at silent, silent. This is a key lesson: equilibrium does not always mean socially optimal.

## Slide 7: How to Read a Payoff Matrix

Before solving more examples, let us make sure we read payoff matrices correctly.

The row player chooses a row. The column player chooses a column. In each cell, the first number belongs to the row player, and the second number belongs to the column player.

For example, if the row player chooses U and the column player chooses L, the payoff is three for the row player and two for the column player.

The common mistake is to compare the first number and the second number inside the same cell. Do not do that. These numbers belong to different people and may not be directly comparable. When we find a best response for the row player, we compare row player's payoffs across rows, holding the column fixed. When we find a best response for the column player, we compare column player's payoffs across columns, holding the row fixed.

## Slide 8: Dominated Strategies

Now we move to dominated strategies.

A strategy is dominated if another strategy is always at least as good and sometimes strictly better, no matter what the opponent does. If a rational player has a dominated strategy, they should not use it.

For a row player who maximizes, we compare rows. A row is dominated if another row has entries greater than or equal to it in every remaining column, and strictly greater in at least one column.

For a column player in a zero-sum table, the entries are payoffs to Player 1. Player 2 wants to minimize Player 1's payoff. So a column is dominated if another column has entries less than or equal to it in every remaining row, and strictly lower in at least one row.

This is a very useful first step because it can make a large payoff table much smaller.

## Slide 9: Exercise 1

Let us try this table. Assume all entries are payoffs to Player 1. Player 1 wants larger numbers, and Player 2 wants smaller numbers.

Take one minute to look for dominated rows or columns. For rows, look for another row that is always greater than or equal. For columns, look for another column that is always less than or equal.

You do not need to solve the whole game yet. The task is only to simplify the table.

Pause here and give students time. If the room is quiet, guide them by saying: start with Row S1 and compare it with Row S3. Then compare Column S4 with Column S2.

## Slide 10: Exercise 1 Solution

One possible elimination order is shown here.

First, Column S4 is dominated by Column S2. Check this column by column: in every row, Column S2 gives Player 1 a payoff no larger than Column S4. Since Player 2 wants to minimize Player 1's payoff, Player 2 would never choose Column S4.

Second, Row S1 is dominated by Row S3. Row S3 is better for Player 1 in every remaining column. Third, Row S2 is also dominated by Row S3. After those removals, Row S5 becomes dominated by Row S3 in the reduced table. Finally, Column S3 is dominated by Column S5 in the reduced table.

The exact order can differ. The important point is that every step must be justified using the table that remains at that moment. Do not use a removed row or column to justify a later step.

## Slide 11: Zero-Sum Games

Now let us focus on zero-sum games.

In a zero-sum game, one player's gain is exactly the other player's loss. Because of that, we only need one payoff table. The entries are payoffs to Player A. Player A wants to maximize these numbers, while Player B wants to minimize them.

The value of the game is the expected payoff to Player A when both players use optimal strategies. If the value is positive, the game is favorable to Player A. If it is negative, it is favorable to Player B. If it is zero, we often call it a fair game.

## Slide 12: Pure Strategy: Saddle Point Test

Here is a zero-sum payoff table from the problem set. The entries are payoffs to Player A.

The first thing to check is whether there is a pure strategy saddle point. For each row, compute the row minimum. This tells us the worst payoff Player A can guarantee by choosing that row. Player A wants the largest of these row minima. Here the row minima are 12, 8, 2, and minus 5. The largest is 12, from Row A1.

For each column, compute the column maximum. This tells us the worst case for Player B if Player B chooses that column, because Player A will try to maximize. Player B wants the smallest of these column maxima. The column maxima are 40, 15, 12, and 35. The smallest is 12, from Column B3.

Because maximin equals minimax, both equal 12, we have a saddle point.

## Slide 13: Pure Strategy Result

The saddle point is A1, B3, and the value of the game is 12.

Why is this stable? If Player A chooses A1, Player B's best response is B3, because it gives Player A the smallest payoff in that row. If Player B chooses B3, Player A's best response is A1, because it gives Player A the largest payoff in that column.

So neither player wants to move away unilaterally. This is a pure strategy equilibrium for the zero-sum game.

In an exam or homework, this is the fastest type of question. Always try the saddle point test before doing mixed strategies.

## Slide 14: When There Is No Saddle Point

Now consider this table. The row minima are minus 2, minus 3, and minus 4, so maximin is minus 2. The column maxima are 5, 4, and 2, so minimax is 2.

They are not equal. That means there is no pure strategy saddle point.

Intuitively, if Player A announces a pure row, Player B can exploit it. If Player B announces a pure column, Player A can exploit it. So a fixed deterministic choice is not stable.

This motivates mixed strategies: instead of always choosing one row or one column, players randomize.

## Slide 15: Mixed Strategies

A mixed strategy is a probability distribution over pure strategies.

For example, if Player A has two rows, A can choose A1 with probability p and A2 with probability one minus p. If Player B has two columns, B can choose B1 with probability q and B2 with probability one minus q.

Once players use probabilities, payoffs become expected payoffs. The central idea is indifference. At equilibrium, if a player randomizes among several strategies, those strategies must give the same expected payoff. Otherwise, the player would put all probability on the better one.

This idea is what makes the algebra manageable.

## Slide 16: Graphical Method Setup

Now we use the graphical method on a homework-style example.

Player A has two rows, A1 and A2. Player B has four columns. Let p be the probability that A chooses A1. Then A chooses A2 with probability one minus p.

For each possible pure column of Player B, we write Player A's expected payoff. If B chooses B1, the expected payoff is 2p plus 4 times one minus p, which simplifies to 4 minus 2p. If B chooses B2, it is 3 minus p. If B chooses B3, it is 2 plus p. If B chooses B4, it is 6 minus 8p.

These four expressions are four lines in p.

## Slide 17: Graphical Method

The graph plots the four expected payoff lines.

Remember the logic. Player A chooses p first, but Player B is trying to minimize A's payoff. So for any fixed p, the payoff A can actually guarantee is the minimum of the four lines. That minimum is called the lower envelope.

Player A wants to choose p to make this lower envelope as high as possible. On the graph, the best point is where the lower envelope reaches its highest point. In this example, the optimal p is 4 over 9, and the value is 22 over 9.

Therefore, Player A's optimal mixed strategy is A1 with probability 4 over 9 and A2 with probability 5 over 9.

## Slide 18: Why the Intersection Matters

Let us explain why this intersection matters.

At the optimal p, two constraints are binding. Here the binding lines are B3 and B4. If only one line were binding, usually A could move p a little bit to improve the minimum payoff. At the optimal point, the limiting columns balance each other.

We set the two binding expected payoffs equal:

2 plus p equals 6 minus 8p.

Solving gives p equals 4 over 9. Substituting back gives V equals 2 plus 4 over 9, which is 22 over 9.

This is the algebraic version of reading the graph.

## Slide 19: Check the Binding Lines

It is important to check the answer against all lines, not only the two lines we used.

At p equals 4 over 9, the expected payoffs are 28 over 9 for B1, 23 over 9 for B2, 22 over 9 for B3, and 22 over 9 for B4.

The smallest payoff is 22 over 9, and it occurs for B3 and B4. That confirms B3 and B4 are the binding columns.

This also tells us something about Player B's mixed strategy. Player B should put positive probability only on columns that bind. So B1 and B2 get probability zero, while B3 and B4 may get positive probability.

## Slide 20: Find Player B's Mixed Strategy

Now we find Player B's probabilities.

Let q3 be the probability of B3 and q4 be the probability of B4. Since B only uses B3 and B4, q3 plus q4 equals 1.

To make Player A willing to mix between A1 and A2, A's expected payoff from A1 must equal A's expected payoff from A2.

If A chooses A1, the expected payoff against B's mix is 3q3 minus 2q4. If A chooses A2, it is 2q3 plus 6q4. Set them equal:

3q3 minus 2q4 equals 2q3 plus 6q4.

This gives q3 equals 8q4. Together with q3 plus q4 equals 1, we get q3 equals 8 over 9 and q4 equals 1 over 9.

So B's optimal strategy is zero, zero, 8 over 9, 1 over 9.

## Slide 21: Graphical Method Checklist

This slide is a checklist you can use in homework.

If Player A has two rows, let p be the probability of the first row. Write one expected payoff line for each column of Player B. Then identify the lower envelope, because Player B will choose the worst column for A. Choose p to maximize that lower envelope.

After that, the binding columns are the columns that can get positive probability for Player B. Use indifference equations to solve Player B's probabilities.

The same idea works in reverse when Player B has two columns. Then we let q be the probability of one column, write one payoff line for each row, and Player B minimizes the upper envelope.

## Slide 22: Practice 2

Now let us try the reverse case. Here Player B has two columns, B1 and B2, while Player A has six rows.

Let q be the probability that B chooses B1. Then B chooses B2 with probability one minus q.

For each row of Player A, we can compute A's expected payoff as a function of q. Since Player A will choose the best row, Player B wants to minimize the maximum of these row payoff lines. In other words, we will look at the upper envelope.

Before showing the result, ask students: which rows look likely to matter? Very low rows will not be chosen by Player A, so we expect only the upper lines to determine the solution.

## Slide 23: Practice 2 Payoff Lines

Here are the payoff lines.

For example, if A chooses A2, the expected payoff is 3q plus 5 times one minus q, which becomes 5 minus 2q. If A chooses A4, the expected payoff is 4q plus 1 times one minus q, which becomes 1 plus 3q.

Since Player A chooses the best row, Player B faces the upper envelope of these lines. Player B wants to choose q to make the upper envelope as low as possible.

In many problems, you do not need to draw a perfect graph. You can identify candidate intersections, then check which one is actually on the upper envelope.

## Slide 24: Practice 2 Result

The solution is determined by rows A2 and A4.

Set 5 minus 2q equal to 1 plus 3q. This gives q equals 4 over 5. Substituting back, the value is 5 minus 2 times 4 over 5, which equals 17 over 5, or 3.4.

Now find Player A's probabilities. Since A mixes between A2 and A4, let A choose A2 with probability p and A4 with probability one minus p.

To keep Player B indifferent between B1 and B2, we equalize A's expected payoff under B1 and B2. Under B1, the payoff is 3p plus 4 times one minus p, which is 4 minus p. Under B2, it is 5p plus 1 times one minus p, which is 1 plus 4p.

Set them equal: 4 minus p equals 1 plus 4p. Then p equals 3 over 5.

So A's optimal strategy is to choose A2 with probability 3 over 5 and A4 with probability 2 over 5. B's optimal strategy is B1 with probability 4 over 5 and B2 with probability 1 over 5.

## Slide 25: LP Formulation

The graphical method is convenient when one player has exactly two strategies. For larger zero-sum games, we can use linear programming.

For Player A, the decision variables are the probabilities x_i and the game value V. We maximize V. For each column j of Player B, we require the expected payoff against that column to be at least V. That is the constraint sum over i of a_ij x_i greater than or equal to V.

We also require the probabilities to sum to one and be nonnegative.

The interpretation is simple. Player A wants to choose a mixed strategy that guarantees at least V no matter which column Player B chooses. Maximizing V gives the best guaranteed payoff.

You do not need to memorize advanced LP transformations here. Focus on the logic: constraints represent guarantees against each opponent strategy.

## Slide 26: From Zero-Sum to Business Competition

Not all games are zero-sum.

In a business setting, two firms may both make positive profits. One firm's gain does not have to be exactly the other firm's loss. However, the Nash equilibrium idea still applies.

Each firm asks: given the other firm's decision, what is my best response? Equilibrium occurs where the best responses are consistent with each other.

The Cournot model is a classic example. Firms choose quantities simultaneously, and the market price depends on the total quantity produced.

## Slide 27: Cournot Model

In the Cournot model, firm 1 chooses q1 and firm 2 chooses q2. The market price is p equals a minus b times q1 plus q2.

If both firms have unit cost c, firm 1's profit is price minus cost, times quantity. So firm 1's profit is a minus b times q1 plus q2 minus c, all multiplied by q1.

To find firm 1's best response, treat q2 as fixed and maximize with respect to q1. Taking the derivative and setting it equal to zero gives q1 star equals a minus c minus bq2, divided by 2b.

Similarly, firm 2 has a best response function depending on q1.

## Slide 28: Cournot Equilibrium

The Nash equilibrium is where the two best response functions intersect.

In the symmetric cost case, both firms have the same cost, so the equilibrium quantities are equal. Solving the two equations gives q1 star equals q2 star equals a minus c divided by 3b.

The interpretation is important. Each firm knows that producing more lowers the market price. Therefore, each firm holds back relative to the level that would occur under perfect competition.

This is different from zero-sum games, but the best response logic is the same.

## Slide 29: Cournot Practice

Now consider the practice problem from the lecture.

The price is p equals 14 minus 2Q, where Q is q1 plus q2. Firm 1 has unit cost 2, and Firm 2 has unit cost 4.

Firm 1's profit is price minus cost, times q1. That is 14 minus 2q1 minus 2q2 minus 2, multiplied by q1. Simplifying, we get 12 minus 2q1 minus 2q2, multiplied by q1.

Firm 2's profit is 14 minus 2q1 minus 2q2 minus 4, multiplied by q2. Simplifying, we get 10 minus 2q1 minus 2q2, multiplied by q2.

## Slide 30: Cournot Practice Solution

Take the derivative of firm 1's profit with respect to q1:

12 minus 4q1 minus 2q2 equals zero.

So firm 1's best response is q1 equals 3 minus one half q2.

For firm 2, take the derivative with respect to q2:

10 minus 2q1 minus 4q2 equals zero.

So firm 2's best response is q2 equals 2.5 minus one half q1.

Solving these two linear equations gives q1 star equals 7 over 3 and q2 star equals 4 over 3.

The lower-cost firm produces more. That makes economic sense: firm 1 has unit cost 2, while firm 2 has unit cost 4.

## Slide 31: Which Method Should I Use?

This slide is a method selection guide.

If you see obvious bad rows or columns, start with dominated strategy elimination. If the game is zero-sum and a pure solution might exist, do the saddle point test. If there is no saddle point and one player has only two strategies, use the graphical method. If the game is larger, formulate it as an LP. If the decision variables are continuous business decisions, such as quantities in Cournot competition, use best-response functions.

In homework, writing the correct method at the beginning already makes the solution much clearer.

## Slide 32: Common Mistakes

Let me summarize a few common mistakes.

First, do not compare Player A's payoff with Player B's payoff in the same cell. Compare one player's payoffs across their own available actions.

Second, in a zero-sum game, remember Player B minimizes Player A's payoff. That is why we use column maxima for the saddle point test and lower or upper envelopes in the graphical method.

Third, do not declare a Nash equilibrium without checking unilateral deviations. A Nash equilibrium means no one can improve by changing alone.

Fourth, in the graphical method, use the correct envelope. If Player A has two rows and chooses p, A maximizes the lower envelope. If Player B has two columns and chooses q, B minimizes the upper envelope.

Finally, probabilities must sum to one and must be nonnegative.

## Slide 33: Mini Quiz

Let us finish with a short quiz.

Question one: In a Nash equilibrium, can the outcome be inefficient? Yes. The Prisoner's Dilemma is the key example.

Question two: In a zero-sum game, what does Player B want to do to Player A's payoff? Player B wants to minimize Player A's payoff.

Question three: What equality must hold for a saddle point? The maximin value must equal the minimax value.

Question four: If Player A mixes between two rows, what must be true about the expected payoff of those two rows? They must give the same expected payoff under the opponent's equilibrium mixed strategy. Otherwise A would only choose the better row.

## Slide 34: Summary

Today we covered the basic toolkit for introductory game theory.

Game theory studies strategic decisions, where payoffs depend on other decision makers. Nash equilibrium is a no-unilateral-deviation condition. Dominance and saddle point tests are fast first checks. Mixed strategies use probabilities to create stable expected payoffs. For zero-sum games, graphical and LP methods are practical tools.

When you do homework, start by identifying the game type. Is it zero-sum? Does it have a saddle point? Does one player have two strategies? Are there dominated strategies? This diagnosis will usually tell you the solution path.

## Slide 35: References

The tutorial is mainly based on Professor Yang's Lecture 4 slides, the lecture exercises, and the game theory problem set for IEDA 1250 Summer 2026.

I also checked several introductory game theory teaching materials to decide the tutorial structure. The common pattern is to start from Prisoner's Dilemma and Nash equilibrium, then move to payoff matrices, dominance, saddle points, mixed strategies, and examples. That is why today's tutorial follows this problem-solving order.

Thank you. If time remains, we can work through another problem set question together.


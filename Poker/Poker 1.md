# Fundamentals
## Be the house
Make sure that you are the one in any hand that has the edge. Even with a small edge, you will lose sometimes but overall you will come up good.

## Hand rankings
- Royal flush
- Straight flush
- 4 of a kind
- Full house
- Flush
- Straight
- 3 of a kind
- 2 pair
- 1 pair
- High card

## When looking at the community cards, work out what is the best possible hand with those cards?

## Types of straight draws
- Double belly buster
	- When two different cards can give you a straight (e.g. 76 flopping 593)
	- Is well disguised if you hit it, meaning even if a 4 comes it's not obvious that you have the straight. 
- Open ended draw
	- 10J and flopping 9Q2. 
	- The board looks quite "straight"-y, so people can read it better.

## Useful facts
- You cannot make a full house without a pair on the board.
- You cannot make a flush without 3 of a suit on the board.
	- Beware the "idiot" end of a straight, as in 23 flopping 456.
- Straights can be tricky to identify, and few unpaired boards *can't* have a straight.
- You can't have a straight without a 5 or a 10.
- Bottom two pair is a vulnerable hand. If a higher card pairs on the board, you are counterfeited.
- Full house is the best hand if you have the third of the highest pair on the board. (Q3 - QQ882)

## Setup
- One player is the dealer, or the "button".
- The left of the dealer is the small blind.
- Left of them is the big blind.
- Left of them is Under the Gun (UTG) and has to act first.
- Minimum bet is the BB.
- Minimum raise is the amount of the previous bet or raise (you can't just bet $1 when the big blind is $5).
	- Subtly here, the UTG can call the BB, or they can bet twice the big blind or anything above that.
- The blind straddle is only in cash games and it raises the stakes.
	- UTG can straddle by putting in double the BB.
	- The Mississippi straddle is when anyone can do it, but dealer gets priority. And it's 2-5 times the BB

## Stacks
- Each player has a certain number of chips on the table.
- You can only bet your stack.
- If you go all in with someone else who has more than you, there's a side pot. You may only ever win your stack from other people.
- Side pot:
	- Player A has 1500, B has 800, C has 2300.
	- B wins, A second best, C third best.
	- B wins 2400 (their 800 stack plus 800 from each of the others)
	- A gets the "side pot", which is the amount that A bet over B's stack (700) plus that amount from C, so 1400 total.
	- C loses 800 to B, 700 to C, and gets the rest back.
- Sometimes you can refer to your stack as the number of big blinds.

## House cut - the rake
- In casinos, the house will usually take about 5% of the pot whenever you win it.
- If you play $5 - $10, the rake will be every half hour or so, and each player pays a BB.
- Tip the dealer when you win a hand.

# Expected value
- In poker, EV is how much you win times the probability of winning, MINUS how much you lose times the probability of losing.
- Push your positive expectation, and fold you negative expectations.
- Any time you bet, call, raise, your payment in at that point is only that bet/call/raise. Don't consider everything else you've put into the pot because it's already there.

## Pot odds
- Easier way to calculate EV
- Pot odds is the ratio of the amount in the pot to the amount of the bet to call.
	- $70 in the pot
	- $20 to call
	- 70:20 is 3.5:1
	- Odds against hitting are, e.g. 37 non-clubs to 9 clubs, which is 4:1
- Whenever odds against hitting are worse than pot odds, don't call (above example).
- Whenever pot odds are better than odds against, call! 
- Pot odds are calculated on the flop.

## Calculating outs
- Involves calculation and guesswork.
- What does your opponent have?
	- Could your outs give them a better hand?
- E.g. You have Q-10s
- You raise and opponent calls.
- Flop: As Jh 8c
- You check, opponent bets. How many outs do you have?
- Possible Op hands:
	- 2 pair or better
		- You need a K or 9 for a straight, so 8 outs
		- Backdoor flush draw, 10/47 on the turn and 9/46 on the river. We call that 2 outs because you need to draw twice (this is a genera rule for runner runner draws)
		- We could hit but they get a full house, so we subtract 2 outs
		- So we have 8 outs if they have a big hand
	- A in the hand
		- Unlikely to beat a straight or flush, so 10 outs. We need to hit straight with a K or 9 (8 outs) or a backdoor flush (2 outs)
	- J in the hand
		- 3 more outs because we can pair our Q as well as above, so 13 outs
	- Lower pair
		- You can hit the straight or flush, or pair your Q or 10. 16 outs
	- Since we have no idea what he has, let's call it 10 outs to be safe.

### Handy outs table
Rule of thumb: 14 outs makes you even money against a better hand (no bet will scare you off). And you will always be getting better than even pot odds from any bet

| Number of outs | Drawing hand                                           |
| -------------- | ------------------------------------------------------ |
| 4              | 2 pair, needing a full house; or gutshot straight draw |
| 6              | 2 overcards needing to make a pair                     |
| 8              | Open-ended straight draw                               |
| 9              | Flush draw                                             |
| 11             | Flush draw plus a pair needing to improve to trips     |
| 12             | Flush draw plus gutshot straight draw                  |
| 15             | Flush draw plus open-ended straight draw               |

## Express odds vs. implied odds
- When all in, odds are easy to calculate.
- With chips behind, it's more complicated
	- How much will you win if you hit your draw?
	- Some draws are obvious, e.g. flushes.
	- Some are hidden, e.g. straights.
- Implied odds are the pot odds, taking into account future betting (how much money could I bet after the river if I hit my draw, not just what am I betting now).
- 
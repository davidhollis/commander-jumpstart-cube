---
title: "The Math"
draft: false
---

## Cube Composition

I spent a little time fiddling with different deck distributions, but landed on:

  - 6 decks of each single color (30 in total)
  - 2 decks of each color pair (20 in total)

for a total of 50 decks.

The important thing to me was ending up in a situation where if you were dealt any two decks at random, you'd end up in 2 or 3 colors most of the time[^1]. Enter the hypergeometric distribution[^2]! With the configuration above, I determined the probability of every distribution of single- and dual-colored decks:

| Deck Distribution | Probability            |
|-------------------|------------------------|
| 2 single          | 0.3551020408 (≈ 35.5%) |
| 1 single, 1 dual  | 0.4897959184 (≈ 49.0%) |
| 2 dual            | 0.1551020408 (≈ 15.5%) |

So if you draw 2 random decks, you'll get a 1-color deck and a 2-color deck slightly less than half the time, and of the rest of the possible draws, you'll get two 1-color decks more than twice as often as two 2-color decks. 

This is encouraging, but it's only part of the story. I want to get from here to the probability distribution of the number of colors in the combined deck. To get there, I first needed to calculate the probability of each color count given the deck distribution. I'm sure there's a clean formula for this somewhere, but there were few enough cases that I just wrote out explicit formulas for each case in terms of the deck counts and plugged them into the spreadsheet. The results:

| Deck Distribution | Pr(1 color\|...) | Pr(2 colors\|...) | Pr(3 colors\|...) | Pr(4 colors\|...) |
|-------------------|------------------|-------------------|-------------------|-------------------|
| 2 single          | 0.1724137931     | 0.8275862069      | 0[^3]             | 0[^3]             |
| 1 single, 1 dual  | 0[^3]            | 0.4000000000      | 0.6000000000      | 0[^3]             |
| 2 dual            | 0[^3]            | 0.05263157895     | 0.6315789474      | 0.3157894737      |

Next up is brushing the rust off some elementary probability and determining that for any given color count:

```
Pr(n colors) =   Pr(n colors && 2 single)
               + Pr(n colors && 1 single, 1 dual)
               + Pr(n colors && 2 duals)

             =   Pr(n colors|2 single) * Pr(2 single)
               + Pr(n colors|1 single, 1 dual) * Pr(1 single, 1 dual)
               + Pr(n colors|2 duals) * Pr(2 duals)
```

And fortunately we've got all those values in the tables above. Asking the spreadsheet nicely to do all the arithmetic for us yields:

| # colors | Probability            |
|----------|------------------------|
| 1        | 0.06122448980 (≈ 6.1%) |
| 2        | 0.4979591837 (≈ 49.8%) |
| 3        | 0.3918367347 (≈ 39.2%) |
| 4        | 0.04897959184 (≈ 4.9%) |

Looks good! So almost half the time you'll end up with a 2-color deck, and most of the time when you don't you'll be 3-color. Combined, you'll be in 2 or 3 colors about 89% of the time, and in the extreme cases of 1 or 4 about 11% of the time.

So how did I arrive at the original numbers? Well, I followed the extremely scientific method of _"plug all of this into a spreadsheet with the 1- and 2-color deck counts as parameters, then fiddle with them until I find a combination that both had a distribution I like and doesn't involve me building hundreds of decks"_.


## Lands

As a baseline, I'd like very final deck to have 38 lands. Since the primary purpose of [the colorless supplement][c-supplement] is to provide baseline color fixing and utility artifacts that almost every commander deck would want, I found a set of 10 lands that it could contain. That leaves 28 between the two half-decks. So each half-deck will ultimately contain 14±1 lands (13 lands for half-decks with very low curves, 15 lands for half-decks with very high curves).

[c-supplement]: /decks/00-colorless-supplement


[^1]: 1 and 4 colors are both possible, if you end up with a pair of overlapping single-color decks or non-overlapping two-color decks, respectively.
[^2]: The hypergeometric distribution with parameters _N_, _K_, and _n_ measures the probability Pr( _X_ = _k_ ) of _k_ successes in _n_ draws **without replacement** from a population of size _N_ containing _K_ successful objects. Most famously in Magic, it can be used to determine the probability of drawing exactly _k_ cards with a certain property (e.g., a land) in the first _n_ cards of an _N_-card deck where _K_ cards in your starting deck had the property you're looking for (for example, the probability of drawing an opening hand with exactly 3 lands from a 40-card deck with 17 lands ≈ 32.3%).
[^3]: These configurations (3 or 4 colors with two 1-color decks; 1 or 4 colors with a 1-color and a 2-color deck; and 1 color with two 2-color decks) are impossible.
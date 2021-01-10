---
draft: false
---

:wave:

This is the landing page for my cube project: a commander cube in the style of [JumpStart][jumpstart]. The aim is to create a fast, fun, varied cube format that operates kind of like a board game.

[jumpstart]: https://magic.wizards.com/en/articles/archive/news/introducing-jumpstart-new-way-play-magic-2020-02-20

## How to play

### "Sealed"

Each player randomly selects 4 different [half-decks](/decks), then chooses 2 from that set of four to build their deck: both of the selected half-deck commanders become partner commanders of their full deck[^1], then that player grabs one [colorless supplement][c-supplement] and shuffles all of their non-commander cards together.

> **For example:** let's say you randomly pull [Neheb, the Eternal][neheb]; [Verazol, the Split Current][verazol]; [Eligeth, Crossroads Augur][eligeth]; and [Kwain, Itinerant Meddler][kwain]. You decide that Neheb's mana production would go nicely with a commander like Verazol with its cost of {{< mana x g u >}}. Your deck will be a Temur deck with Neheb and Verazol as partner commanders, and the 98 cards in your starting library will come from Neheb's half-deck, Verazol's half-deck, and the [colorless supplement][c-supplement].

Players then play a normal game of commander (life totals starting at 40, etc.).

[neheb]: /decks/19-burn
[verazol]: /decks/49-kicker
[eligeth]: /decks/07-scry-bal
[kwain]: /decks/31-wu-control

### "Draft"

Order the players randomly. The first player chooses one half-deck from among the full set. Then the next player chooses from among the remainder, and so on until the last player, who picks **two** half-decks. After that, the remaining players pick their second half-decks in reverse order until everyone has two.

> **For example:** If Abby, Ben, Chris, and Dana are drafting the cube in that order:
>
>   1. First, Abby picks their first half-deck.
>   2. Then, Ben picks their first half-deck.
>   3. Then, Chris picks their first half-deck.
>   4. Then, Dana picks both of their half-decks.
>   5. Then, Chris picks their second half-deck.
>   6. Then, Ben picks their second half-deck.
>   7. Finally, Abby picks their second half-deck.

Each player then builds their deck: both of their half-deck commanders become partner commanders of their full deck[^1], then they grab one [colorless supplement][c-supplement] and shuffle all of their non-commander cards together.

Players then play a normal game of commander (life totals starting at 40, etc.).

## Composition

The cube is still a work in progress, but in its eventual state it will have:

  - 4 identical copies of [the colorless supplement][c-supplement] (though putting more together to support more players isn't out of the question)
  - 50 half-decks:
      - 6 decks of each single color
      - 2 decks of each color pair

For details on how I came to those numbers, [check out the math](/math).

## Deck Building

While I don't expect to be able to produce 50 perfectly balanced decks—some will naturally be more or less powerful than others—I'd like them to end up in the same general band. To that end, I'm going to be avoiding:

  - putting very general tutors in any of the decks (perferring very narrow tutors, if any)
  - putting any 2- or 3-card infinite combos in a single deck (pairs of decks may contain combos when shuffled together)
  - including any must-answer value engines (i.e., no {{< card Sylvan Library >}} or {{< card Rhystic Study >}})
  - including any turn-one fast mana (i.e., no {{< card Sol Ring >}}, {{< card Mana Crypt >}}, {{< card Lotus Petal >}}, etc.)

In general, the guiding principle is that **the most powerful cards should be synergistic with the themes of the decks they belong to**. They're allowed to be independently powerful as well, but they should be at their best when surrounded by the rest of their deck.

Decks should be somewhat focused, but shouldn't be nonfunctional without specific non-commander cards. After all, they'll be shuffled together with another deck, and I want to avoid (as much as possible) the situation where drawing an equal mix from both parts leaves a player doing nothing.

To help allow a baseline level of interaction, each half-deck will use the following template as a starting point. Exact quantities can vary slightly if there's a good reason (for example, decks with very low curves might run one fewer land, or decks with higher curves one more; or in some cases categories may overlap with one another; etc.).

{{< comp-chart >}}

  - 1 commander ( {{< set cmd >}} )
  - 14 lands ( {{< symbol land >}} )
  - 27 nonland cards ( {{< symbol multiple >}} ), consisting of:
      - about 2 sweepers ( {{< set v14 >}} ) [^2]
      - about 3 targeted removal spells ( {{< symbol power >}} ) [^2]
      - about 2 ramp spells ( {{< symbol "ability-landfall" >}} ) [^3]
      - about 5 card draw spells ( {{< symbol "counter-lore" >}} ) [^4]
      - a collection of other cards ( {{< symbol "ability-transform" >}} ) that synergize with or otherwise support the theme of the deck

Even though some cards may be in multiple decks, not every deck will have the same suite of removal, ramp, etc. (e.g., not every white deck will have {{< card Path to Exile >}} or {{< card Land Tax >}}). Cards in more specific categories may key off the deck's theme, but they'll do _something_ on their own (taking card draw as an example, {{< card Reverse Engineer >}} is much better with artifacts, but will still draw cards without any).

## Following the cube's development

I'll be developing the cube live on Twitch at http://twitch.tv/sconeforgemystic, every Thursday at 7:00pm Pacific time. For go-live notifications, you can follow me on Twitter ([@SconeforgeMystic](https://twitter.com/sconeforgemystic)). If you know me in person and want to join in the discussion as the decks are built, reach out to me and I'll invite you to the Discord server.

[c-supplement]: /decks/00-colorless-supplement
[^1]: even if they don't have partner, or if they have "partner with" another commander
[^2]: which can at least kill creatures
[^3]: which must permanently accelerate mana production
[^4]: which must produce card advantage (at least 1 card worth) for its controller, and must be able to dig through the library
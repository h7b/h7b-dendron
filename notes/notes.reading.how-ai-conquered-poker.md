---
id: Q7attJXePy0DT9sCWnDtl
title: How AI Conquered Poker
desc: ''
updated: 1647563807747
created: 1642635147089
---
# Reading 2022-01-20

## Metadata

- Ref:: [The New York Times](https://www.nytimes.com/2022/01/18/magazine/ai-technology-poker.html), [Hacker News](https://news.ycombinator.com/item?id=29983043)
- Title:: How A.I. Conquered Poker
- Author:: Keith Romer
- Year of publication:: 2022
- Category:: Blog
- Topic::

## Notes from reading

### Poker discussion
ref: [jeffreyrogers](https://news.ycombinator.com/item?id=29989060), [jdm386](https://news.ycombinator.com/item?id=29992008)

PioSolver requires putting in the hand range of the opponent, so the quality of PioSolver's solution is largely down to how accurate the guess at that hand range is. But if a pro knows he is playing against PioSolver configured with a certain hand range he can just change his strategy to adapt. In theory though if PioSolver knows the correct hand range then it shouldn't be possible to any better than tie given enough hands

Free practice poker tool: [GTO Wizard](https://gtowizard.com/en/), [PioSOLVER free](https://www.piosolver.com/collections/frontpage/products/piosolver-free)

Recommended poker books:
- `The Mathematics of Poker`, by Chen & Ankenman - this one doesn't age because it's really fundamental if you want to understand things from the ground up. But it won't seem that practical at first.
- `Applications of No-Limit Hold'em`, by Matthew Janda - this one goes into specifics about how to think on each street, how to build a good strategy etc. Some of the details will be different from the latest theory because the book was released in 2013 but it's still a very solid read if you want to level up.
- `Modern Poker Theory`. outlines a lot of strategy in the game and talks a little about game theory and its implications
- `Play Optimal Poker` by Andrew Brokos
    - It gives less direct poker advice but uses "toy games" that share some similarities with poker but are simplified to demonstrate some of the implications that game theory has on poker. It does contain some direct poker advice but it's more of a book to teach you how to think properly about how game theory applies to poker and how you can use that to study with something like a solver and actually understand what you're seeing.  I think that the Brokos book assumes you know certain poker terms and doesn't contain a glossary whereas modern poker theory is almost like a textbook and has a section where it defines all of the terms it uses. `Modern poker theory` will have more actionable advice but the Brokos book is excellent to teach you how to think about game theory and requires more self-reflection and has more questions to the reader.
    - `Applications of No-Limit Hold'em` or `The Mathematics of Poker` are recommended by a different reply here. I would caution that these are extremely academic and extremely dense texts that would be a very tough read for a newer player. `The Mathematics of Poker` is less practical and more of a math book than a poker book. Further, `Applications of No-Limit Hold'em` shows how to work out solver-like solutions before solvers existed and also contains a lot of math. I think the other two above (`Modern Poker Theory` and `Play Optimal Poker`) are more practical and aren't going to lead you to put the book down a 10th of the way through.

### Alphastar, StarCraft 2 AI discussion
ref: [dwohnitmok](https://news.ycombinator.com/item?id=29988812), [runnerup](https://news.ycombinator.com/item?id=29994228)

A joy to read the discussion related to `Alphastar`, the StarCraft 2 AI that defeated pro players.
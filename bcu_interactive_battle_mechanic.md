### Interactive Battles in Blockchain Cuties

I'd like to scratch up a simple battle mechanic with actualy gameplay, where winner is decided not on random, but based on how player acts during the battle. One of these weekends I'll implement it and try to push.

Ok, here is the dildo.

We add a new adventure, like "Interactive Land", where you can only send one cutie at a time. Matchmaking takes up to 30 seconds, if opponent not found, you fight with bot. When fight starts, the screen Winter markuped for HP battle reports will appear, with a small addition: there is a list of actions for you to choose in the center. It will consist of three options:

- Attack (Scissors)
    When you choose it, you deal a damage to enemy, equal to your attack + 10 (no 1-20 roll for now in this design to keep things dead simple)
- Defend (Rock)
    When you choose it, if enemy attacked, his dealt damage gets decremented by your defence stat +10, and you get a _Charge_ (see Prepare). If enemy did not attack, you just wasted the turn.
- Prepare (Paper)
    When you choose it, if enemy did not attack, you gain a _Charge_. Charges can stack indefinetely and get spent one at a time whenever you next time attack or defend, multiplying your attack or defence value twice. If enemy attacked, you just wasted the turn.

(the logic may be a bit different in the end, this is just a basic idea)

Opponents make turns simultaneously with up to 10 seconds time available for thinking per turn. If you don't make it in 10 seconds, "Prepare" is automatically chosen. If both players choose attack, they both get damage at same time. This mechanic allows draws.

Winner gets 2 personal blue pots. This is primarily focused on new players that only have one cutie. Though I'd bet older players will also be fond of this mechanic. If this stuff goes well, may think of more use cases, like using it in tournaments, etc...

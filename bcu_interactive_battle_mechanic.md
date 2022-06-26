## Interactive Battles in Blockchain Cuties

I'd like to scratch up a simple battle mechanic with actual gameplay, where winner is decided not on random, but based on how player acts during the battle. One of these weekends I'll implement it and pesent to you, guys.

Ok, here is the deal.

We add a new adventure, like "Interactive Land", where you can only send one cutie at a time. Matchmaking takes up to 30 seconds, if opponent was not found, you fight with a bot. When fight starts, the screen Winter marked-up for HP battle reports will appear, with a small addition: there is a list of actions for you to choose in the center. It will consist of three options:

- Attack (Scissors)
    When you choose it, you deal a damage to enemy, equal to your attack stat, but not less than 1 (no 1-20 roll for now in this design to keep things dead simple)
- Defend (Rock)
    When you choose it, if enemy attacked, his dealt damage gets decremented by your defence stat (but at least 1 damage is dealt to avoid stalemate), and you get a _Charge_ (see Prepare). If enemy did not attack, you just wasted the turn.
- Prepare (Paper)
    When you choose it, if enemy did not attack, you gain a _Charge_. Charges can stack indefinetely and get spent one at a time whenever you next time attack or defend, multiplying your attack or defence value trice. If enemy attacked, you just wasted the turn.

(the logic may be a bit different in the end, this is just a basic idea)

Opponents make turns simultaneously with up to 10 seconds time available for thinking per turn. If you don't make it in 10 seconds, "Prepare" is automatically chosen. If both players choose attack, they both get damage at same time. This mechanic allows draws - nobody gets the drop in this case.

Winner gets 2 personal blue pots and, if fight was against human, 1 Medal of Honor. This is primarily focused on new players that only have one cutie. Though I'd bet older players will also be fond of this mechanic. If this stuff goes well, may think of more use cases, like using it in tournaments, etc...

Note: in this design Attack option is more valuable than others (as it has effect in _any_ case), that's intentional. By making attack the most optimal choice we incentivize player to use it more often, making him eager to get carried away, become predictable and get countered by opponent's "Defence" option (which in it's turn is countered by "Prepare").

![image](https://user-images.githubusercontent.com/5202330/175836478-e21cc5a8-a299-4b46-8761-011a86ed5ae4.png)

______

I was thinking for some time, and one thing that would be good to add to this system is _taunts_. _Taunts_ is a different way to spend the _charges_: when you are making a turn, you can use a _taunt_ on one of the options, spending the charge and notifying the opponent about your chosen taunt action (turn time limit gets refreshed and if opponent already made his turn action, he is allowed to change it). After you _taunted_ the action you may use it (and get the a bonus to it's effect) or may use different action (and waste the charge, but having a good chance of deceiving the opponent). _Taunted_ action bonuses are as follow:

- Attac: damage is multiplied x3, same as it works now, but now you have to _taunt_ it before using
- Protec: if enemy attacked, he gets damaged by the value you reduced with your defence (including multipliers)
- Prepare: in addition to gaining a charge, you also steal a charge from enemy (to make it more effective, even allow making enemy charges negative)

I also thought about making prepare give **2** charges to balance out it being so useless...


## 2k22 update
The initial implementation will be much simpler than what was described in the original 2k20. There won't be complicated special effects from "Prepare" charges and from getting a good counter match. Instead, getting a counter-match will simply nullify enemy's action effect. Charges are to be used as a separate win condition: getting a fixed number of them will make you win regardless of how much hp does the opponent have left, somewhat similar to AoE's [Wonder Victory](https://ageofempires.fandom.com/wiki/Wonder_(Age_of_Empires_II))

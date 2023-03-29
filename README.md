# Everything about ignite, I guess

The following is a collection of brief analyses conducted as part of an effort to gain a better understanding of the bugs associated with Ignite (Munching and Vomit).

## GENERAL TL;DR

### WHAT WE KNEW BEFORE THIS

- Fire Mages (TTW and FFB) are losing DPS due to ignite munching.

### WHAT WE KNOW NOW

- There is a second bug, referred in here as ignite vomit, which in a vacuum results in a DPS gain.
- We confirmed munching is a much bigger problem for TTW mages compared to FFB.
- Across all mages, the negatives effects of "munching" are less severe than expected due to "vomit". But "munching" is still very much a problem.
- The window for an ignite vomit to happen is <40ms and has a ~30% rate of ocurring.

### IMPLICATIONS

- The Mage Sim has been updated to include an option for vomit (a.k.a. bleeding).
- Attempts at consistently replicating and generating vomits in a real setting are currently underway.
- We have a broader understanding of fire mage ignite damage, its bugs, and how they affect us.

# Table of Contents

1. [Munching: The hidden DPS loss on your Ignite](#munching---the-hidden-dps-loss-of-ignite)<br>
    1.1. [What is "munching"?](#what-is-munching)<br>
    1.2. [When is "munching"?](#when-is-munching) <br>
    1.3. [How to (workaround) "munching"?](#how-to-workaround-munching) <br>
    1.4. [Examples of munching](#examples-of-munching) <br>
2. [Vomit: When Ignite goes wrong for the best](#deaths) <br>
    1.1. [What is "vomit"?](#what-is-vomit)<br>
    1.2. [When is "vomit"?](#when-is-vomit) <br>
    1.4. [Examples of munching](#examples-of-vomit) <br>
3. [The vomit window](#interru)<br>
4. [Anonymized Raid Deaths Report](#dea)<br>


## Munching: The hidden DPS loss of Ignite 

#### **Tl,dr:** 

<ins> Ignite **munching**</ins> happens randomly to your ignite damage, and it <ins>is a DPS loss</ins>. More frequent on TTW Mages than FFB mages. As TTW, you can minimize its effects with a WA and/or a macro.

### What is "munching"?

Ignite munching is a well-documented bug [1,2,3] that can cause a loss of DPS for Fire Mages due to how spell interactions work. 

### When is "munching"?

In short, **munching** happens for the most part in 2 scenarios:

1. Living Bomb explosion crits at the same time or extremely close to a projectile critting (fireball, frostfirebolt, or pyroblast).
    - Ignite from the Living Bomb explosion gets munched. 

2. A Pyroblast crits immediately after or extremely close to another projectile crits (fireball or frostfirebolt).
    - Ignite from the projectile before the pyroblast will be munched.

### How to (workaround) "munching"?

Unless you are a TTW mage, there is not much you can do about it.

Because of how projectile travel times work, scenario #2 is more frequently observed among TTW Mages, with fireball having a different travel time compared to frostfire bolt.

The effects of munching on TTW mages can be mitigated by using WAs and macros, making it less likely to happen. 
You can check the FAQ or the commands "!munch" and "!fuckmunch" on [Mage Discord](https://discord.gg/eszwRckRmA) for more details.

However, **munching will STILL happen**, with or without weakauras, and regardless of spec (TTW or FFB).

To the best of our knowledge, this won't be fixed, but you can make yourself heard in the Blizzard Forums by making a post/thread about it.

### Examples of munching

Figure 1: Example of a munching scenario 1. [4]

<img src="img/munch_example.png" />

Figure 2: Example of a munching scenario 1. Different spell [5]

<img src="img/munch_example_2.png" />

### References

1.- [Ignite munching on its way out, one way or another February 23, 2011 ](https://www.engadget.com/2011-02-23-ignite-munching-on-its-way-out-one-way-or-another.html?guccounter=1&guce_referrer=aHR0cHM6Ly93d3cuZ29vZ2xlLmNvbS8&guce_referrer_sig=AQAAAD4s-zDY_aUerkO-18-cyhJQcrgeH8xubvmt371MBNuirIY9RqM4OMzpJpGb3Br798GnMxzw88aoKIwsa_BxHZ_ugd1B1hlkzZ7tW-8JqjSfmm2iLa_mik77fB3SBlYBlYYV73NCN7fBqA0yqsc_bQV-K2xutXyaVFT5x-8HaLlO)

2.- [Ignite Munching wiki article](https://wowwiki-archive.fandom.com/wiki/Ignite_(old))

3.- [!munch @ Mage Discord](https://discord.gg/eszwRckRmA)

4.- [Algalon encounter used for figure 1](https://classic.warcraftlogs.com/reports/WKhF9jBXbQ4MRwnx#fight=17&view=events&source=7&type=damage-done&eventstart=2790468)

5.- [Algalon encounter used for figure 2](https://classic.warcraftlogs.com/reports/FamxdM3W94RBTY87#fight=52&type=damage-done&source=19&view=events)


## Vomit: When Ignite goes wrong for the best

#### **Tl,dr:** 

<ins> Ignite **vomit**</ins> happens randomly to your ignite damage, and it <ins>is a DPS gain</ins>. Intentionally manipulating this bug in our favor seems unrealistic, if not impossible, until someone can replicate it consistently AND demonstrate it can be used in a real scenario. 

### What is "vomit"?

A less well-documented Ignite bug in Wrath of the Lich King is the opposite of Ignite Munch (from now on, "Ignite Vomit"), which allows an ignite to keep rolling and result in an additional tick that should not have occurred.

Until recently (at the moment of writing), this bug had not been documented or described at all for Wrath of the Lich King Classic.

This bug has been discussed in an [ElitistJerk forum thread in 2008 [1]](https://web.archive.org/web/20100412150438/http://elitistjerks.com/f31/t19766-mage_rolling_ignites_they_back/), and the first documented claim for it can be traced back to another [ElitistJerk thread in 2007[2]](https://web.archive.org/web/20110810120414/http://elitistjerks.com/f31/t12302-mage_ignites_working_correctly/).

<img src="img/old_2007.png" />

<img src="img/human_mage_2007.png" />

Additionally, a brief explanation of the bug can be found in the [wow wiki section for Ignite Bugs, under the section "Known Bugs"](https://wowwiki-archive.fandom.com/wiki/Ignite_(old)#Past_changes). 

Unlike "Ignite Munching", which has a section named for its own in the wiki, Ignite Vomit is simply described in one paragraph as something that can happen, but that should not be confused with the old "rolling" ignite system from pre-2.0 (known to us as "Classic").

### When is "vomit"?

Vomit occurs when a spell crits as the same time (or extremely close) to an ignite tick.

Figure 1: Example of a vomit scenario. The spell before ignite crits/lands on the same timestamp as the ignite, according to logs.[3]

<img src="img/vomit_example.png" />

Figure 2: Example of a vomit scenario.  The spell before ignite crits/lands 28ms before the ignite.[4]

<img src="img/vomit_example_2.png" />

### Practical example

[The following log has a practical example, from figure 2,](https://classic.warcraftlogs.com/reports/a:mZaNPdTgzLFBVW8K#fight=3&type=damage&source=14&target=123&view=events) of vomit ocurring "naturally"

(log shared by @Redteam#9819 in [#🐲sim-and-log-review at Mage Discord](https://discord.gg/eszwRckRmA) long ago, and taken as an example after a vomit event was discovered months later)

00:39.416 seconds into the log the following happens

```
1.- Ignite tick for 6687

2.- Fireball crits for 7984 
[adds to ignite: 7984 * 0.4 = 3193] 
expected ignite tick: (6687+3193) / 2 =  4939

Immediately after the fireball:
3.- Ignite ticks for 6687

4.- Living bomb crits for 2007 
[adds to ignite: 2007 * 0.4 = 802]

5.- Fireball crits for 9393 
[adds to ignite:  9393 * 0.4 = 3757]

6.- Ignite ticks for 7220
```
To get a 7220 ignite tick you would need an ignite of 14440, which is only possible if the following happened:

3193 (From 2.- Fireball) + 802 (From 4.- LB) + 3757 (From 5.- FB) + 6686 (From 3.- IG due to "Vomit")

Doing :

**(A)** 802 (4.- LB) + 3757 (5.- FB) + 3193 (2.- FB)  = 7752 / 2 = 3876

or

**(B)** 802 (4.- LB) + 3757 (5.- FB) + 6686 (3.- IG)  = 11245/ 2 = 5622

Do not get close to the 7220 ignite tick seen in the log

### Additional examples

Another example can be seen (here [6]:)[https://classic.warcraftlogs.com/reports/64xjRNaFgtr3Qd9b#fight=5&type=damage&source=9&phase=2&target=97&view=events]

At the ignites that happen at 02:30.103, 02:32.086 and 02:34.105, with a vomit event happening 02:30.082

<img src="img/vomit_example_3.png" />


### References

1.- https://web.archive.org/web/20100412150438/http://elitistjerks.com/f31/t19766-mage_rolling_ignites_they_back/

2.- https://web.archive.org/web/20110810120414/http://elitistjerks.com/f31/t12302-mage_ignites_working_correctly/

3.- [Algalon encounter used for figure 1](https://classic.warcraftlogs.com/reports/WKhF9jBXbQ4MRwnx#fight=17&view=events&source=7&type=damage-done&eventstart=2790468)

4.- [Patchwerk encounter used for figure 1](https://classic.warcraftlogs.com/reports/a:mZaNPdTgzLFBVW8K#fight=3&type=damage&source=14&target=123&view=events)

5.- [Practical example log #1](https://classic.warcraftlogs.com/reports/a:mZaNPdTgzLFBVW8K#fight=3&type=damage&source=14&target=123&view=events)

6.- [Practical example log #2](https://classic.warcraftlogs.com/reports/64xjRNaFgtr3Qd9b#fight=5&type=damage&source=9&phase=2&target=97&view=events)

# Other analysis done

- Check other things I have done here: https://github.com/ForgeGit?tab=repositories


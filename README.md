# Everything about ignite, I guess

The following is a collection of brief analyses conducted as part of an effort to gain a better understanding of the bugs associated with Ignite (Munching and Vomit).

## Tl;dr 

### WHAT WE KNEW BEFORE THIS

### ADDED VALUE 

### IMPLICATIONS


# Table of Contents

1. [Munching](#munching---the-hidden-dps-loss-of-ignite) <br>
2. [Vomit](#deaths) <br>
3. [Graphic v.1.a](#interru)<br>
4. [Anonymized Raid Deaths Report](#dea)<br>


## Munching - The hidden DPS loss of Ignite 

#### **Tl,dr:** 

<ins> Ignite **munching**</ins> happens randomly to your ignite damage, and <ins>it is a DPS loss</ins>. More frequent on TTW Mages than FFB mages. As TTW, you can minimize its effects with a WA and/or a macro.

### What is "munching"?

Ignite munching is a well-documented bug [1,2,3] that can cause a loss of DPS for Fire Mages due to how spell interactions work. 

### When is "munching"?

In short, **munching** happens for the most part in 2 scenarios:

1. Living Bomb explosion crits at the same time as a projectile crits (fireball, frostfirebolt, or pyroblast).
    - Ignite from the Living Bomb explosion gets munched. 

2. A Pyroblast crits immediately after a projectile crits (fireball or frostfirebolt) .
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

1.- [Ignite munching on its way out, one way or another February 23, 2011 ](https://www.engadget.com/2011-02-23-ignite-munching-on-its-way-out-one-way-or-another.html?guccounter=1&guce_referrer=aHR0cHM6Ly93d3cuZ29vZ2xlLmNvbS8&guce_referrer_sig=AQAAAD4s-zDY_aUerkO-18-cyhJQcrgeH8xubvmt371MBNuirIY9RqM4OMzpJpGb3Br798GnMxzw88aoKIwsa_BxHZ_ugd1B1hlkzZ7tW-8JqjSfmm2iLa_mik77fB3SBlYBlYYV73NCN7fBqA0yqsc_bQV-K2xutXyaVFT5x-8HaLlO)

2.- [Ignite Munching wiki article](https://wowwiki-archive.fandom.com/wiki/Ignite_(old))

3.- [!munch @ Mage Discord](https://discord.gg/eszwRckRmA)

4.- [Algalon encounter used for figure 1](https://classic.warcraftlogs.com/reports/WKhF9jBXbQ4MRwnx#fight=17&view=events&source=7&type=damage-done&eventstart=2790468)

5.- [Algalon encounter used for figure 2](https://classic.warcraftlogs.com/reports/FamxdM3W94RBTY87#fight=52&type=damage-done&source=19&view=events)


## Vomit: When Ignite goes wrong for the best

A less well-documented Ignite bug in Wrath of the Lich King is the opposite of Ignite Munch (from now on, "Ignite Vomit"), which allows an ignite to keep rolling and result in an additional tick that should not have occurred.

This bug has been  discussed in an [ElitistJerk forum thread in 2008 [1]](https://web.archive.org/web/20100412150438/http://elitistjerks.com/f31/t19766-mage_rolling_ignites_they_back/), and the first documented claim for it can be traced back to another [ElitistJerk thread in 2007[2]] (https://web.archive.org/web/20110810120414/http://elitistjerks.com/f31/t12302-mage_ignites_working_correctly/).

<img src="img/old_2007.png" />

<img src="img/human_mage_2007.png" />

Additionally, a brief explanation of the bug can be found in the [wowwiki section for Ignite Bugs, under the section "Known Bugs"](https://wowwiki-archive.fandom.com/wiki/Ignite_(old)#Past_changes). 

Unlike "Ignite Munching", which is a bug interaction with a section named for its own in the wiki, Ignite Vomit is just described in a one paragraph as something that can happen, but that should not be confused with the old "rolling" ignite system from pre-2.0 (known to us as "Classic").

Figure 1: Example of a vomit scenario. The spell before ignite crits/lands on the same timestamp as the ignite, according to logs. [3]
<img src="img/vomit_example.png" />

Figure 2: Example of a vomit scenario.  The spell before ignite crits/lands 28ms before the ignite. [4]
<img src="img/vomit_example_2.png" />


1.- https://web.archive.org/web/20100412150438/http://elitistjerks.com/f31/t19766-mage_rolling_ignites_they_back/
2.- https://web.archive.org/web/20110810120414/http://elitistjerks.com/f31/t12302-mage_ignites_working_correctly/
3.- [Algalon encounter used for figure 1](https://classic.warcraftlogs.com/reports/WKhF9jBXbQ4MRwnx#fight=17&view=events&source=7&type=damage-done&eventstart=2790468)
4.- [Patchwerk encounter used for figure 1](https://classic.warcraftlogs.com/reports/a:mZaNPdTgzLFBVW8K#fight=3&type=damage&source=14&target=123&view=events)

# Other analysis done

- Check other things I have done here: https://github.com/ForgeGit?tab=repositories


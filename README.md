# Unlimited Callouts 2

A fixed/updated version of the [Unlimited Callouts mod by Sambot](https://steamcommunity.com/sharedfiles/filedetails/?id=563159491), updated to work with newer versions of Prison Architect.

## Installation

Install the mod off of [Steam Workshop](https://steamcommunity.com/sharedfiles/filedetails/?id=2564810339).

Altneratively, you can download this repository and move the `Unlimited Callouts 2` folder into your Prison Architect mods folder.

## Changes

* Adds a new callout to request elite ops via truck for $1000 each.
* Sets the limit of all callouts to `2^28`.
* Gives elite ops the sound effects of soldiers.
* Buffs speed of troop trucks to match the speed of other emergency vehicles.

## Description

Unlimited Callouts 2 is a mod for Prison Architect that does two things:

1. Allows you to have practically infinite emergency services callouts (i.e. firemen, paramedics, riot police; technically the limit is `2^31 - 1`, but for all intents and purposes, that is as good as infinite)

2. Adds elite ops that arrive by truck to the list of emergency services callouts, costing $1000 per truck of six troops, and also having the same practically infinite limit as the other callouts.

It has become slightly dysfunctional in more recent versions of the game (the callout for the soldiers will appear, but none of the buttons are actually clickable), so this particular mod aims to do the same thing for recent versions of Prison Architect.

The problem with the old mod appears to center around the `MaxNumber` property of all the `Callout`s. `MaxNumber` defines the maximum number of that callout you can have simultaneously. For example, if the `MaxNumber` for firefighter teams is 3, then I can have at most 3 firefighter teams in my prison at a time. In Sambot's original mod, the `MaxNumber` for all the callouts was `2^31 - 1`, or `2147483647`. In previous versions of Prison Architect, this worked fine, but in newer versions, the game appears to do some kind of math that will "set" a limit for `MaxNumber` based on the number of units that arrive with any given callout.

One of the things this mod does is reduce the limit from `2^31 - 1` to a number that is acceptable for Prison Architect again. From experimenting, it appears that the highest value you can put in `MaxNumber` for a callout with a `NumEntities` of `4` (that is, the callout will spawn 4 units) is `2^29 - 1`, and for callouts with a `NumEntities` of `6`, the number is in the range, in mathematical notation, `[2^28, 2^29 - 1)`. Thus, this mod sets the `MaxNumber` value for all callouts to `2^28`. You will probably never get anywhere close to these limits (I tried spawning in 1,150 troop trucks and my FPS dropped to 2), so these are as good as infinite for standard gameplay.

Sambot's original Unlimited Callouts mod also added a callout for a truck of soldiers. In the spirit of preserving the original UC mod's features, this mod was also going to add a callout for soldiers. However, at the time of writing, the AI for soldiers is dysfunctional, so they have been replaced with the elite ops that are now in the game instead. I find it to be a suitable replacement, as they have very similar behavior to the called out soldiers. I may add another callout for soldiers or replace the elite ops with them in the future if they get fixed, but for the time being, elite ops will be available in their place.
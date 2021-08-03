# Unlimited Callouts 2

A fixed/updated version of the [Unlimited Callouts mod by Sambot](https://steamcommunity.com/sharedfiles/filedetails/?id=563159491), updated to work with newer versions of Prison Architect.

## Installation

Install the mod off of [Steam Workshop](https://steamcommunity.com/sharedfiles/filedetails/?id=2564810339).

Altneratively, you can download this repository and move the `Unlimited Callouts 2` folder into your Prison Architect mods folder.

## What is this?

Unlimited Callouts is a mod for Prison Architect that does two things:

1. Allows you to have practically infinite emergency services callouts (i.e. firemen, paramedics, riot police; technically the limit is `2^31 - 1`, but for all intents and purposes, that is as good as infinite)

2. Adds soldiers / National Guard to the list of emergency services callouts, costing $1000 per truck of six troops, and also having the same practically infinite limit as the other callouts.

It has become slightly dysfunctional in more recent versions of the game (the callout for the soldiers will appear, but none of the buttons are actually clickable), so this particular mod aims to do the same thing for recent versions of Prison Architect.

The problem with the old mod appears to center around the `MaxNumber` property of all the `Callout`s. `MaxNumber` defines the maximum number of that callout you can have simultaneously. For example, if the `MaxNumber` for firefighter teams is 3, then I can have at most 3 firefighter teams in my prison at a time. In Sambot's original mod, the `MaxNumber` for all the callouts was `2^31 - 1`, or `2147483647`. In previous versions of Prison Architect, this worked fine, but in newer versions, the game appears to do some kind of math that will "set" a limit for `MaxNumber` based on the number of units that arrive with any given callout.

This mod simply reduces the limit from `2^31 - 1` to a number that is acceptable for Prison Architect again. From experimenting, it appears that the highest value you can put in `MaxNumber` for a callout with a `NumEntities` of `4` (that is, the callout will spawn 4 units) is `2^29 - 1`, and for callouts with a `NumEntities` of `6`, the number is in the range, in mathematical notation, `[2^28, 2^29 - 1)`. Thus, this mod sets the `MaxNumber` value for all callouts to `2^28`, except for the Air Soldiers callout, which has a maximum of `2^27` since the 28th power was too high. You will probably never get anywhere close to these limits (I tried spawning in 1,150 troop trucks of soldiers and my FPS dropped to 2), so these are as good as infinite for standard gameplay.

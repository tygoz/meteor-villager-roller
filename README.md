# Meteor Villager Roller

![checks](https://github.com/maxsupermanhd/meteor-villager-roller/actions/workflows/checks.yml/badge.svg)
![devbuild](https://github.com/maxsupermanhd/meteor-villager-roller/actions/workflows/devbuild.yml/badge.svg)

Addon that changes villager proffession until desired trade found

## Versions

| Minecraft | Supported |
| --------- | --------- |
| 1.18.1 | Yes |
| 1.18 | Compile-yourself |
| 1.17.1 | No (branch planned) |
| 1.17 | Compile-yourself |
| 1.16 1.16.x | Compile-yourself *|
| < 1.16 | No |

\* Imports modification required because of meteor refactoring

## Solving use-case

Addon is targeted for lazy people that are playing on server and trying to find enchantment on librarians. No functionality about other trades/proffessions implemented and planned, you can pull request them if you really want to.

## How-to

1. Acquire villager (not nitwit)
2. Acquire *some* lecterns (32 will be good)
3. (Recommended, not required) Acquire axe, better quality - faster rolling
4. Confine yourself and a villager from step 1 in a space where no freely moving enteties and blocks are present (except villager and you)
5. Block villager from wandering around (slabs, blocks, stairs, *not trapdoors* since those mess with pathfinding)
6. Place a lectern where villager can access it and ensure that hand-rolling of proffession is possible
7. Configure module to your needs and enable it
8. Follow selection of block and villager from chat messages
9. Leave module running alone (switching focus from window will likely open pause menu and *pause* rolling if "Pause on screens" option is enabled, disable it if you know what you are doing)
10. Profit!

## Common issues

- It says "We got your villager" twice and stops \
  Addon is designed to run on servers. Singleplayer and plugins can interfeer with how merchant screens behave, nothing that can be done about it.
- I can not interact with villager anymore \
  See above, screen desync can be fixed by rejoining server. Nothing that can be done about it.
- It does not place lecterns back \
  It does place lecterns back, if it failed it means that block is impossible to place because player, villager, other entity or block is already occupying that block. Rolling process will hang because of this but will resume after manual block placement.
- It closes chat/overlay/screens while rolling \
  Yes it does because there is no way to not to, when interaction with villager is requested server will force client to open merchant screen (will replace any screen that is present) and opening that screen is required to get list of trades from the villager. Toggle "Pause on screens" will prevent new interactions if any screen is open (to aboid force closing it), after you done what you wanted you can manually interact with villager to resume rolling.
- It does not collect lecterns and fails to place them when they run out \
  Searching, pathfinding and moving to specific item on the ground is difficult and messy, there always a chance that all lecterns will fly away from player and it will end up with empty hands. You can optimise it by having hopper-dropper setup or flowing water if you really want to. Feel free to implement non distructive moving towards dropped item if you want.
- It always rolls to best level of enchantment \
  Because it is designed to do exactly that. There is no easy way to make a list selector in settings that will specify enchantment level, feel free to make one yourself.

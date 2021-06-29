# simple-configs

A simple set of configuration files for Portal 2 speedrunning with SAR.

## Installation

Place all these config files within the `Portal 2/portal2/cfg` directory, as is;
they should automatically be run by the game as necessary. Ensure [SAR] is
installed.

[SAR]: https://github.com/p2sr/SourceAutoRecord

## Categories

These configuration files support the following speedrun categories in
singleplayer:
- Inbounds No SLA (`fullgame`)
- any% (`anypc`)
- Singleplayer Challenge Mode (`sp_cm`)

And the following in coop:
- All Main Courses (`amc`)
- All Courses (`ac`)
- Coop Challenge Mode (`coop_cm`)

To manually switch to a category, simply run the category name as a
command; for instance, the command `anypc` activates the any% category.

By default, the configs will try to automatically detect the right
category when you load into a map. To disable this, see the
'Customisation svars' section below. Note that singleplayer any% and
coop All Courses cannot be detected; if you are running these
categories, you must manually switch to them. While one of these two
categories is selected, the auto-detection system is disabled.

## Binds

You *must* set the following binds for the configs to function
correctly:
- `bind mwheelup +scrollup`

You can bind the following commands:
- `funneling_toggle` - toggle portal funneling
- `fullbright_toggle` - toggle fullbright
- `sensitivity_toggle` - toggle low sensitivity
- `useswap_toggle` - toggle scrollup being use
- `+supershoot` - hold to enable scrollup being shoot
- `30fps_toggle` - toggle 30fps mode (for coop button glitches and certain SLA tricks)
- `contimes_toggle` - toggle seeing contimes text (e.g. for double dialogue skip)
- `dialogue_toggle` - toggle the dialogue from glados, wheatley, and the announcer
- `do_load <save name>` - load a save only if in non-CM singleplayer
- `do_reset` - reset your run

The aliases `cm_only` and `non_cm_only` can be used to make a bind only
effective in certain cases, to handle rule differences between the
[CM boards] and [speedrun.com]. For instance, a key bound to `cm_only
funneling_toggle` would toggle portal funneling if and only if you were
playing CM.

[CM boards]: https://board.portal2.sr
[speedrun.com]: https://speedrun.com/portal_2

## Customisation svars

- `no_dialogue_toasts`  - when 1, disable dialogue fade toasts
- `no_auto_category`    - when 1, disable automatic speedrun category selection

## Extra configuration

Rather than modifying this autoexec.cfg directly, it is recommended you
put any "personal" configuration (e.g. setting svars, performing HUD
customisation) in `extra.cfg`. This file will be execed once by the
autoexec.

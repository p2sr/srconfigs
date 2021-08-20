# srconfigs

A simple-to-use set of configuration files for Portal 2 speedrunning with SAR.

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
categories, you must manually switch to them.

After manually selecting a category, the automatic selection will not be
run until the `auto` command is run to re-enable it.

## Binds

You *must* set the following binds for the configs to function
correctly:
- `bind mwheelup +scrollup`
- `bind mwheeldown +scrolldown`

You can bind the following commands:
- `funneling_toggle` - toggle portal funneling
- `fullbright_toggle` - toggle fullbright
- `lowsens_toggle` - toggle low sensitivity
- `useswap_toggle` - toggle scrollup being use
- `supershoot_toggle` - toggle scroll being shoot
- `30fps_toggle` - toggle 30fps mode (for coop button glitches and certain SLA tricks)
- `contimes_toggle` - toggle seeing contimes text (e.g. for double dialogue skip)
- `dialogue_toggle` - toggle the dialogue from glados, wheatley, and the announcer
- `do_load <save name>` - load a save only if in non-CM singleplayer
- `do_reset` - reset your run

All of the `_toggle` binds also have `+`/`-` versions; e.g.
`+supershoot` can be bound to enable supershoot only while a key is
held.

The aliases `cm_only` and `non_cm_only` can be used to make a bind only
effective in certain cases, to handle rule differences between the
[CM boards] and [speedrun.com]. For instance, a key bound to `cm_only
funneling_toggle` would toggle portal funneling if and only if you were
playing CM.

[CM boards]: https://board.portal2.sr
[speedrun.com]: https://speedrun.com/portal_2

## Customisation svars

- `no_dialogue_toasts`      - when 1, disable all dialogue fade toasts
- `no_dialogue_toasts_sp`   - when 1, disable dialogue fade toasts in singleplayer
- `no_dialogue_toasts_coop` - when 1, disable dialogue fade toasts in coop
- `no_auto_category`        - when 1, disable automatic speedrun category selection
- `coop_cm_enable_hud`      - when 1, don't disable the CM stats HUD in coop
- `coop_no_stopvideos`      - when 1, don't run `stopvideos` on every coop load
- `fullgame_demo_name`      - defaults to `%Y-%m-%d_%H-%M-%S/fullgame`
- `anypc_demo_name`         - defaults to `%Y-%m-%d_%H-%M-%S/anypc`
- `sp_cm_demo_name`         - defaults to `chapter$chapter/$map/$map`
- `amc_demo_name`           - defaults to `$role/%Y-%m-%d_%H-%M-%S/amc`
- `ac_demo_name`            - defaults to `$role/%Y-%m-%d_%H-%M-%S/ac`
- `coop_cm_demo_name`       - defaults to `$role/course$course/$map/$map`

Demo names may use the following strings:
- `$chapter` / `$course` - interchangable. The number of the chapter (e.g. `8`)
- `$chapter_name` / `$course_name` - interchangable. The name of the chapter (e.g. `the-itch`)
- `$map` - the human-readable map name (e.g. `triple-laser`)
- `$role` - in coop, either `blue` or `orange`

## Extra configuration

Rather than modifying this autoexec.cfg directly, it is *highly
recommended* you put any "personal" configuration (e.g. setting svars,
performing HUD customisation) in `extra.cfg`. This file will be run
once by the autoexec. This file should be used in order to make updating
this set of config files easier; as long as the autoexec is never
modified, updates should be a simple drag-and-drop process.

In this file you can define extra categories if you wish, using the
`add_cat` and `detect_cat` commands. For instance, to add a category
named "tournament" and automatically switch to it when on a specific
map, simply add this to `extra.cfg`:

	add_cat tournament
	detect_cat tournament "map=workshop/123456/map_name"

When this category is activated, as well as every map load in which it
is enabled, the file `cats/tournament.cfg` will be `exec`d; this file
should therefore contain the necessary configuration for the category.
Look at the built-in category files for an example.

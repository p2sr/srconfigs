# srconfigs

A simple-to-use set of configuration files for speedrunning Portal 2 and its mods with SAR.

## Installation

Place all these config files within the `Portal 2/portal2/cfg` directory, as is;
they should automatically be run by the game as necessary. Ensure [SAR] is
installed.

[SAR]: https://github.com/p2sr/SourceAutoRecord

## Categories

These configuration files support the following speedrun categories:
- Inbounds No SLA (`fullgame`)
- any% (`anypc`)
- Singleplayer Challenge Mode (`sp_cm`)
- All Main Courses (`amc`)
- All Courses (`ac`)
- Coop Challenge Mode (`coop_cm`)
- Chapter ILs (`chapter_il`)
- Celeste Mode (`celeste` - P2SM only)

To manually switch to a category, simply run the category name as a
command; for instance, the command `anypc` activates the any% category.

The configs will try to automatically detect the right
category when you load into a map. Note that singleplayer any% and
coop All Courses cannot be detected; if you are running these
categories, you must manually switch to them.

After manually selecting a category, the automatic selection will not be
re-enabled until the `auto` command is ran.

Note that in mods, only the `fullgame` category exists from the above.
Some mods also add a simple `il` category for doing individual level
runs.

## Binds

You *must* set the following binds for the configs to function
correctly:
- `bind mwheelup +scrollup`
- `bind mwheeldown +scrolldown`

When used in Portal Reloaded, the command to shoot a time portal is `+attack3`. Therefore you should set this bind:
- `bind mouse3 +attack3`

It is recommended to change your chat bind (`say`) to the more general `chat` provided by srconfigs.
- `bind <key> chat`

You can bind the following commands:
- `funneling_toggle` - toggle portal funneling
- `fullbright_toggle` - toggle fullbright
- `customsens_toggle <sensitivity>` - toggle custom sensitivity
- `useswap_toggle` - toggle scrollup being use
- `supershoot_toggle` - toggle scroll being shoot
- `30fps_toggle` - toggle 30fps mode (for coop button glitches and certain SLA tricks)
- `contimes_toggle` - toggle seeing contimes text (e.g. for double dialogue skip)
- `dialogue_toggle` - toggle the dialogue from glados, wheatley, and the announcer
- `do_load <save name>` - load a save only if in non-CM singleplayer. (Deprecated - see `cm_only` and `non_cm_only` below)
- `do_reset` - reset your run

All of the `_toggle` binds also have `+`/`-` versions; e.g.
`+supershoot` can be bound to enable supershoot only while a key is
held.

The aliases `cm_only` and `non_cm_only` can be used to make a bind only
effective in certain cases, e.g. `bind r "cm_only restart_level"`

## HUD text

Every toggle has a piece of associated HUD text which can be shown or
hidden at will. By default, the texts corresponding to funneling and
dialogue are shown.

The text visibility can be changed using `sar_hud_show_text` and
`sar_hud_hide_text`; for instance, `sar_hud_show_text 2` will show the
text corresponding to fullbright. The text IDs are below.

- 0: dialogue
- 1: funneling
- 2: fullbright
- 3: customsens
- 4: useswap
- 5: supershoot
- 6: 30fps
- 7: contimes

## Customisation svars

You can customise the behaviour of srconfigs by setting the following
svars using the `svar_set` command. For instance,
`svar_set no_dialogue_toasts 1` will disable dialogue fade toasts.

- `sp_use_save`             - Selects which save to use for Portal 2 Fullgame, Any%, and Chapter 1 runs. 0 - no save, 1 - containerridesave, 2 - vault save. Defaults to 1.
- `mel_use_save`            - Selects which save to use for Portal Stories: Mel runs. 0 - no save, 1 - tram save. Defaults to 0.
- `no_dialogue_toasts`      - when 1, disable all dialogue fade toasts
- `no_dialogue_toasts_sp`   - when 1, disable dialogue fade toasts in singleplayer
- `no_dialogue_toasts_coop` - when 1, disable dialogue fade toasts in coop
- `no_taunt_toasts_coop`    - when 1, disable [taunt] toasts in coop
- `show_map_name_coop`      - when 1, show the current map name in coop. Defaults to 1.
- `show_blank_fades`        - when 1, show [no fade] for maps that don't have a dialogue fade. Defaults to 1.
- `coop_cm_enable_hud`      - when 1, don't disable the CM stats HUD in coop. Defaults to 1.
- `coop_no_stopvideos`      - when 1, don't run `stopvideos` on every coop load
- `coop_no_remoteview`      - when 1, don't enable remote view on every coop load
- `cm_attempt_counter`      - when 1, show an attempt counter on the SAR HUD in CM. Defaults to 1.
- `cm_ghost_server`         - when 1, connect to a world-wide ghost server when playing CM. Off by default.
- `chapter_il_betsrighter`  - when 1, give betsrighter in relevant chapter IL runs (i.e. chapter 2-9 in Portal 2). Defaults to 1.
- `chapter_il_fly`          - when 1, give fly in relevant chapter IL runs (i.e. chapter 9 in Portal 2). Defaults to 1.
- `useswap_invert`          - when 1, invert the `useswap` toggle so that `+useswap` makes both scrolls jump
- `useswap_both`            - when 1, make the `useswap` toggle affect mwheeldown as well as mwheelup
- `supershoot_use_orange`   - when 1, make the `supershoot` toggle shoot the orange portal instead of blue
- `cm_keep_pb_only`         - when 1, only store PB demos in CM. Requires CM board autosubmission to be set up!
- `fullbright_amount`       - defaults to 0.1; the value to use for `mat_ambient_light` when toggling fullbright
- `anypc_transition_time`   - defaults to 0. `ui_loadingscreen_transition_time` for the `anypc` category
- `enable_menu_transitions` - defaults to 0. Re-enables the transition effects in menus.
- `demo_folder_name`        - defaults to `demos`
- `fullgame_demo_name`      - defaults to `%Y-%m-%d_%H-%M-%S/fullgame`
- `anypc_demo_name`         - defaults to `%Y-%m-%d_%H-%M-%S/anypc`
- `sp_cm_demo_name`         - defaults to `chapter$chapter/$map/$map`
- `amc_demo_name`           - defaults to `$role/%Y-%m-%d_%H-%M-%S/amc`
- `ac_demo_name`            - defaults to `$role/%Y-%m-%d_%H-%M-%S/ac`
- `coop_cm_demo_name`       - defaults to `$role/course$course/$map/$map`
- `il_demo_name`            - defaults to `chapter$chapter/$map/$map`
- `chapter_il_demo_name`    - defaults to `$role/$chapter_course/%Y-%m-%d_%H-%M-%S/$chapter_course`
- `celeste_demo_name`       - defaults to `%Y-%m-%d_%H-%M-%S/celeste`
- `reverse_demo_name`       - defaults to `%Y-%m-%d_%H-%M-%S/reverse`

Demo names may use the following strings:
- `$chapter` / `$course` - interchangable. The number of the chapter (e.g. `8`)
- `$chapter_name` / `$course_name` - interchangable. The name of the chapter (e.g. `the-itch`)
- `$chapter_course` - e.g. `chapter1` in SP or `course1` in coop
- `$map` - the human-readable map name (e.g. `triple-laser`)
- `$formatted_map` - the human-readable map name in title case and spaced (e.g. `Triple Laser`)
- `$role` - in coop, either `blue` or `orange`

## Chapter ILs

Chapter ILs have an extra command you should use in order to set which
chapter you're running. The command `run_cur_chapter` will set up
chapter ILs to run the chapter for the map you're currently in; or
alternatively, you can use the command `run_chapter 5` (for instance) to
set it up to run chapter 5. This will automatically force the
`chapter_il` category (so you should use `auto` to later switch to other
categories). Once you've set the chapter to run, you can use your reset
bind etc as normal.

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

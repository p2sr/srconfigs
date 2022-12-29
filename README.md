# srconfigs

A simple-to-use set of configuration files for speedrunning Portal 2 and its mods with SAR.

## Installation

Place all these config files within the `Portal 2/portal2/cfg` directory, as is;
they should automatically be run by the game as necessary. Ensure [SAR] is
installed. Refer to the [Speedrun Setup Guide] for a video tutorial.

[SAR]: https://github.com/p2sr/SourceAutoRecord
[Speedrun Setup Guide]: https://youtu.be/fnFenfXjrtg?t=37

## Categories

These configuration files support the following speedrun categories:

- Inbounds No SLA (`fullgame`)
- Any% (`anypc`)
- Singleplayer Challenge Mode (`sp_cm`)
- All Main Courses (`amc`)
- All Courses (`ac`)
- Solo Coop (`solocoop`)
- Coop Challenge Mode (`coop_cm`)
- Chapter ILs (`chapter_il`)
- Celeste Mode (`celeste` - P2SM only)
- Reverse Mod (`reverse` - P2SM only)
- Workshop (`workshop`)

To manually switch to a category, simply run the category name as a
command; for instance, the command `anypc` activates the Any% category.

The configs will try to automatically detect the right
category when you load into a map. Note that singleplayer Any%,
coop All Courses, and Solo Coop cannot be detected; if you are running these
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

- `dialogue_toggle` - toggle the dialogue from glados, wheatley, and the announcer
- `funneling_toggle` - toggle portal funneling
- `fullbright_toggle` - toggle fullbright
- `customsens_toggle <sensitivity>` - toggle custom sensitivity
- `useswap_toggle` - toggle scrollup being use
- `supershoot_toggle` - toggle scroll being shoot
- `30fps_toggle` - toggle 30fps mode (for coop button glitches and certain SLA tricks)
- `contimes_toggle` - toggle seeing contimes text (e.g. for double dialogue skip)
- `swapsplit` - switch between the blue and orange robots when playing solocoop
- `do_load <save name>` - load a save only if in non-CM singleplayer. (Deprecated - see `cm_only` and `non_cm_only` below)
- `do_reset` - reset your run

All of the `_toggle` binds also have `+`/`-` versions; e.g.
`+supershoot` can be bound to enable supershoot only while a key is
held.

The aliases `cm_only`, `non_cm_only`, `cat_only`, and `non_cat_only`
can be used to make a bind only effective in certain cases, e.g.
`bind r "cm_only do_reset; cat_only amc stopvideos"`

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
svars using the `svar_set` command.

For instance, `svar_set no_dialogue_toasts 1` will disable dialogue fade toasts.

|            Name            | Default | Description
| -------------------------- | :-----: | -----------
| `sp_use_save`              |    1    | Selects which save to use for Portal 2 Fullgame, Any%, and Chapter 1 runs.<br>0 - no save, 1 - [containerridesave], 2 - [vault save].
| `mel_use_save`             |    0    | Selects which save to use for Portal Stories: Mel runs.<br>0 - no save, 1 - [tram save].
| `no_dialogue_toasts`       |    0    | When 1, disable all dialogue fade toasts.
| `no_dialogue_toasts_sp`    |    0    | When 1, disable dialogue fade toasts in singleplayer.
| `no_dialogue_toasts_coop`  |    0    | When 1, disable dialogue fade toasts in coop.
| `no_taunt_toasts_coop`     |    0    | When 1, disable `[taunt]` toasts in coop.
| `show_map_name_coop`       |    1    | When 1, show the current map name in coop.
| `show_blank_fades`         |    1    | When 1, show `[no fade]` for maps that don't have a dialogue fade.
| `coop_cm_enable_hud`       |    1    | When 1, don't disable the CM stats HUD in coop.
| `coop_no_stopvideos`       |    0    | When 1, don't run `stopvideos` on every coop load.
| `coop_no_remoteview`       |    0    | When 1, don't enable remote view on every coop load.
| `coop_no_remoteview_lobby` |    0    | When 1, don't enable remote view on coop loads into the Lobby.<br>Turn this on if you experience lag in the Lobby.
| `solocoop_fullscreen`      |    0    | When 1, have one fullscreen view in Solo Coop instead of splitscreen.
| `cm_attempt_counter`       |    1    | When 1, show an attempt counter on the SAR HUD in CM.
| `cm_ghost_server`          |   -1    | When 1, connect to a world-wide ghost server when playing CM.
| `chapter_il_betsrighter`   |    1    | When 1, give [Betsrighter] in relevant Chapter IL runs. (i.e. chapter 2-9 in Portal 2)
| `chapter_il_fly`           |    1    | When 1, give [Crouch Fly] in relevant Chapter IL runs. (i.e. chapter 9 in Portal 2)
| `useswap_invert`           |    0    | When 1, invert the useswap toggle so that `+useswap` makes both scrolls jump.
| `useswap_both`             |    0    | When 1, make the useswap toggle affect `+scrolldown` as well as `+scrollup`.
| `supershoot_use_orange`    |    0    | When 1, make the supershoot toggle shoot the orange portal instead of blue.
| `cm_keep_pb_only`          |    0    | When 1, only store PB demos in CM. Requires [CM board autosubmission] to be set up!
| `fullbright_amount`        |   0.1   | The value to use for `mat_ambient_light` when toggling fullbright.
| `anypc_transition_time`    |    0    | `ui_loadingscreen_transition_time` for the `anypc` category.
| `enable_menu_transitions`  |    0    | Re-enables the transition effects in menus.
| `demo_folder_name`         |  demos  | Name of the folder for demos.<br>e.g. `.../steamapps/common/Portal 2/portal2/demos/...`

[containerridesave]: https://drive.google.com/open?id=1ZwhBdnYNeFi2pVEvhlAq_EU1OD1WFS8k
[vault save]: https://www.speedrun.com/resourceasset/azdcg
[tram save]: https://cdn.discordapp.com/attachments/811780246608281650/983275907022204938/tram.sav
[Betsrighter]: https://wiki.portal2.sr/Wakeup
[Crouch Fly]: https://wiki.portal2.sr/Crouch_Flying_Glitch
[CM board autosubmission]: https://youtu.be/3GLUW4sGmLs?t=392

|          Name          | Default
| ---------------------: | :------
| `fullgame_demo_name`   | `%Y-%m-%d_%H-%M-%S/fullgame`
| `anypc_demo_name`      | `%Y-%m-%d_%H-%M-%S/anypc`
| `sp_cm_demo_name`      | `chapter$chapter/$map/$map`
| `amc_demo_name`        | `$role/%Y-%m-%d_%H-%M-%S/amc`
| `ac_demo_name`         | `$role/%Y-%m-%d_%H-%M-%S/ac`
| `solocoop_demo_name`   | `%Y-%m-%d_%H-%M-%S/solocoop`
| `coop_cm_demo_name`    | `$role/course$course/$map/$map`
| `il_demo_name`         | `chapter$chapter/$map/$map`
| `chapter_il_demo_name` | `$role/$chapter_course/%Y-%m-%d_%H-%M-%S/$chapter_course`
| `celeste_demo_name`    | `%Y-%m-%d_%H-%M-%S/celeste`
| `reverse_demo_name`    | `%Y-%m-%d_%H-%M-%S/reverse`
| `workshop_demo_name`   | `%Y-%m-%d_%H-%M-%S/workshop`

Demo names may use the following strings:

- `$chapter` / `$course` - interchangeable. The number of the chapter (e.g. `8`)
- `$chapter_name` / `$course_name` - interchangeable. The name of the chapter (e.g. `the-itch`)
- `$chapter_course` - e.g. `chapter1` in SP or `course1` in coop
- `$map` - the human-readable map name (e.g. `triple-laser`)
- `$formatted_map` - the human-readable map name in title case and spaced (e.g. `Triple Laser`)
- `$role` - in coop, either `blue` or `orange`
- Other [strftime] timestamp syntax

[strftime]: https://cplusplus.com/reference/ctime/strftime

## Chapter ILs

Chapter ILs have an extra command you should use in order to set which
chapter you're running.

The command `run_cur_chapter` will set up chapter ILs to run the chapter
for the map you're currently in; or alternatively, you can use the command
`run_chapter 5` (for instance) to set it up to run chapter 5.

This will automatically force the `chapter_il` category (so you should use
`auto` to later switch to other categories). Once you've set the chapter
to run, you can use your reset bind etc as normal.

## CM Autoreset

Included in srconfigs is a feature that automatically resets CM
([Challenge Mode]) runs if you don't reach splits by certain times.

To use this functionality, make a folder in the uppercase Portal 2
directory called `autoreset`. In this folder, make a file called
`<map>.txt` where `<map>` is what you get from `svar_get map` while on
the map, e.g. `portal-gun.txt`.

Then, on each line in this file you can add the tick number at
which the run should be reset. For example, with the following
`portal-gun.txt`:

```txt
316
686
1098
1930
1930
2004
```

The run would be automatically reset if you didn't reach the Door Trigger
in 5.267 seconds (316 ticks), the Drop Trigger in 11.433 seconds
(686 ticks), etc.

The `sar_speedrun_result` command will output these tick values at the
end of each split line.

If a certain split doesn't matter, you can set its cutoff time to that
of the next split, as shown above on the fourth split.

[Challenge Mode]: https://wiki.portal2.sr/Challenge_Mode

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

```cfg
add_cat tournament
detect_cat tournament "map=workshop/123456/map_name"
```

When this category is activated, as well as every map load in which it
is enabled, the file `cats/tournament.cfg` will be `exec`d; this file
should therefore contain the necessary configuration for the category.
Look at the built-in category files for an example.

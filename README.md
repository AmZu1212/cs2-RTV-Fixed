<p align="center">
  <img src="https://github.com/user-attachments/assets/6d5549f3-7fdc-4f4f-a26d-739863f46055" alt="cs2"/>
</p>

![Top Banner](https://github.com/user-attachments/assets/7fda2d74-d90f-4a15-a4f0-2e73835bf580)
# CS2 Rock The Vote (Fixed)
A Patch for abnerfs's rtv system for cs2. The code was changed to support counterstrikesharp version 1.0.318

General purpose map voting plugin, started as a simple RTV and now has more features.

Please consider supporting Abnerfs's since this is originally his work:

[![](https://www.paypalobjects.com/en_US/i/btn/btn_donate_LG.gif)](https://www.paypal.com/donate/?hosted_button_id=XDAQUYUGT5PTJ)

## Enjoy
 - Not planning on maintaining this plugin, so feel free to fork or download and publish your future fixes :D
 - please check out Abnerfs's repo and leave a star! [![click here](https://github.com/abnerfs/cs2-rockthevote)]
## Requirements (Last working version was 1.0.318)
[Latest release of Counter Strike Sharp](https://github.com/roflmuffin/CounterStrikeSharp)

# Installation
- Download the latest release
- Extract the .zip file into `addons/counterstrikesharp/plugins`
- Run your server client once
- close the server client
- edit the config file in `addons/counterstrikesharp/config/RockTheVote`
- Enjoy!


## Documentation courtesy of Abnerfs:
# Features
- Reads from a custom maplist
- RTV Command
- Timeleft command
- Nominate command
- Votemap command
- Supports workshop maps
- Nextmap command
- Fully configurable
- Translated by the community

# Translations
| Language             | Contributor          |
| -------------------- | -------------------- |
| Brazilian Portuguese | abnerfs              |
| English              | abnerfs              |
| Ukrainian            | panikajo             |
| Turkish              | brkvlr               |
| Russian              | Auttend              |
| Latvian              | rcon420              |
| Hungarian            | Chickender, lovasatt |
| Polish               | D3X                  |
| French               | o3LL                 |
| Chinese (zh-Hans)    | himenekocn           |

# Configs
- A config file will be created in `addons/counterstrikesharp/configs/plugins/RockTheVote` the first time you load the plugin.
- Changes in the config file will require you to reload the plugin or restart the server (change the map won't work).
- Maps that will be used in RTV/nominate/votemap/end of map vote are located in addons/counterstrikesharp/configs/plugins/RockTheVote/maplist.txt

## General config
| Config         | Description                                                                      | Default Value | Min | Max |
| -------------- | -------------------------------------------------------------------------------- | ------------- | --- | --- |
| MapsInCoolDown | Number of maps that can't be used in vote because they have been played recently | 3             | 0   |     |

## RockTheVote
Players can type rtv to request the map to be changed, once a number of votes is reached (by default 60% of players in the server) a vote will start for the next map, this vote lasts up to 30 seconds (hardcoded for now), in the end server changes to the winner map.

| Config              | Description                                                                                                            | Default Value | Min   | Max                                  |
| ------------------- | ---------------------------------------------------------------------------------------------------------------------- | ------------- | ----- | ------------------------------------ |
| Enabled             | Enable/Disable RTV functionality                                                                                       | true          | false | true                                 |
| EnabledInWarmup     | Enable/Disable RTV during warmup                                                                                       | false         | false | true                                 |
| NominationEnabled   | Enable/Disable nomination                                                                                              | true          | false | true                                 |
| MinPlayers          | Minimum amount of players to enable RTV/Nominate                                                                       | 0             | 0     |                                      |
| MinRounds           | Minimum rounds to enable RTV/Nominate                                                                                  | 0             | 0     |                                      |
| ChangeMapImmediatly | Whether to change the map immediatly when vote ends or not                                                             | true          | false | true                                 |
| HudMenu             | Whether to use HudMenu or just the chat one, when false the hud only shows which map is winning instead of actual menu | true          | false | true                                 |
| HideHudAfterVote    | Whether to hide vote status hud after vote or not, only matters when HudMenu is true                                   | false         | false | true                                 |
| MapsToShow          | Amount of maps to show in vote,                                                                                        | 6             | 1     | 6 with HudMenu, unlimited without it |
| VoteDuration        | Seconds the RTV should can last                                                                                        | 30            | 1     |                                      |
| VotePercentage      | Percentage of players that should type RTV in order to start a vote                                                    | 60            | 0     | 100                                  |


## End of map vote
Based on mp_timelimit and mp_maxrounds cvar before the map ends a RTV like vote will start to define the next map, it can be configured to change immediatly or only when the map actually ends

| Config                  | Description                                                                                                            | Default Value | Min   | Max                                  |
| ----------------------- | ---------------------------------------------------------------------------------------------------------------------- | ------------- | ----- | ------------------------------------ |
| Enabled                 | Enable/Disable end of map vote functionality                                                                           | true          | false | true                                 |
| ChangeMapImmediatly     | Whether to change the map immediatly when vote ends or not                                                             | true          | false | true                                 |
| HideHudAfterVote        | Whether to hide vote status hud after vote or not, only matters when HudMenu is true                                   | false         | false | true                                 |
| MapsToShow              | Amount of maps to show in vote,                                                                                        | 6             | 1     | 6 with HudMenu, unlimited without it |
| VoteDuration            | Seconds the RTV should can last                                                                                        | 30            | 1     |                                      |
| HudMenu                 | Whether to use HudMenu or just the chat one, when false the hud only shows which map is winning instead of actual menu | true          | false | true                                 |
| TriggerSecondsBeforeEnd | Amount of seconds before end of the map that should trigger the vote, only used when mp_timelimit is greater than 0    | 120           | 1     |                                      |
| TriggerRoundsBeforEnd   | Amount of rounds before end of map that should trigger the vote, only used when mp_maxrounds is set                    | 2             | 1     |                                      |
| DelayToChangeInTheEnd   | Delay in seconds that plugin will take to change the map after the win panel is shown to the players                   | 6             | 3     |                                      |

## Votemap
Players can vote to change to an specific map by using the votemap <mapname> command

| Config              | Description                                                              | Default Value | Min   | Max  |
| ------------------- | ------------------------------------------------------------------------ | ------------- | ----- | ---- |
| Enabled             | Enable/disable votemap funtionality                                      | true          | false | tru  |
| VotePercentage      | Percentage of players that should vote in a map in order to change to it | 60            | 1     | 100  |
| ChangeMapImmediatly | Whether to change the map immediatly when vote ends or not               | true          | false | true |
| EnabledInWarmup     | Enable/Disable votemap during warmup                                     | true          | false | true |
| MinRounds           | Minimum rounds to enable votemap                                         | 0             |       |      |
| MinPlayers          | Minimum amount of players to enable votemap                              |               |       |      |


## Timeleft
Players can type `timeleft` to see how much time is left in the current map 

| Config    | Description                                                                      | Default Value | Min   | Max  |
| --------- | -------------------------------------------------------------------------------- | ------------- | ----- | ---- |
| ShowToAll | Whether to show command response to everyone or just the player that executed it | false         | false | true |

## Nextmap
Players can type `nextmap` to see which map is going to be played next

| Config    | Description                                                                      | Default Value | Min   | Max  |
| --------- | -------------------------------------------------------------------------------- | ------------- | ----- | ---- |
| ShowToAll | Whether to show command response to everyone or just the player that executed it | false         | false | true |


  
# Adding workshop maps
- If you are not hosting a collection in order to add workshop maps you need to know it's id and add as following in the maplist.txt file: `<mapname>:<workshop-id>`.
- If you are already hosting a collection and can change to workshop maps using the command `ds_workshop_changelevel <map-name>` you don't need the id, just put the actual map name and it will work.

```
de_thera:3121217565
de_dust2
```

![Bottom Banner](https://github.com/user-attachments/assets/37fdd0cc-1e97-464d-82f6-6b3a6e116ac4)

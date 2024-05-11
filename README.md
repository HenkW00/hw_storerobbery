# HW Scripts | Store Robbery [ESX] [OX]

## Introduction
This comprehensive Lua script is designed for use on FiveM servers running the ESX framework. It enables dynamic store robbery scenarios where players can engage in criminal activities by robbing safes at various store locations across the game map. The script includes detailed configurations for police interaction, item requirements, skill checks, and more.

## :white_check_mark: Features
- Players can lockpick and rob safes in various stores, requiring specific items and skill checks
- Depending on the server configuration, the script notifies police with details about ongoing robberies.
- Robberies require specific items like lockpicks and are subject to skill checks to increase gameplay complexity.
- Admins can customize robbery parameters, including police requirements, cooldown periods, and more.

## :globe_with_meridians: Dependencies
- [es_extended](https://github.com/ESX-Org/es_extended)
- [ox_inventory](https://github.com/overextended/ox_inventory)
- [ox_lib](https://github.com/overextended/ox_lib)
- [hw_utils](https://hw-scripts-store.tebex.io/package/6258214) -> FREE
- [cd_dispatch](https://forum.cfx.re/t/paid-codesign-police-dispatch/2007097) -> PAID
- [linden_outlawalert](https://github.com/thelindat/linden_outlawalert) -> FREE

## :white_check_mark: Configuration
The configuration options can be found in `config.lua`:
```lua
Config = {}

Config.checkForUpdates = true -- Recommended to leave as 'true'
Config.Debug = true -- Not yet finished, probbaly in one of the upcomming updates...
Config.EnableLogs = true -- Do you want to enable discord logging?
Config.Webhook = 'https://discord.com/api/webhooks/1238481168282681426/3h_clAohvwsoWByvXf7OMH-8VoDF-3RIra7DLVdTu81M7jeXujlLBClVfyy0EJzD4mlV' -- URL for logging to discord
Config.DiscordBotName = 'HW Logs' -- How should the bot name be called?

Config.PoliceJobs = { -- Jobs that count as cops (needed for counting online cops)
    'police',
    'sheriff',
    'trooper',
}

Config.MinPolice = 0 -- Minimum police needed online to start the robbery
Config.DispatchType = "default" -- [cd_dispatch / linden / default] 
Config.PoliceCanRob = true -- Allow players with police jobs to rob?
Config.Cooldown = 15 -- Cooldown for each safe in minutes
Config.ShowAllBlips = false -- Store safe blips show on map or not? (this overwrites al blip states below)
Config.BlipName = 'Safe Robbery'

Config.SafeLocations = {
    {
        Position = vector3(-43.3865, -1748.3951, 29.4210), -- Target location
        Reward = 'black_money', -- Item to get after successful robbery
        RewardRange = {5000, 15000}, -- Minimum and Maximum count for the reward item
        NeededItem = {"lockpick", 1}, -- itemname, count
        ProgressLength = math.random(10000,25000), -- In ms, how long should the animation be
        Blip = true, -- Show blip
        Robbed = false -- Don't touch
    },
}
```

## :wrench: Download & Installation
Follow these steps to set up the script on your ESX server:

1. **Download the Files**: Download the script files from the provided source.
2. **Copy to Server Resource Directory**: Place the `hw_storerobbery` folder in the server resource directory.
3. **Update `server.cfg`**: Add the following line to your `server.cfg` file:
    ```cfg
    start hw_storerobbery
    ```
4. **Start Your Server**: Restart or start your ESX server to load the `hw_storerobbery` resource.

If help is needed, you can contact me via discord.
Link for that you can find in console upon restarting the script, otherwise just search for HenkW00 on google/github/CFX

Enjoy the script, I hope you like it! <3

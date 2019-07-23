# discord-server-manager
Players have to link their discord account before they could use the restricted commands

## Description
This is a discord version of the SWGM plugin, it was requested HERE by paulo_crash
Players can't use the restricted commands if they are not connected to the discord server.

When a player connect, he will get an assign ID, with he can link his account through discord.

## Known bugs
If a player disconnect from the discord server after he has linked it ingame, it wont be refreshed, I'll fix it in the next release.

## Dependencies
You can't run this plugin at all without Discord-API
SMJansson - Required for Discord-API
SteamWorks - Required for Discord-API

## Installation
Create a discord bot, and a new channel in your server
Upload the smx and the .ini to your server
Edit the "cfg/sourcemod/discord_server_manager.cfg" with your details

## Cvars
dsm_token "" // Your discord bot token
dsm_channel_id "" // Channel ID in discord where the players can link their accounts
dsm_assign_command "!link" // Command in discord to link the account. eg.( !link 12345 )
dsm_use_swgm "0" // 1 - Use the same .ini as the SWGM for the commands | 0 - Use a new ini (configs/dsm/command_listener.ini)  


## Commands
sm_link //The player can get his assign id with this command  

## Natives && Forwards



/** 
 * Check if the client has linked his account
 * 
 * 
 * @param client        Client Index. 
 * @return             True if the client has an accountlinked, false otherwise. 
 */ 
native bool DSM_IsDiscordMember(int client);

/**
 * Called when a player has linked his account
 * @param client client that has linked the account.
 */
forward void DSM_OnClientLinkedAccount(int client);  


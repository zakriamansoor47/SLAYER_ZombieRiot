# Accepting Paid Request! Discord: Slayer47#7002
# Donate: If you like my work, you can donate to me via [Steam Trade Offer](https://bit.ly/3qDpgPd)

## Description:
Humans need to fight against Zombies by eliminating all of them in that day (in that round) before they can continue to the next level. And be aware, that if you get infected by Zombie you will turn into a Zombie.

## Gameplay:
https://www.youtube.com/watch?v=ys8GR-f7X-U

## Installation:
**1.** Upload files to your server.

**2.** Edit **configs/plugins/SLAYER_ZombieRiot/SLAYER_ZombieRiot.json** if you want to change the settings.

**3.** Change the Map **or** Restart the Server **or** Load the Plugin.


## Commands:
`!zriot_human <player name>` - Make Zombie a Human (Only for Admins with specific flag)
`!zriot_zombie <player name>` - Make Human a Zombie (Only for Admins with specific flag)
`!zriot_setday <number of the day>` - Change current Day (Only for Admins with specific flag)

## Configuration:
```
{
	"ZRiot_PluginEnabled": true,			// Enable/Disable Zombie Riot Plugin
	"ZRiot_HudText": true,					// Enable persistent display of the HUD which displays day, zombies left, and humans left (false = Disable)
	"ZRiot_NoBlock": true,					// Enable/Disable NoBlock for Zombies. Prevents zombies from getting stuck in each other
	"ZRiot_Regression": true,				// If the zombies win the round, the game will regress one day (false = Disable)
	"ZRiot_Freeze": 10,						// Time, in seconds, to freeze zombies at round start to allow humans to get set up (0 = Disable)
	"ZRiot_FirstRespawn": 10,				// Amount of time to wait before spawning a player into the game for the first time (0 = Disable)
	"ZRiot_Respawn": 30,					// Amount of time each human has to wait before they will respawn into the game (0 = Disable)
	"ZRiot_ZombieMax": 12,					// The max amount of zombies spawned at one time
	"ZRriot_Cashamount": 12000,				// How much money Human players will have when they spawn (0 = Disable)
    "ZRriot_HumanWinSoundPath": "",			// Sound Play when Humans Wins. Please Use real file extension of the sound like '.mp3' or '.wav' instead of '.vsnd_c' ("" = Disable)
    "ZRriot_ZombieWinSoundPath": "",		// Sound Play when Zombie Wins. Please Use real file extension of the sound like '.mp3' or '.wav' instead of '.vsnd_c' ("" = Disable)
    "ZRriot_ZombieDieSoundPath": "",		// Zombie Die Sounds Path (Seperate Each Sound Path with ';'). Play Random Sound.  Please Use real file extension of the sound like '.mp3' or '.wav' instead of '.vsnd_c' ("" = Disable)
    "ZRriot_AdminFlagToUseCMDs": "@css/root",
	"ZRiot_Days": [
		// Here you can pre-define each day and its difficulty
		// Format:
		//  "DayName" - This is what the day will be referred to
		//	"ZKillCount" - How many zombies that need to be killed before moving onto the next day
		//	"ZHealthBoost" - The amount of extra HP each zombie will get in addition to that zombie's initial health
		//	"ZRespawn" - If enabled, all zombies will be immediately respawn after death, when the day kill limit is
		//	          - reached, the remaining zombies dig into the ground and the next day will begin
		//            - Respawn is typically 'false' for bosses
		//	"DeathsBeforeZombie" - How many deaths as human before being switched to the Zombie force (0: Disable)
		//	"ZombieOverride" - OPTIONAL: If specified only listed zombies will be spawned during this day, separate with "," (look in zombies.txt)
		//	"DayStoryLine" - OPTIONAL: If specified, the text will be printed on round_start for the day, used to illustrate some kind of story line
		{
		  "DayName": "Outbreak",
		  "ZKillCount": 15,
		  "ZHealthBoost": 0,
		  "ZRespawn": true,
		  "DeathsBeforeZombie": 2,
		  "ZombieOverride": "",
		  "DayStoryLine": "This is the First Day Called: Outbreak"
		},
		{
		  "DayName": "Uprising",
		  "ZKillCount": 16, // 25
		  "ZHealthBoost": 25,
		  "ZRespawn": false,
		  "DeathsBeforeZombie": 0,
		  "ZombieOverride": "",
		  "DayStoryLine": ""
		},
		{
		  "DayName": "Riot!",
		  "ZKillCount": 17, // 30
		  "ZHealthBoost": 50,
		  "ZRespawn": true,
		  "DeathsBeforeZombie": 2,
		  "ZombieOverride": "",
		  "DayStoryLine": ""
		},
		{
		  "DayName": "Rampage",
		  "ZKillCount": 18, // 50
		  "ZHealthBoost": 75,
		  "ZRespawn": true,
		  "DeathsBeforeZombie": 2,
		  "ZombieOverride": "",
		  "DayStoryLine": ""
		},
		{
		  "DayName": "Surge",
		  "ZKillCount": 19, // 75
		  "ZHealthBoost": 100,
		  "ZRespawn": true,
		  "DeathsBeforeZombie": 2,
		  "ZombieOverride": "",
		  "DayStoryLine": ""
		},
		{
		  "DayName": "Storm",
		  "ZKillCount": 20, // 100
		  "ZHealthBoost": 125,
		  "ZRespawn": true,
		  "DeathsBeforeZombie": 2,
		  "ZombieOverride": "",
		  "DayStoryLine": ""
		},
		{
		  "DayName": "Containment",
		  "ZKillCount": 21, // 200
		  "ZHealthBoost": 150,
		  "ZRespawn": true,
		  "DeathsBeforeZombie": 2,
		  "ZombieOverride": "",
		  "DayStoryLine": ""
		},
		{
		  "DayName": "Final Stand",
		  "ZKillCount": 1,
		  "ZHealthBoost": 0,
		  "ZRespawn": false,
		  "DeathsBeforeZombie": 0,
		  "ZombieOverride": "Hell Knight", // Boss Zombie
		  "DayStoryLine": "This is the Last Day Called: Final Stand"
		}
		// Add your Days Here
	],
	"ZRiot_Zombies": [
		// Here you can pre-define the different zombies and their abilities
		// Format:
		//	"ZombieClassName" - Any word(s) to help keep track of the different zombies
		//	"ZombieTypeNormal" - 'true' will spawn the zombie randomly in the day (unless the day has a zombieoverride)
		//	       				- 'false' this zombie can only be spawned via an override defined in days.txt
		//	"ZombieModelPath" - [Optional] Enter the Path of the Custom Zombie Model
		//	"ZombieHealth" - Spawn HP of this zombie
		//	"ZombieSpeed" - Speed of the zombie (1.0 = Normal, <1.0 = Slow, >1.0 = Fast)
		//	"ZombieGravity" - Gravity of the zombie (1.0 = Normal Gravity, <1.0 = Low Gravity, >1.0 = High Gravity)
		//	"ZombieJump" - Extra jump power that the zombie will receive (recommended you lower the gravity as you raise this)
		//	"ZombieFOV" - Field of vision (Default: 90)
		{
		  "ZombieClassName": "Classic",
		  "ZombieModelPath": "characters/models/tm_professional/tm_professional_varf3.vmdl",
		  "ZombieTypeNormal": true,
		  "ZombieHealth": 100,
		  "ZombieSpeed": 1.1,
		  "ZombieGravity": 0.9,
		  "ZombieJump": 15.0,
		  "ZombieFOV": 110
		},
		{
		  "ZombieClassName": "Splinter",
		  "ZombieModelPath": "characters/models/tm_professional/tm_professional_varf4.vmdl",
		  "ZombieTypeNormal": true,
		  "ZombieHealth": 90,
		  "ZombieSpeed": 1.2,
		  "ZombieGravity": 0.95,
		  "ZombieJump": 10.0,
		  "ZombieFOV": 110
		},
		{
		  "ZombieClassName": "Leep",
		  "ZombieModelPath": "characters/models/tm_professional/tm_professional_varf5.vmdl",
		  "ZombieTypeNormal": true,
		  "ZombieHealth": 100,
		  "ZombieSpeed": 1.1,
		  "ZombieGravity": 1.0,
		  "ZombieJump": 50.0,
		  "ZombieFOV": 110
		},
		{
		  "ZombieClassName": "Heavy",
		  "ZombieModelPath": "characters/models/tm_phoenix_heavy/tm_phoenix_heavy.vmdl",
		  "ZombieTypeNormal": true,
		  "ZombieHealth": 200,
		  "ZombieSpeed": 0.8,
		  "ZombieGravity": 1.0,
		  "ZombieJump": 17.0,
		  "ZombieFOV": 110
		},
		{
		  "ZombieClassName": "Hell Knight",
		  "ZombieModelPath": "characters/models/tm_professional/tm_professional_varf2.vmdl",
		  "ZombieTypeNormal": false,
		  "ZombieHealth": 15000,
		  "ZombieSpeed": 1.2,
		  "ZombieGravity": 0.6,
		  "ZombieJump": 30.0,
		  "ZombieFOV": 110
		}
		// Add your Zombie Classes Here
	],
	"ConfigVersion": 1
}
```

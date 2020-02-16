# Editing the Character Save JSON 

In this document, we'll break down all of the different parts of the save file which are relevant to those that are interested in modding their offline character. If you're looking for a particular field, please use the CTRL + F function to better navigate to the section that you desire. 

With that out of the way, lets start by breaking it down. 

## Lines 2-7: 
### Contents: File Information :heavy_check_mark:

	"Name":	"Player",
	"PlayerId":	"offlineplayer",
	"CharacterId":	"Player",
	"DifficultyMode":	1,
	"League":	1,
	"UpdatedAt":	"20-02-13T18:46:10Z",

### "Name"

This definies the name of your character.

### "PlayerId"

**Always** have this set to this to **"offlineplayer"** as we'll never be editing an online character (seriously though... just don't, it's a sure way to lose your purchase and get banned)
  
### "CharacterId"

This has to match the **"Name"** peramater on Line 1
  
### "DifficultyMode"

This is used to define the difficulty that the character is set to load into in the file. There are two variations of how this can be set.

Game Mode | Values
----------|---------
Story | 0 / 1
Champions of Stormwall | 1

**0** - This is the **Story Mode Difficulty**
**1** - This is the **Normal Difficulty**

As Champions of Stormwall is not part of the story, the 0 value is not applicable.

### "League" 

Currently not used in general day-to-day editing and the function is unknown at this time.

### "UpdatedAt" 

This is when the last update was made by the game client. 

## Lines 8-19
### Contents: "CharacterCustomization" :heavy_check_mark:

		"Sex":	1,
		"Face":	6,
		"SkinColor":	600,
		"Haircut":	100,
		"HairColor":	30,
		"Beard":	1,
		"BeardColor":	5,
		"LeftEye":	12,
		"RightEye":	12,
		"Archetype":	2
	},

A brief look at this set of variables allows us to choose each part of the character that is available on creation through the in game UI. This section will be expanded upon when all of the values for each variable have been identified. 

The interesting thing to note, that along with the cosmetic values, we can also see the players "Archetype" choice amongst the cosmetics.
	
## Lines 20-33 "Stats" :heavy_check_mark:


	"Stats":	{
		"Strength":	90,
		"Agility":	90,
		"Constitution":	90,
		"Power":	90,
		"Level":	90,
		"PassiveSkillPoints":	0,
		"CurrentXP":	"7618",
		"RemainingStatsPoints":	890,
		"Gold":	"999999",
		"PrimordialAffinity":	"999999",
		"IsAutoDashAvailable":	1,
		"DashStatusActivation":	0

This is everyones dream, to be able to modify values in a clean and easy way. The numeric values that you see / change here will be directly visible and effecting your character in game. 

For further clarification, these stats are named in game differently to those in the save file, so do keep in mind which stats your editing. Also, they're not in the same order is in the game.

Name in JSON | Name in Game
-------------|---------------
Strength | Fortitude
Agility | Agility
Constitution | Toughness
Power | Wisdom

### Safe Values for "Strength" / "Agility" / "Constitution" / "Power"

Minimum Value | Known Safe Value
--------------|------------------
10 | 1000

Given that a character will be able recieve 890 points over the course of the levelling process, these values are given as basics that you'd be able to set across all fields. They can more than likely go into the 10,000 range, but this hasn't been tested at the time of writing. 

### "Level"
This is your character level. The one that your experience bar increases when you fill it up.

Minimum Value | Maximum Value
--------------|------------------
1 | 90

### "PassiveSkillPoints"

This is the number of **Unassigned Passive Skill Points** that your character has available. The maximum without further complications at this time is 89, due to the characters maximum level being 90.

Minimum Value | Maximum Value
--------------|------------------
0 | 89

### "CurrentXP"

This dictates the amount of experience that is currently displayed in the Experience Bar. Values can differ depending on the level of the character as the amount needed will increase with each passing level. Recommended to set the "Level" of the character instead of the "Experience" I would recommend setting this to **0**

### "RemainingStatsPoints"

This is the number of **Unassigned Stat Points** that your character has available. The known safe value is 890, as we gain 10 per level on the way to level 90. Further testing will be needed to see if there are any issues going above this value.

Minimum Value | Known Safe Value
--------------|------------------
0 | 890

### "Gold" :heavy_dollar_sign:

$$$$ - You know what this is.

Minimum Value | Known Safe Value
--------------|------------------
0 | 999999

### "PrimordialAffinity"

This is the Purple Currency that is gained when you sell Enneracts to the merchant in town or redeem a skill that you already own. 

Minimum Value | Known Safe Value
--------------|------------------
0 | 999999

### "IsAutoDashAvailable" 1 / "DashStatusActivation" 0 :no_entry:

## Line 34-39 "UnlockedSkills"


	"UnlockedSkills":	[{
			"SkillName":	"player_brutalstrike",
			"Level":	1,
			"CurrentXp":	"0",
			"Variants":	"0000000000000000"
		}],

This group of information is used to define which skills your character has learnt through Enneracts. In these fields we can see key information about how they are broken down. 

### "SkillName" 

This is the internal name of the skill that is available for your character. All of the skills can be found at the following link. The skill name is the same as the .xml file as a **UID**

https://gitlab.com/erosson/wolcendb/-/tree/master/datamine/Game/Umbra/Skills/NewSkills/Player


### "Level"

This dictates the level of skill which in turn, unlocks runes and points to be able to assign to them.

Minimum Value | Maximum Value
--------------|------------------
1 | 90

### "CurrentXp":

This sets the current experience value for the skill. I would recommend just setting the level, not the xp and leaving this field at **0**

### "Variants" :no_entry:

This has a use, but little is known about it as of yet.

### Example
An example of having multiple high level skills set up looks like the following:

	"UnlockedSkills":	[{
			"SkillName":	"player_aetherblade",
			"Level":	30,
			"CurrentXp":	"0",
			"Variants":	"0000000000000000"
		}, {
			"SkillName":	"player_aetherblast",
			"Level":	30,
			"CurrentXp":	"0",
			"Variants":	"0000000000000000"
		}, {
			"SkillName":	"player_arrowsrain",
			"Level":	30,
			"CurrentXp":	"0",
			"Variants":	"0000000000000000"
		},

# Editing the Character Save JSON 

In this document, we'll break down all of the different parts of the save file which are relevant to those that are interested in modding their offline character. If you're looking for a particular field, please use the CTRL + F function to better navigate to the section that you desire. 

With that out of the way, lets start by breaking it down. 

## Lines 2-7: 
### Contents: File Information

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
### Contents: "CharacterCustomization"

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
	
## Lines 20-33 "Stats"


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





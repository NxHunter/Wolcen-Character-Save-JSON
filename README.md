# Editing the Character Save JSON 

In this document, we'll break down all of the different parts of the save file which are relevant to those that are interested in modding their offline character. If you're looking for a particular field, please use the CTRL + F function to better navigate to the section that you desire. 

With that out of the way, lets start by breaking it down. 

## Lines 1-3: "Name" "PlayerId" "CharacterId" "DifficultyMode" "League" "UpdatedAt"

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

	"CharacterCustomization":	{
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

This repository is mainly a tutorial for how to edit the Character Save JSON

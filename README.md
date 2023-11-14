# A MapTool macro for rolling from JSON and more for GURPS by Emdis

Provides the ability to roll custom skills, attributes and listed skills. 

Skills have to be manually ripped from GCS and GCA save files (character sheets). 

Has input filtering, rudimentary tooltips for 'vs' numbers, conditional output formatting, correct critical thresholds based on the effective skill (not Telegraphic yet).

Displays colored crits; margin of success or failure.

Can be used for blind rolls through ` [gm:] ` with the included calling macro.

![2023-11-13_22-20](https://github.com/saint-thomas-more/maptool-roll-popup/assets/126619536/0e00a1c4-3dee-4823-972d-c904937771d4)

## Possible output
` ST⁠–10, modifiers: +2+3-2 -1+10 =>  10 vs (22): succeeded by 12 `

![2023-11-13_22-21](https://github.com/saint-thomas-more/maptool-roll-popup/assets/126619536/0d8fdcb7-3ec0-4dd4-8a4d-dfcd6f622367)

***
## GCA

`.gdf` files are `.xml` under-the-hood and must be converted to `.json`.

## GCS

`.gcs` files are `.json` under-the-hood.
- The sheet must not contain skill containers as they complicate the ` .json ` sctructure.

## Ripping the skills array

1. Open your `.json` in Notepad, for example.
2. Find the array:
	` "skills": [...] `.
3. Copy the brackets and their content.
4. Paste into the property.

## MapTool properties

- Takes individual attribute properties for the input with the regular GURPS short names, i.e.:
	- ST
	- DX
 	- IQ
  	- HT
  	- Will
  	- Per 
- Requires a ` Skills ` property (isn't case sensitive).
- Input for the ` Skills ` property: 
	` [ {skill-object}, {skill-object}, ... ] `
- Requires a ` SheetType ` property with ` GCA ` or ` GCS ` listed.

***

## Input Filtering for the Modifier window

- Accepts strings with addition and substraction.
- Accepts any symbols on the number row and replaces them with correct numbers and signs.
` _@=& ` becomes `-2+7 `.
- Accepts spaces.
- Accepts repeating signs and replaces them with a singular sign.
- The first number can be written without a sign. Adds "+" in this case.

- Throws an error for "+-" combinations.
- Throws an error for incorrect symbols.

## Input Filtering for the Custom SL window

- Must be a number
- Accepts any symbols on the number row and replaces them with correct numbers and signs.
- Filters out + and - signs.

- Throws an error if the filtered result isn't a number.

***

## Import

- Import the macro set ` .mtmacset `by rightclicking on a macro panel in MapTool.

***
## Usage tips

1. Impersonate a token
2. Choose a `Roll` or a `Blind Roll` calling macro
***
- ` Alt + Down Arrow ` to open the drop-down menu.
- The calling macros are going to work as long as the Backend macro is in the same library.
- ` [r: Output] ` can be included in the end to turn into a self-sufficient rolling macro.

***
<sub><sub>Disclaimer: <a href="http://www.sjgames.com/gurps/"><b><i>GURPS</i></b></a> is a trademark of Steve Jackson Games, and its rules and art are copyrighted by Steve Jackson Games. All rights are reserved by Steve Jackson Games. This game aid is the original creation of mine and is released for free distribution, and not for resale, under the permissions granted in the <a href="http://www.sjgames.com/general/online_policy.html">Steve Jackson Games Online Policy</a>.</sub></sub>

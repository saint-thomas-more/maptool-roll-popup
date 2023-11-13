# A MapTool macro for rolling from JSON and more for GURPS by Emdis

Provides the ability to roll custom skills, attributes and listed skills. 

Skills have to be manually ripped from GCS and GCA save files (character sheets). 

Has input filtering, rudimentary tooltips for 'vs' numbers, conditional output formatting, correct critical thresholds based on the effective skill (not Telegraphic yet).

Displays colored crits; margin of success or failure.

Can be used for blind rolls through ` [gm:] ` with the included calling macro.

## Possible output:
ST⁠–10, modifiers: +2+3-2 -1+10 =>  10 vs (22): succeeded by 12  

------------------------------------------------------------------------------------------
## GCA

`.gdf` files are `.xml` under-the-hood and must be converted to `.json`.

## GCS

`.gcs` files are `.json` under-the-hood

## Ripping the skills array

- Open `.json` in Notepad.
- Find the array:
	` "skills": [...] `
- Copy the brackets and their content
- Paste into the property

## MapTool properties

- Takes individual attribute properties for the input with the regular GURPS short names.
- Input for the skills property: 
	` [ {skill-object}, {skill-object}, ... ] `
- Requires a ` SheetType ` property with "GCA" or "GCS" listed (without quotes).

------------------------------------------------------------------------------------------

## Input Filtering for the Modifier window:

- Accepts strings with addition and substraction.
- Accepts any symbols on the number row and replaces them with correct numbers and signs.
` _@=& ` becomes `-2+7 `.
- Accepts spaces.
- Accepts repeating signs and replaces them with a singular sign.
- The first number can be written without a sign. Adds "+" in this case.

- Throws an error for "+-" combinations.
- Throws an error for incorrect symbols.

## Input Filtering for the Custom SL window: 

- Must be a number
- Accepts any symbols on the number row and replaces them with correct numbers and signs.
- Filters out + and - signs.

- Throws an error if the filtered result isn't a number.

------------------------------------------------------------------------------------------

## Import:

- Import the macro set ` .mtmacset `by rightclicking on a macro panel in MapTool.

------------------------------------------------------------------------------------------

## Use tips:

- ` Alt + Down Arrow ` to open the drop-down menu.
- The calling macros are going to work as long as the Backend macro is in the same library.
- ` [r: Output] ` can be included in the end to turn into a self-sufficient rolling macro.

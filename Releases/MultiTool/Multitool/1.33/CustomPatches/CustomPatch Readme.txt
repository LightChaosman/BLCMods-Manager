// Example:
// Name=My Custom Patch
// Game=BL2
// Address=321B48
// UiElement=1
// DONE!

// Finish the CustomPatch with "DONE!" as seen above.
// To comment out a line add // at the start.
//
// WARNING & DISCLAIMER!
// DOUBLE AND TRIPLE CHECK THE PATCHES YOU "RELEASE"
// THE CREATORS OF CUSTOM PATCHES ARE RESPONSIBLE FOR THEIR PATCHES TO WORK!
// I (c0dycode) AM !NOT! RESPONSIBLE IF CUSTOM PATCHES CAUSE GAMES TO CRASH.
// MESSAGE THE CUSTOM PATCH AUTHORS AND LET THEM CHECK AGAIN!
// ALSO MAKE A !BACKUP! OF YOUR EXE!
//
// Possible parameters with example-values:
// Name=Example Patch -> The name of this patch that'll be shown as an "expander" in the tool
// Name can be empty or left out and the tool will use the Filename instead
// Also, do NOT include "Readme" in the filename.
//
// Game=BL2 -> The game this patch is for. Valid options are "BL2" and "TPS"

// Address=321B48 -> The address of the position in the exe-file that you want to patch. This needs to be in Hex-Form!

// PatchSignature=B3 F4 FF 24 63 -> (Recommended) This is what the tool will be looking for. Don't set this to the bytes you want to change and also do not include them. 
// Otherwise the tool won't find the correct position afterwards.
// Make sure that this pattern is UNIQUE or the FIRST result in the exe. Otherwise the tool reads/writes from/to the wrong location.
// Starting from version 1.21 you can also use Patterns with Wildcards in the form of "??".
// For example:
// B3 F4 ?? ?? 63
//
// With that, you can now technically include the bytes you want to patch in the signature and switch the bytes with the wildcard "??".
// For more information about the PatchSignature, feel free to hit me up on discord.
//
// Offset=5 -> This only needs to be provided if you use PatchSignature.
// With the Signature above, B3 would be Offset 0. So (0)B3 (1)F4 (2)FF (3)24 (4)63 (5)?? -> ValueToReadFrom/WriteTo
// Negative Values are also possible. 
// For example: Offset=-2 would result in:
// (-2)63 (-1)A2 (0)B3 (1)F4 (2)FF (3)24 (4)63 -> The value we read from/write to will be 63
// DO NOT include the value to read from/write to in the Signature - otherwise the tool will not find the correct address after changing the value!
//
// ValueName=ExampleValue -> The Name that will be shown next to the CheckBox/NumericUpDown-Element
// ValueRange=4 -> this is the number of bytes you want/need to read. For example the currencies are stored as 4 bytes (FFFFFF7F if set to absolute max (Big-Endian)). Be aware of Big- and Little-endian!
// For a brief explanation see this wiki-article : https://en.wikipedia.org/wiki/Endianness
// Possible values are: 1, 2 and 4 (Default is 1, in case ValueRange is not provided)
//
// UiElement=1 or 2 - Where 1 will show a CheckBox(enabled/disabled) and 2 will show a Numberselection
// MinValue=10 -> When using UiElement=2 this will be the lowest possible value.
// MaxValue=100 -> Same as MinValue except the maximum possible value.
// EnabledValue=75 -> The value to determine if/that the status is Enabled (needed if your patch only has an enabled/disabled-option and uses the CheckBox UiElement)
// DisabledValue=74 -> The value to determine if/that the patch is Disabled (needed if your patch only has an enabled/disabled-option and uses the CheckBox UiElement)
//
// Presets:
// 
// Recommended way with PatchSignature and Offset + Numeric-Value UiElement
// Name=The Recommended Way with PatchSignature and Offset
// Game=BL2
// PatchSignature=43 00 83 FE
// Offset=4
// ValueName=UVHM Level Modifier
// MinValue=1
// MaxValue=72
// UiElement=2
// DONE!
//
// Recommended way with CheckBox-UiElement instead
// Name=The Recommended Way with PatchSignature and Offset
// Game=BL2
// PatchSignature=43 00 83 FE
// Offset=4
// ValueName=UVHM Level Modifier
// DisabledValue=74
// EnabledValue=75
// UiElement=1
// DONE!
//

Name=My Custom Patch
Game=BL2
Address=321B48
ValueRange=1
ValueName=TestValue
MinValue=100
MaxValue=255
PatchSignature=0B 1A 64 73
EnabledValue=255
DisabledValue=0
UiElement=1
DONE!

Name=CustomPatch 2
Game=BL2
ValueName=Custom Patch Value
MinValue=1
MaxValue=50
Offset=4
ValueRange=1
PatchSignature=43 00 83 FE
UiElement=2
DONE!

Name=My Custom Patch TPS
Game=TPS
Address=321B48
ValueRange=0
ValueName=TestValue
MinValue=100
MaxValue=200
PatchSignature=0B 1A 64 73
UiElement=2
DONE!

Name=UVHM Level Modifier TPS
Game=TPS
ValueName=UVHM Min Level
MinValue=1
MaxValue=50
Offset=4
ValueRange=1
PatchSignature=43 00 83 FE
UiElement=2
DONE!

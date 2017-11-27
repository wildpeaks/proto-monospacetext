# MonospaceText

VRML PROTO (based on `Text`) that **displays a monospace text** using monospace font `Consolas`.

It can optionally **automatically crop the text to fit** a maximum number of characters per line,
and number of lines (using an ellipsis to indicate when content has been cropped).

It also **provides the bounding box of the resulting text**, so you can do things like adding
a border around the text, a background, or using the text like a tooltip that should
be placed one side or the other depending on the space available.

	EXTERNPROTO MonospaceText [
		exposedField  MFString  string
		exposedField  SFFloat   fontSize
		exposedField  SFInt32   maxChars
		exposedField  SFInt32   maxLines
		eventOut      SFVec2f   area
	] "proto.MonospaceText.wrl#MonospaceText"


-------------------------------------------------------------------------------

## Property `string`

**Text lines** to display (like `Text.string`).

Definition:
 - Field Type: `exposedField`
 - Data Type: `MFString`
 - Default Value: `[]`


-------------------------------------------------------------------------------

## Property `fontSize`

**Size of the text** (in VRML units), like `FontStyle.size`.

Definition:
 - Field Type: `exposedField`
 - Data Type: `SFFloat`
 - Default Value: `1`


-------------------------------------------------------------------------------

## Property `maxChars`

**Maximum number of characters per line** (`-1` means "no limit").

Definition:
 - Field Type: `exposedField`
 - Data Type: `SFInt32`
 - Default Value: `-1`

Note that it *doesn't wordwrap*, merely adds ellipsis if it's too long.


-------------------------------------------------------------------------------

## Property `maxLines`

**Maximum number of lines** (`-1` means "no limit").

Definition:
 - Field Type: `exposedField`
 - Data Type: `SFInt32`
 - Default Value: `-1`


-------------------------------------------------------------------------------

## Event `area`

**Size (width, height)** in VRML units of the displayed text.

Definition:
 - Field Type: `eventOut`
 - Data Type: `SFVec2f`

The origin of the shape is the *top-left corner*, therefore the bounding box is:
 - top: `0`
 - left: `0`
 - right: `size.x`
 - bottom: `-size.y`


-------------------------------------------------------------------------------


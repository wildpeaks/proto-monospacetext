# MonospaceText

VRML PROTO (based on `Transform`) that **displays a monospace text** using monospace font `Consolas`.

It can optionally **automatically crop the text to fit** constraints (characters per line,
number of lines, width, height), using an ellipsis to indicate when content has been cropped.

It also **provides the bounding box of the resulting text**, so you can do things like adding
a border around the text, a background, or using the text like a tooltip that should
be placed one side or the other depending on the space available.

It can also **align text horizontally & vertically**.

Also, the **font size can be modified** at runtime (therefore also animatable), unlike `FontStyle.size`.

	EXTERNPROTO MonospaceText [
		exposedField  SFNode    appearance
		exposedField  MFString  string
		exposedField  SFString  align
		exposedField  SFString  valign
		exposedField  SFFloat   fontSize
		exposedField  SFInt32   maxChars
		exposedField  SFInt32   maxLines
		exposedField  SFFloat   maxWidth
		exposedField  SFFloat   maxHeight
		eventOut      SFVec2f   bboxCenter
		eventOut      SFVec2f   bboxSize
	] "proto.MonospaceText.wrl#MonospaceText"


-------------------------------------------------------------------------------

## Property `string`

**Text lines** to display (like `Text.string`).

Definition:
 - Field Type: `exposedField`
 - Data Type: `MFString`
 - Default Value: `[]`


-------------------------------------------------------------------------------

## Property `align`

**Horizontal alignment** (`left`, `center`, or `right`).

Definition:
 - Field Type: `exposedField`
 - Data Type: `SFString`
 - Default Value: `"left"`


-------------------------------------------------------------------------------

## Property `valign`

**Vertical alignment** (`top`, `center`, or `bottom`).

Definition:
 - Field Type: `exposedField`
 - Data Type: `SFString`
 - Default Value: `"top"`


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

## Property `maxWidth`

**Maximum width** in VRML units (`-1` means "no limit").

Definition:
 - Field Type: `exposedField`
 - Data Type: `SFFloat`
 - Default Value: `-1`


-------------------------------------------------------------------------------

## Property `maxHeight`

**Maximum height** in VRML units (`-1` means "no limit").

Definition:
 - Field Type: `exposedField`
 - Data Type: `SFFloat`
 - Default Value: `-1`


-------------------------------------------------------------------------------

## Event `bboxCenter`

2D position in VRML units of the **center of the bounding box** of displayed text.

Note: this is *not the same as the anchor* (local position `[0, 0]`) which also depends on the alignment.

Definition:
 - Field Type: `eventOut`
 - Data Type: `SFVec2f`


-------------------------------------------------------------------------------

## Event `bboxSize`

**Size (width, height)** in VRML units of the displayed text.

Definition:
 - Field Type: `eventOut`
 - Data Type: `SFVec2f`

For example, with alignment top-left, the bounding box is:
 - top: `0`
 - left: `0`
 - right: `size.x`
 - bottom: `-size.y`

With aligment top-right instead, the bounding box is:
 - top: `0`
 - left: `-size.x`
 - right: `0`
 - bottom: `-size.y`


-------------------------------------------------------------------------------


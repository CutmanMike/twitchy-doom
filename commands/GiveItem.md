# GiveItem

Gives the streamer an item directly.

## Parameters
```
Actor - The actor to give to the player. (Required)
Amount - The amount of the inventory to give to the player (Default 1).
```

`Actor` must be a valid Inventory class. If successful, a message will be displayed and the player will recieve the item of the specified `amount`. Any text the user provides after this command will also be displayed in a followup message.

## Examples

```
$savetofile("C:\MyFiles\Stream\STREAM.txt","GiveItem|Actor=Medikit|$username|$dummyormsg")
```
Gives a medikit to the player.

```
$savetofile("C:\MyFiles\Stream\STREAM.txt","GiveItem|Actor=InvulnerabilitySphere,NoNotify=true|$username|$dummyormsg")
```
Gives an Invulneraiblity Sphere to the player, but doesn't display any messages.

## Screenshots

![screenshot_giveitem](../screenshots/screenshot_giveitem.png)

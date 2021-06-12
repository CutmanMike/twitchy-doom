# GiveMonsterItem

Gives a random living monster in the level an Inventory item. Only useful for custom inventory items that effect monsters.

## Parameters
```
Actor - The Inventory Actor to give the monster. (Required)
Radius - The radius near the player to try to find a random monster for the item (default is the whole map).
Monsters - The amount of monsters to give items to.
Capradius=true - Do not exceed the Radius parameter to try to find a monster.
AddName=true - Add the user's name to the monster too.
```

`Actor` must be a valid Inventory item. 

If `Radius` is specified, it will try to give the item to a monster near the player within `Radius` * 128 map units. If it can't, the radius is increased until it finds a monster (unless the capradius parameter is specified).

## Examples

```
$savetofile("C:\MyFiles\Stream\STREAM.txt","GiveMonsterItem|Actor=MyCustomItem|$username|$dummyormsg")
```
Gives a random monster "MyCustomItem".

```
$savetofile("C:\MyFiles\Stream\STREAM.txt","GiveMonsterItem|Actor=ABigBomb,radius=3,Addname=true|$username|$dummyormsg")
```
Gives a random monster within 384 map units of the player "ABigBomb", and displays the user's name above the monster.


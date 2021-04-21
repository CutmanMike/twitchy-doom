# GiveMonsterItem

Gives a random living monster in the level an Inventory item. Only useful for custom inventory items that effect monsters.

## Parameters
```
Actor - The Inventory Actor to give the monster.
```

`Actor` must be a valid Inventory item.

## Examples

```
$savetofile("C:\MyFiles\Stream\STREAM.txt","GiveMonsterItem|Actor=MyCustomItem|$username|$dummyormsg")
```
Gives a random monster "MyCustomItem".

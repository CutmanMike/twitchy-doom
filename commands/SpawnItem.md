# SpawnItem

Spawns an item in the world. The username of the person who sent the command will appear above it as long as it is in the players's line of sight.

## Parameters
```
Actor - The actor to give to the player.
```

`Actor` should be a valid Actor class. If the monster class is invalid, it will choose a random monster from the existing pool of monsters.
If the class is a RandomSpawner, it will choose a monster from the result of that RandomSpawner.

## Examples

```
$savetofile("C:\MyFiles\Stream\STREAM.txt","SpawnItem|Actor=RocketBox|$username|$dummyormsg")
```
Spawns a box of rockets near the player for them to pick up.

```
$savetofile("C:\MyFiles\Stream\STREAM.txt","GiveItem|Actor=ExplosiveBarrel,NoName=true|$username|$dummyormsg")
```
Spawns an Explosive Barrel near the player, and doesn't show the username above the actor.

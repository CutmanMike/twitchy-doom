# SpawnMonster

Spawns a monster in the world, which immediately starts hunting the player. The monster has the username of the person who sent the command will appear above it as long as it is in the players's line of sight.

## Parameters
```
Actor - The actor to spawn.
```

`Actor` should be a valid Actor class. If the monster class is invalid, it will choose a random monster from the existing pool of monsters.
If the class is a RandomSpawner, it will choose a monster from the result of that RandomSpawner.

## Examples

```
$savetofile("C:\MyFiles\Stream\STREAM.txt","SpawnMonster|Actor=Archvile|$username|$dummyormsg")
```
Spawns an Archvile near the player.

```
$savetofile("C:\MyFiles\Stream\STREAM.txt","SpawnMonster|Actor=Fatso,NoName=true|$username|$dummyormsg")
```
Spawns a Mancubus near the player without the username.

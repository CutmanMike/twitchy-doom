# SpawnOnPlayer

Spawns an Actor at the player's position. If the actor is a projectile, fire it from the player instead. Any text the user provides after this command will also be displayed in a followup message.

## Parameters
```
Actor - The actor to spawn. (Required)
```

`Actor` must be a valid Actor class. It does no collision checks so spawning solid actors this way is not recommended.

If the actor has the MISSILE flag it will be fired as if the player fired it from a weapon.

## Examples

```
$savetofile("C:\MyFiles\Stream\STREAM.txt","SpawnOnPlayer|Actor=BFGBall|$username|$dummyormsg")
```
The player will fire a BFG shot immediately.

```
$savetofile("C:\MyFiles\Stream\STREAM.txt","SpawnOnPlayer|Actor=Rocket,Delay=3|$username|$dummyormsg")
```
The player will fire a Rocket Launcher Rocket after 3 seconds.

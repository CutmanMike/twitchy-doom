# ChangeMusic

Changes the current Level's music to something else.

## Parameters
```
Song - The Inventory Actor to give the monster.
Duration - The duration the song should last in seconds.
```

`Song` should be a valid Music lump. If invalid or left blank, the game will play silence instead. This could be useful if your bot software can play music upon recieving the command.

`Duration` is how long the music should last in seconds before reverting to the level's original song. 0 will make the song last until the level ends.

## Examples

```
$savetofile("C:\MyFiles\Stream\STREAM.txt","ChangeMusic|Song=D_TENSE,Duration=30|$username|$dummyormsg")
```
Plays the "D_TENSE" song for 30 seconds.


```
$savetofile("C:\MyFiles\Stream\STREAM.txt","ChangeMusic|Duration=10|$username|$dummyormsg")
```
Turns the music off for 10 seconds.

```
$savetofile("C:\MyFiles\Stream\STREAM.txt","ChangeMusic|Song=D_COUNTD|$username|$dummyormsg")
```
Plays the "D_COUNTD" song until the level ends.

# TwitchyDoom

TwitchyDoom is a mod for GZDoom that allows Streamlabs Chatbot users to create commands that interact with GZDoom, allowing viewers to interact with their streams.

# Installation

First, you must have Streamlabs Chatbot (free) installed and have a working chatbot linked to your main Twitch account. There are many installation guides and videos on this, but here's the official one: https://cdn.streamlabs.com/chatbot/Documentation_Twitch.pdf

Next, you will need a directory on your computer with a single file in it called STREAM.txt. This file will be written to by the chatbot, and read by GZDoom. You do not need to touch this file after creating it.

Finally, your GZDoom launcher should add this folder to its list of external files (For example: ZDL has a folder+ button), along with the TwitchyDoom pk3 file. You're now ready to begin customizing the bot.

To confirm everything is set up, boot up GZDoom and walk forward. You should see a message confirming the game is working. If you don't get a message, TwitchyDoom pk3 is missing. If you get an error, your launcher is not pointing to the STREAM.txt folder correctly.

# Adding Commands

To add a command that works with TwitchyDoom, first click the Add Command button in the Streamlabs Chatbot client. You can name the command whatever you like, and alter the costs and cooldowns etc as you please. The important part is the Response field. This needs to contain the following data:

```
$savetofile("FILEPATH","COMMAND|PARAMETERS|$username|$dummyormsg")
```

`FILEPATH` must be replaced with the path to your STREAM.txt. For example, if you placed it in C:\MyFiles\Stream\, you would replace `FILEPATH` with `C:\MyFiles\Stream\STREAM.txt`

`COMMAND` is the TwitchyDoom command you wish to execute when this command is called by a viewer. See the [list of commands](#command-list) below. If you wanted to use the SpawnMonster command, you would replace `COMMAND` with `SpawnMonster`

`PARAMETERS` are any paramaters the TwitchyDoom command you've chosen supports. Using the same example of SpawnMonster, the parameters desires a monster class to spawn. If you wanted this command to spawn an Archvile, you would replace `PARAMETERS` with `Archvile`

Note: If you do not wish to declare any parameters or the command does not use them, you must still include all three |'s in the response. I.e SpawnMonster||$username|$dummyormsg

$username and $dummyormsg should be left alone. These retrieve the username and text sent by the viewer.

Here's an example of what response field should look like (assuming your STREAM.txt is in C:\MyFiles\Stream\):

```
$savetofile("C:\MyFiles\Stream\STREAM.txt","SpawnItem|Medikit|$username|$dummyormsg")
```
Which would trigger the SpawnItem TwitchyDoom command, spawning a Medikit near the player.

# Command List

### `GiveItem` item

Gives the streamer an item directly. `item` must be a valid Inventory class. If successful, a message will be displayed. Any text the user provides after this command will also be displayed.

### `SpawnItem` item

Spawns an item nearby for the streamer. `item` must be a valid Actor class (but not necessarily an Inventory item). The user's name appears above the item.

### `SpawnMonster` monster

Spawns a monster near the streamer (512 or more map units away). If left blank or invalid, a random monster is chosen instead. The monster has the user's name tag above it. If `monster` is invalid or unspecified, a random monster is chosen. A user can add `distant` to the message to try to spawn the monster further away from the streamer.

Be aware spawning an actor which then spawns a monster (such as a RandomSpawner) will not be handled properly for spawn collision, and will not have the user's name tag appear.

### `SpawnFriendlyMonster` monster

Spawns a friendly monster next to the streamer. If `monster` is invalid or unspecified, a random monster is chosen. A message is printed when this happens, and the user can add an additional chat message after the command. The monster also has the user's name tag above it along with the tag (ALLY).

### `MonsterSound`

Play a random monster's alert sound at a random volume. The user can specify which monster class to make a sound after the command.

### `RaiseDead` radius

Resurrects monsters near the streamer. `radius` is the range of the resurrection circle in map units. If unspecified, it defaults to 600 map units.

### `GiveMonsterItem` item

Gives a random living monster in the level an item. `item` must be a valid Inventory class. Only useful for custom inventory items that effect monsters.

# Creating new Command classes

TODO

<!-- EOF -->

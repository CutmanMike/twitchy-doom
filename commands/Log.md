# Log

Logs a message to the console. This is only useful for combining with other commands to provide extra in-game message to a command that may not have notifications.

The final paramter of the response is used as the message text. You can use Chatbot aliases in the text.

## Examples

```
$savetofile("C:\MyFiles\Stream\STREAM.txt","GiveMonsterItem|Actor=ABigBomb,Addname=true|$username|$dummyormsg")
$savetofile("C:\MyFiles\Stream\STREAM.txt","Log|||$username has set you up the bomb...")
```

Gives a monster "ABigBomb", then prints a message to the console.

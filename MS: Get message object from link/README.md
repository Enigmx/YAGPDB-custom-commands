# Get message object from link
Retrieve the full message object from a Discord message link. The message must belong to the same server.

# Use
Copy and paste the script into your code, then assign the message link (as a string) to the `$messageLink` variable.

The result will be stored in the `$messageObject` variable:
- Returns **false** if no link was provided  
- Returns **nil** if the message could not be found or does not exist  

You can then use this variable in the rest of your code.

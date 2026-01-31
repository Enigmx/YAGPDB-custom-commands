# Swift Mute
Immediately mute a member without requiring a reason or a duration. A powerful tool designed for fast-paced chats where quick moderation is needed.

# Use manual
**-sm [targets] [number]**: Mute the members mentioned in the message.  
- You may optionally provide a number below 100, which determines how many messages are deleted per target (up to five targets).  
- The order of arguments does not matter.

# Set up instructions
One piece of code has to be integrated as a custom command. Copy the code from the file and paste it into the response box of the custom command. Configure it as follows:
___

### Code #1
**Trigger type**: Regex  
**Trigger**: \A(-sm)\b  
**Response**: Paste code from file #1  
**Role restrictions**: Moderators only  
**Channel restrictions**: None  

⚙️ **Extra configuration**: Configure the first section of the code as follows:
- **{{$limit := 50}}**: Maximum number of messages a moderator can delete per targeted member. This is capped at 100 to prevent excessive message deletion.
- **{{$logchannel := 0}}**: Replace `0` with the channel ID where logs confirming swift mutes will be sent. It is recommended to use the same channel where moderators run commands.
- **{{$mutedrole := 0}}**: Replace `0` with the role ID of the muted role. It is not recommended to reuse the same role used for regular mutes, as this command applies its own duration and removes the role automatically.
- **{{$duration := 600}}**: Duration of the swift mute in seconds. All swift mutes will use this fixed duration.

⚙️ **Additional requirement**: The native "clear" command must be enabled in the "Moderation" section of YAGPDB’s control panel.

___
You can begin use should everything be set up until this point.

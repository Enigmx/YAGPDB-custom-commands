# Restrict
Restrict members from accessing specific channels or systems by temporarily assigning a role. Each restriction is based on a link between a channel or keyword and a role. You can run the command directly in the channel you want to restrict access to, or specify a channel or keyword manually.

By default, restrictions last 30 days, after which the role is automatically removed.

# Use manual
**-restrict [user] [days]**: Restrict the specified member from the current channel. The duration is optional and defaults to 30 days.

**-restrict [user] [channel] [days]**: Restrict the specified member from a specific channel instead of the current one. The duration is optional and defaults to 30 days.

**-restrict [user] [keyword] [days]**: Restrict the specified member from a non-channel-based system associated with a keyword.

**-restrict admin**: Open the configuration tools used to manage restriction bindings.

**-restrict admin list**: Display all configured channel and keyword bindings.

**-restrict admin add [channel] [role]**: Create a new binding between a channel and a role.  
The channel can be provided as a channel mention or channel ID, and the role as a role mention or role ID.

**-restrict admin add [keyword] [role]**: Create a new binding between a keyword and a role for non-channel-based restrictions.

**-restrict admin remove [channel]**: Remove the binding between a channel and its associated role. Once removed, members can no longer be restricted from that channel unless it is reconfigured.

**-restrict admin remove [keyword]**: Remove the binding between a keyword and its associated role.

# Set up instructions
One piece of code has to be integrated as a custom command. Copy the code from the file and paste it into the response box of the custom command. Configure it as follows:  
___

### Code #1
**Trigger type**: Command  
**Trigger**: restrict  
**Response**: Paste code from file #1  
**Role restrictions**: Moderators only  
**Channel restrictions**: None  

⚙️ **Extra configuration**: Configure the first section of the code as follows:
- **{{$staffchat := 0}}**: Replace `0` with the channel ID where restriction notifications will be sent.

___
You can begin use should everything be set up until this point.

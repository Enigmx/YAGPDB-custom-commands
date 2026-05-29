# Scam Automoderation
Automatically times out, soft bans, or bans members who are flagged as scammers by YAGPDB. Works by loading keywords and configuring whether to take action as soon as a message is flagged, or after a member crossposts into multiple channels. Useful to enable moderators of the server to contribute to a scam list without giving them access to the control panel.

# Use manual
**-antiscam**: Opens the main menu where insight about the tool is given. Click **"New"** to add a new scam entry. You will be prompted to configure:

- **Keyword**: Content to flag in messages. This also applies to file names.  
- **Action to take**:  
  - **Timeout** → Good for manual moderator review  
  - **Soft ban** → Bans, deletes messages, then unbans (useful for compromised accounts)  
  - **Ban** → Best for accounts created specifically for spam  
- **Trigger**: Choose whether to take action immediately when a message is flagged, or only if the member crossposts into multiple channels (helps reduce false positives).

**-antiscam [ID]**: View a specific scam entry. You can edit or delete it.

**-antiscam admin**: Opens the admin panel where you can:
- Configure immune roles  
- Choose who can add/edit scams  
- Set the moderation log channel  

# Set up instructions
Four pieces of code have to be integrated as custom commands. Copy the code from each file and paste it into the response box of the corresponding custom command. Configure them as follows:
___

### Code #1
**Trigger type**: Command  
**Trigger**: antiscam  
**Response**: Paste code from file #1  
**Role restrictions**: You choose  
**Channel restrictions**: You choose  

⚙️ **Extra configuration**: Configure the first section of the code as follows:
- **{{$admin := 0}}**: Replace `0` with the role ID of the admin role that can edit admin configuration.

⚙️ **Additional requirement**: The native "timeout" and "ban" commands must be enabled in the YAGPDB control panel.
___

### Code #2
**Trigger type**: Regex  
**Trigger**: \A  
**Response**: Paste code from file #2  
**Role restrictions**: None  
**Channel restrictions**: None  

⚙️ **Extra configuration**: None  

❗ **Warning**: This code is designed to run every time a message is sent. If you already have a custom command that runs on every message, you can safely append this code to the end of that command’s response.
___

### Code #3
**Trigger type**: Component  
**Trigger**: antiscam  
**Response**: Paste code from file #3  
**Role restrictions**: None  
**Channel restrictions**: None  

⚙️ **Extra configuration**: None
___

### Code #4
**Trigger type**: Modal  
**Trigger**: antiscam  
**Response**: Paste code from file #4  
**Role restrictions**: None  
**Channel restrictions**: None  

⚙️ **Extra configuration**: None
___
You can begin use should everything be set up until this point.

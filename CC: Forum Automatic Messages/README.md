# Forum Automatic Messages
Configure messages that are automatically sent whenever a new post is created in forum channels. Supports creating, editing, and removing automatic messages with embed customization.

# Use manual
**-messageforum [forum channel]**: Add, edit, or remove automatic messages for the specified forum channel.  
**-messageforum**: Shows which forum channels currently have automatic messages enabled   

🔘 **Add**: Create a new automatic message for the selected forum channel. A modal is sent with the following fields: 
- **Embed title**: Title of the embed  
- **Embed description**: Main content of the embed (supports long text)  
- **Embed color**: Must be a **color number** (integer)  
- **Embed image**: Image URL for the embed  
- **Pin message automatically?**: Choose whether the message should be pinned when sent

🔘 **Edit**: Edit the existing automatic message    

🔘 **Remove**: Delete the automatic message for that forum channel  

# Set up instructions
Four pieces of code have to be integrated as custom commands. Copy the code from each file and paste it into the response box of the corresponding custom command. Configure them as follows:
___

### Code #1
**Trigger type**: Command  
**Trigger**: messageforum  
**Response**: Paste code #1  
**Role restrictions**: Moderators only  
**Channel restrictions**: None  

⚙️ **Extra configuration**: None
___

### Code #2
**Trigger type**: Regex  
**Trigger**: \A  
**Response**: Paste code #2  
**Role restrictions**: None  
**Channel restrictions**: None  

⚙️ **Extra configuration**: None
___

### Code #3
**Trigger type**: Component  
**Trigger**: forumAutoMessage  
**Response**: Paste code #3  
**Role restrictions**: Moderators only  
**Channel restrictions**: None  

⚙️ **Extra configuration**: None
___

### Code #4
**Trigger type**: Modal  
**Trigger**: forumAutoMessage  
**Response**: Paste code #4  
**Role restrictions**: None  
**Channel restrictions**: None  

⚙️ **Extra configuration**: None
___
You can begin use should everything be set up until this point.

# Embed Creator
Create embed messages through an interactive button interface. Supports multiple embeds, embed fields, importing from message links or JSON, and exporting as YAGPDB code or JSON. You can also send the embed to a channel or edit an existing bot message.

# Use manual
**-embedcreator**: Open the import menu, where you can:
- Start from scratch (**New**)
- Load an embed using JSON (**Load JSON**)
- Load a message from a link (**Load message**)

### Control panel
- Click **Done** to open the export menu  
- Click **Edit content** to edit the message content outside embeds  
- Click **Add embed** to create a new embed  
- Click **Edit embed [number]** to edit a specific embed  

### Embed editor
- **Back**: Return to the control panel  
- **Edit title**: Modify the embed title  
- **Edit description**: Modify the embed description  
- **Edit author**: Set or edit the embed author  
- **Edit footer**: Set or edit the embed footer  
- **Edit color**: Change the embed color  
- **Edit attachment**: Add or modify the embed image/thumbnail  
- **Add field**: Add a new embed field  
- **Edit field (dropdown)**: Select a field to edit or delete  
- **Delete embed**: Delete the current embed  

### Export menu
- **Back**: Return to the control panel  
- **Send message**: Send the embed to a selected channel or thread  
- **Edit message**: Edit an existing message sent by YAGPDB, replacing it with your embed  
- **To YAGPDB**: Export the embed formatted for `complexMessage` use  
- **JSON**: Export the embed in JSON (indented format)  

# Set up instructions
Three pieces of code have to be integrated as custom commands. Copy the code from each file and paste it into the response box of the corresponding custom command. Configure them as follows:
___

### Code #1
**Trigger type**: Command  
**Trigger**: embedcreator  
**Response**: Paste code #1  
**Role restrictions**: You choose  
**Channel restrictions**: You choose  

⚙️ **Extra configuration**: None
___

### Code #2
**Trigger type**: Component  
**Trigger**: embedCreator  
**Response**: Paste code #2  
**Role restrictions**: None  
**Channel restrictions**: None  

⚙️ **Extra configuration**: None
___

### Code #3
**Trigger type**: Modal  
**Trigger**: embedCreator  
**Response**: Paste code #3  
**Role restrictions**: None  
**Channel restrictions**: None  

⚙️ **Extra configuration**: None
___
You can begin use should everything be set up until this point.

# Swift Automoderation
Quickly add temporary automoderation to a channel without having to configure it through YAGPDB’s control panel. YAGPDB automatically deletes messages that contain specific words or phrases of your choice. It can also moderate special message types such as polls, images, links, activities, forwarded messages, and stickers.

Swift Automoderation also includes a template system, allowing you to save commonly used word and phrase lists and quickly apply them whenever needed.

# Use manual
**-sam [channel] [duration] [words]**: Enable automoderation in a channel for the specified duration.  
- If no channel is provided, the current channel is used.  
- If no duration is provided, it defaults to five minutes.  
- To add multiple words or phrases at once, separate them using `/` (for example: `word1/word2/word3`).

**-sam**: Open the control panel.  
The control panel provides usage instructions, shows which channels currently have automoderation enabled, allows you to add new automoderation rules, manage templates, and access configuration options (administrator only).

### Control panel menu
🔘 **Enable**: Enable automoderation in a channel. Once clicked, a modal opens with the following options:
- **Words to automoderate**: Words and phrases to delete automatically. Separate multiple entries using `/`.
- **Special messages**: Select additional message types to automoderate. Available options are:
  - Activities  
  - Polls  
  - Stickers  
  - Links & attachments  
  - Forwarded messages  
- **Channel**: Select the channel where automoderation will be enabled. Categories can be selected by Discord, but this tool works per channel only, do not select a category. If left empty, defaults to the current channel.
- **Duration**: Select how long automoderation should remain active. If left empty, defaults to five minutes.

🔘 **Use templates**: Open the templates menu, where you can manage saved word and phrase lists.

🔘 **Configuration**: This button appears only for members with the administrator role. Opens the configuration menu for the custom command.  

### Templates menu
🔘 **Back**: Return to the main control panel.

🔘 **Add**: Create a new template. Once clicked, a modal opens with:
- **Words to automoderate**: Words and phrases to store in the template, separated using `/`.

🔘 **Load**: Load the selected template. Once clicked, a modal opens with the same options as **Enable**, but with the words field already filled using the template.

🔘 **Edit**: Edit the selected template. Once clicked, a modal opens with:
- **Words to automoderate**: Update the words and phrases stored in the template.

🔘 **Delete**: Delete the selected template.

### Configuration menu
📃 **Maximum duration**: Select the maximum duration moderators are allowed to set for automoderation.

📃 **Immune roles**: Select the roles whose messages will not be deleted by automoderation.

# Set up instructions
Four pieces of code have to be integrated as custom commands. Copy the code from each file and paste it into the response box of the corresponding custom command. Configure them as follows:
___

### Code #1
**Trigger type**: Command  
**Trigger**: sam  
**Response**: Paste code from file #1  
**Role restrictions**: Server moderators only  
**Channel restrictions**: None  

⚙️ **Extra configuration**: Configure the first section of the code as follows:
- **{{$adminRole := 0}}**: Replace `0` with the role ID of the administrator role.
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
**Trigger**: sam  
**Response**: Paste code from file #3  
**Role restrictions**: Moderators only  
**Channel restrictions**: None  

⚙️ **Extra configuration**: None
___

### Code #4
**Trigger type**: Modal  
**Trigger**: sam  
**Response**: Paste code from file #4  
**Role restrictions**: None  
**Channel restrictions**: None  

⚙️ **Extra configuration**: None
___
You can begin use should everything be set up until this point.

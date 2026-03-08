# Custom Command Indent
Automatically apply indentation to YAGPDB custom command code. This tool can format messy code, split inline template actions into separate lines, and apply customizable indentation using tabs or spaces.

You can either select a custom command by its ID from the control panel or paste code directly into the provided menu.

This tool will always attempt to split multiple brace actions on the same line into separate lines.  
Example:
`{{if condition}} {{something}} {{end}}`  
becomes  
`{{if condition}}`  
`{{something}}`  
`{{end}}`

# Use manual
**-indent [CC]**: Indent the custom command by ID. After running the command, you will configure the indentation settings (remove indentation, use TAB indentation, or use a specific number of spaces). Result will be sent as a `.txt` file.

**-indent**: Display information about the command and a button that opens a menu where you can paste code to indent instead of selecting a custom command from the control panel.

### Indent menu
🔘 **Indent**: Click this button to indent your code. A modal will appear where you can choose:

- Remove indentation
- Use TAB indentation
- Use spaces for indentation

Code pasted into the modal can be **up to 4000 characters**. After submitting, the bot will send:

- A `.txt` file containing the modified code
- The modified code in plain text if it is short enough to fit in an embed

# Set up instructions
Three pieces of code have to be integrated as custom commands. Copy the code from each file and paste it into the response box of the corresponding custom command. Configure them as follows:
___

### Code #1
**Trigger type**: Command  
**Trigger**: indent  
**Response**: Paste code from file #1  
**Role restrictions**: You choose  
**Channel restrictions**: You choose  

⚙️ **Extra configuration**: None
___

### Code #2
**Trigger type**: Component  
**Trigger**: indent  
**Response**: Paste code from file #2  
**Role restrictions**: You choose  
**Channel restrictions**: You choose  

⚙️ **Extra configuration**: None
___

### Code #3
**Trigger type**: Modal  
**Trigger**: indent  
**Response**: Paste code from file #3  
**Role restrictions**: None  
**Channel restrictions**: None  

⚙️ **Extra configuration**: None
___
You can begin use should everything be set up until this point.



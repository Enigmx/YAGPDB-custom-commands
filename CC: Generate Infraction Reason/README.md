# Generate Infraction Reason
Generate pre-made infraction reasons using customizable templates. Moderators can quickly generate formatted infractions by tagging one or multiple users and selecting a template. This tool replaces placeholders automatically and supports both single and multi-target infractions.

# Use manual
**-inf [user] [template]**: Generate the infraction reason(s) associated with the template.  
The mentioned user(s) will automatically replace the placeholder inside the template.

**-inf**: Display the list of available templates.

**-inf admin**: Open the administration panel.

### Admin panel

🔘 **Add**: Create a new template.  
When clicked, a modal opens with:
- **Template name**: The name for this infraction template. You can add aliases by splitting them using commas (name1, name2, name3).
- **Infraction #1–#4**: Pre-made infractions. Use [ID] as a placeholder for the users being targeted, and use [text1|text2] as a placeholder for multi target infractions (if one user is targeted, text1 is sent, if more users are targeted, text2 is sent).

🔘 **View**: View a template and its infractions.

### Template view

🔘 **Edit (name)**: Change the template name or its aliases.

🔘 **Add infraction**: Add a new infraction reason to this template. Maximum of 7 infractions per template.

🔘 **Edit**: Modify an existing infraction.

🔘 **Delete**: Remove an infraction.

🔘 **Delete template**: Permanently remove the template.

# Set up instructions
Three pieces of code have to be integrated as custom commands. Copy the code from each file and paste it into the response box of the corresponding custom command. Configure them as follows:
___

### Code #1
**Trigger type**: Command  
**Trigger**: inf  
**Response**: Paste code from file #1  
**Role restrictions**: Moderators only  
**Channel restrictions**: You choose  

⚙️ **Extra configuration**: None
___

### Code #2
**Trigger type**: Component  
**Trigger**: inf  
**Response**: Paste code from file #2  
**Role restrictions**: Moderators only  
**Channel restrictions**: None  

⚙️ **Extra configuration**: None
___

### Code #3
**Trigger type**: Modal  
**Trigger**: inf  
**Response**: Paste code from file #3  
**Role restrictions**: None  
**Channel restrictions**: None  

⚙️ **Extra configuration**: None
___
You can begin use should everything be set up until this point.

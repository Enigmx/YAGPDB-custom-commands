# Todo
Keep track of your pending tasks and receive periodic reminders from YAGPDB. You can configure how often reminders are sent and choose the channel where you want to receive them.

# Use manual
**-todo [task]**: Add a new to-do to your list.

**-todo**: Open your to-do list and management panel.

📃 **Mark as done**: Select from the drop-down which of your to-dos have been completed.

🔘 **Configuration**: Open the configuration menu, where you can manage reminder frequency and notification channel.

### Configuration menu
📃 **How often to remind?**: Select how often YAGPDB will tag you with your to-do list.  
Available options range from **do not remind me** up to **every 7 days**.

📃 **Channel to send reminders in**: Select the channel where you would like to receive reminder notifications.  
Discord allows selecting categories by default, do not select categories, as they are not supported.

🔘 **Configure**: Save the selected settings.

# Set up instructions
Three pieces of code have to be integrated as custom commands. Copy the code from each file and paste it into the response box of the corresponding custom command. Configure them as follows:
___

### Code #1
**Trigger type**: Command  
**Trigger**: todo  
**Response**: Paste code from file #1  
**Role restrictions**: You choose  
**Channel restrictions**: You choose  

⚙️ **Extra configuration**: None
___

### Code #2
**Trigger type**: Component  
**Trigger**: todo  
**Response**: Paste code from file #2  
**Role restrictions**: None  
**Channel restrictions**: None  

⚙️ **Extra configuration**: None
___

### Code #3
**Trigger type**: Crontab  
**Trigger**: 0 0 * * *  
**Channel**: Bot channel  
**Excluding hours**: None  
**Excluding weekdays**: None  
**Response**: Paste code from file #3  

⚙️ **Extra configuration**: None
___
You can begin use should everything be set up until this point.

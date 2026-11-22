# Birthdays Reminder
Keep a public birthday list for your server and get reminded when it's someone's birthday, so you can announce it. Members sign up with their birthday and their local time (so the bot knows when *their* day starts), and everyone ends up in a public list that updates by itself.

Every 8 hours the bot checks whose birthday is today or coming up and posts a reminder in an admin channel. If there's a birthday to announce, the admins who opted in get tagged. They announce it themselves and press a button to mark it as done.

# Use manual
**-birthdayconfig**: Open the settings panel (admins only).

**Add me**: Button of the public birthday list, available to everyone. Members use it to sign up or edit their birthday.

### Add me form
Once clicked, a modal opens where you enter your **day**, your **month**, your **current time** and whether you want your birthday to be announced.
- For **Your current time**, pick the option that matches the time on **your clock right now**. This is how the bot knows your timezone. Don't worry about daylight saving, it's only used to estimate when your day starts.
- If you don't tick the announce box, you stay on the list but nobody will announce your birthday.
- Made a mistake or changed timezone? Press **Add me** again and your old entry gets replaced.

Only members with one of the announce roles can get their birthday announced.

### Settings panel
Where admins set the system up. From here you can open the birthday list, opt in or out of being tagged in reminders, pick the channel where reminders are posted, pick the roles whose birthdays can be announced, and send the public birthday list to a channel (it takes a few seconds, since the bot sends it in 6 messages).

### Birthday list menu
Shows everyone registered, 3 months per page, with arrows to change page. From here you can also add a birthday for someone else (same form as **Add me**, plus their user ID), remove someone from the list by user ID, or go back to the settings panel.

### Reminders
Every 8 hours the bot posts a message in the reminder channel with two parts:

**Birthdays**: Birthdays happening today.
- 🟢 Will be announced.
- 🔴 Won't be announced. It tells you why: they didn't tick the announce box, they don't have the required roles, or they left the server.

**Upcoming**: Birthdays whose day starts in less than 24 hours.
- 🟡 Will need to be announced soon.
- 🔴 Won't be announced, they don't want it.

If there's at least one 🟢, the message is **red** and the admins who opted in get tagged. Once you've announced the birthday, press the check button: the message turns **green** and shows who marked it as done.

If there's nothing to announce, the message is green, nobody gets tagged and the button is disabled.

# Set up instructions
Four pieces of code have to be integrated as custom commands. Copy the code from each file and paste it into the response box of the corresponding custom command. Do them in this order, because the first one creates the database the others use. Configure them as follows:
___

### Code #1
**Trigger type**: Command  
**Trigger**: birthdayconfig  
**Response**: Paste code from file #1  
**Role restrictions**: Admin roles only  
**Channel restrictions**: None  

⚙️ **Extra configuration**: Configure the first section of the code as follows:
- **{{$admin := cslice 0}}**: Replace `0` with the role IDs of your admin roles, separated by spaces (for example `cslice 123456789012345678 987654321098765432`). These are the roles allowed to use the buttons and menus. Being a server administrator is not enough, you need one of these roles. If you change this line later, run the command again to apply it.

❗ **Warning**: The command does not check roles by itself, so set the role restrictions above to keep members out of the settings.
___

### Code #2
**Trigger type**: Component  
**Trigger**: ^birthday (regex)  
**Response**: Paste code from file #2  
**Role restrictions**: None  
**Channel restrictions**: None  

⚙️ **Extra configuration**: None
___

### Code #3
**Trigger type**: Modal  
**Trigger**: ^birthday (regex)  
**Response**: Paste code from file #3  
**Role restrictions**: None  
**Channel restrictions**: None  

⚙️ **Extra configuration**: None
___

### Code #4
**Trigger type**: Crontab  
**Trigger**: 0 */8 * * *  
**Response**: Paste code from file #4  
**Role restrictions**: None  
**Channel restrictions**: None  

⚙️ **Extra configuration**: None
___
Once everything is set up, run **-birthdayconfig** once to create the database. Then pick the reminder channel, pick the roles, press **Opt in** if you want to be tagged, and send the public list. Make sure the bot can see and write in both channels. You can now tell your members to press **Add me**.

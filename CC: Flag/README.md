# Flag
Let your members report problems to your server staff with a simple slash command. Members can report a **forum post**, a **member** or a **message**, and the report lands in a staff channel with buttons to act on it fast: delete the post or message, timeout the member, add a note, or mark the report as done.

The bot also takes care of the boring stuff: it only tags the staff members who are available at that moment (based on their timezone and the channels they chose), it groups repeated reports of the same thing into one message, and it warns staff when something gets reported by a lot of people.

# Use manual
**/flag post [reason] [post]**: Report a forum post.  
- Use it inside the post you want to report and leave **post** empty, or select the post in **post**.  
- **reason** can be up to 400 characters.

**/flag member [member] [reason]**: Report a member.  
- **reason** can be up to 500 characters.

**/flag message [link] [reason]**: Report a message.  
- To get the **link**, hold the message and press "Copy Message Link".  
- **reason** can be up to 300 characters.

Only the person who reports sees the "Sent your report" confirmation. If you report something you already reported, the bot lets you know. Members that staff restricted can't use the command.

### Reports
Reports are sent to the reports channel. Each one shows what was reported and the reason, tags the staff members who should take a look, and comes with buttons for staff:
- Mark the report as done (it turns green).
- Add a note.
- Open your personal configuration (see below).
- One extra button depending on what was reported: **Delete post**, **Timeout** (mutes the member for 10 minutes while staff decides what to do) or **Delete message**. When deleting a post, staff can write a reason, and the post creator gets tagged with it if the admins set that up.

If someone else reports the same thing within 5 days, their reason gets added to the same report instead of creating a new one. When 3 or more people report the same thing, the staff members that chose "only urgent reports" get an urgent ping.

### Personal configuration
Opened from the settings button of any report. Here each staff member chooses if they want to be tagged for reports, if it's for all reports or only urgent ones, from which channels (empty means all), and their timezones, so the bot only tags them for reports made during their day. Staff can also stop a member from using **/flag** for 30 days (or let them use it again) by typing their user ID. Admins get one extra button to open the Administrator panel.
| Zone | Region | Hours (UTC) |
| --- | --- | --- |
| 1 | West Americas | 20:00 - 04:00 |
| 2 | East Americas | 17:00 - 01:00 |
| 3 | West Europe & Africa | 13:00 - 21:00 |
| 4 | East Europe & Africa, West Asia | 10:00 - 18:00 |
| 5 | Central Asia | 07:00 - 15:00 |
| 6 | East Asia, Oceania | 04:00 - 12:00 |

### Administrator panel
Where admins set the system up. From here you can redirect the reports coming from a specific channel to another channel (threads count as their parent channel), choose where the reasons go when staff deletes a post (nowhere, the pinned post of the forum, or a specific channel/thread), and remove a staff member from the notifications, which is useful when someone steps down without opting out.

# Set up instructions
Three pieces of code have to be integrated as custom commands. Copy the code from each file and paste it into the response box of the corresponding custom command. Configure them as follows:
___

### Code #1
**Trigger type**: Slash command  
**Command trigger**: flag  
**Defer a response when triggered**: None  
**Description**: Report misconduct to server staff  
**Use subcommands**: On  
**Subcommands**: Create **3** subcommands as shown below  

- **Subcommand 1**  
**Name**: post  
**Description**: Report a forum post  

| Option | Name | Type | Description | Required | Extra |
| --- | --- | --- | --- | --- | --- |
| 1 | reason | Text | Report details: What is wrong with this post? | On | Max length: 400 |
| 2 | post | Channel | Select which post to report | Off | Allowed channel types: Public Thread |

- **Subcommand 2**  
**Name**: member  
**Description**: Report a member for misconduct  

| Option | Name | Type | Description | Required | Extra |
| --- | --- | --- | --- | --- | --- |
| 1 | member | User | Select who to report. Staff will be notified about them. | On | None |
| 2 | reason | Text | Offer insight regarding misconduct: what are they doing? | On | Max length: 500 |

- **Subcommand 3**  
**Name**: message  
**Description**: Report a message  

| Option | Name | Type | Description | Required | Extra |
| --- | --- | --- | --- | --- | --- |
| 1 | link | Text | Hold in the message, then click "Copy Message Link". | On | None |
| 2 | reason | Text | The reason for the report: what is wrong with the message? | On | Max length: 300 |

**Response**: Paste code from file #1  
**Role restrictions**: None  
**Channel restrictions**: None  

⚙️ **Extra configuration**: Configure the first section of the code as follows:
- **{{$defaultReportChannel := 0}}**: Replace `0` with the ID of the channel where reports are sent by default.
- **{{$admin := 0}}**: Replace `0` with the ID of your admin role. Members with this role get the button to open the Administrator panel.

___

### Code #2
**Trigger type**: Component  
**Trigger**: flag  
**Response**: Paste code from file #2  
**Role restrictions**: Server Staff only  
**Channel restrictions**: None  

⚙️ **Extra configuration**: None
___

### Code #3
**Trigger type**: Modal  
**Trigger**: flag  
**Response**: Paste code from file #3  
**Role restrictions**: Server Staff only  
**Channel restrictions**: None  

⚙️ **Extra configuration**: None
___
You can begin use should everything be set up until this point.

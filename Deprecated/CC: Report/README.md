# Report
Submit a report directly to the server moderators. Members can report messages by replying to them while using the command, allowing YAGPDB to include the full context of the conversation. Forum posts can also be reported using the same system.

When a report is submitted, YAGPDB forwards it to a private moderation channel along with an interactive button menu. Moderators can then delete the reported message or post, time out the reported member, or mark the report as concluded so other moderators know it has already been handled.

# Use manual
**-report [reason]**: Submit a report to the moderation team.  
- If used while replying to a message, the reported message and its context are included automatically.  
- If used on a forum post, the post itself is reported.

# Set up instructions
Four pieces of code are provided. Three must be added as custom commands, and one must be added to the Timeout DM configuration in YAGPDB’s control panel. Configure them as follows:
___

### Code #1
**Trigger type**: Command  
**Trigger**: report  
**Response**: Paste code from file #1  
**Role restrictions**: You choose  
**Channel restrictions**: You choose  

⚙️ **Extra configuration**: Configure the first section of the code as follows:
- **{{$reportChannel := 0}}**: Replace `0` with the channel or thread ID where member reports will be forwarded to.
___

### Code #2
**Trigger type**: Component  
**Trigger**: report  
**Response**: Paste code from file #2  
**Role restrictions**: None  
**Channel restrictions**: None  

⚙️ **Extra configuration**: None
___

### Code #3
**Trigger type**: Modal  
**Trigger**: report  
**Response**: Paste code from file #3  
**Role restrictions**: None  
**Channel restrictions**: None  

⚙️ **Extra configuration**: Configure the first section of the code as follows:
- **{{$forumEraseReportChannel := 0}}**: Replace `0` with the channel or thread ID where members will receive delete reasons when their forum post is removed by a moderator.  
  Replace `0` with `1` to use the pinned post of the current forum instead.  
  Leave at `0` if you do not want members to receive deletion notifications.
___

### Code #4
This code is not added as a custom command.

Navigate to:  
**Server Control Panel → Moderation → Timeout**

Paste the contents of **file #4** into the **Timeout DM** text box.

⚙️ **Extra configuration**: None
___
You can begin use should everything be set up until this point.

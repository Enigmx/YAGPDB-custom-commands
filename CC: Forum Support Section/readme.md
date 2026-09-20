# Forum Support Section
Create a support system using a forum channel. Members can open support posts through a button, select the type of inquiry, and optionally receive a configured forum tag. Staff can manage posts from the logging channel, while members can mark posts as concluded or notify staff.

Support options can be configured as either regular options, which open a tagged support post, or honeypots, which prevent a post from being created and display a custom message instead. The system also supports editing and deleting support posts, deletion notifications, optional staff reports, and automatic closing after a post is concluded.

# Use manual
**-supportconfig**: Open the support forum configuration panel.

**-concluded**: Mark the post as concluded. The post will receive the configured concluded tag and automatically close after 12 hours. Moderators and the post creator can use this command. If enabled, other members can instead notify staff that the post should be concluded.

🔘 **Select menu configuration**: Configure the options members can select when opening a support post.

🔘 **Option**: Add a regular support option. Configure its name, description, and the forum tag that will be applied when selected.

🔘 **Honeypot**: Add an option that prevents a support post from being created and displays a configured message explaining why.

🔘 **Edit option**: Modify an existing support option or honeypot.

🔘 **Support forum**: Select the forum channel where support posts will be created.

📃 **Concluded tag**: Select the forum tag used to indicate that a support post has been concluded.

📃 **Notification channel**: Select the channel or thread where members will be notified when a moderator deletes their support post and provides a reason.

📃 **Reports channel**: Select the channel or thread where requests from members to conclude another member's support post will be sent for staff review.

📃 **Logging channel**: Select the channel or thread where newly created support posts will be logged. The log includes controls for concluding, editing, and deleting the post.

🔘 **Append support button**: Add the support button to an existing YAGPDB message. The message must be accessible to YAGPDB through a valid Discord message link.

🔘 **Open post**: Members can use the support button to open a modal containing the post title, description, and configured inquiry options.

🔘 **Mark as concluded**: Mark a support post as concluded and schedule it to close after 12 hours.

🔘 **Edit**: Edit the title and description of a support post.

🔘 **Delete post**: Delete a support post and optionally provide a reason. If a notification channel is configured and a reason is provided, the post creator will be notified.

🔘 **Accept**: Staff can accept a member's request to have a support post marked as concluded.

🔘 **Decline**: Staff can decline a member's request without changing the support post.

# Set up instructions
Four pieces of code have to be integrated as separate custom commands. Copy the code from each file and paste it into the response box of the corresponding custom command. Configure them as follows:
___

### Code #1
**Trigger type**: Command  
**Trigger**: supportconfig  
**Response**: Paste code from file #1  
**Role restrictions**: Moderators only  
**Channel restrictions**: You choose  

⚙️ **Extra configuration**: None.
___

### Code #2
**Trigger type**: Command  
**Trigger**: concluded  
**Response**: Paste code from file #2  
**Role restrictions**: You choose  
**Channel restrictions**: Support forum only  

⚙️ **Extra configuration**: None.
___

### Code #3
**Trigger type**: Component  
**Trigger**: forumSupport  
**Response**: Paste code from file #3  
**Role restrictions**: None  
**Channel restrictions**: None  

⚙️ **Extra configuration**: None.
___

### Code #4
**Trigger type**: Modal  
**Trigger**: forumSupport  
**Response**: Paste code from file #4  
**Role restrictions**: None  
**Channel restrictions**: None  

⚙️ **Extra configuration**: None.
___

You can begin use should everything be set up until this point.

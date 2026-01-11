# Forum tools  
A collection of tools for managing forum posts, ranging from changing tags to automatically closing posts after a set period. It also includes a special optional feature that updates a post’s tags and closes it after 12 hours, making it ideal for support-style forums that use “resolved” tags.  

## Use manual  
**-forum**: list all available tools.  

**-forum tags**: Modify the post tags. A menu pops up which can be used by moderators. 

**-forum close**: Close the post, moderator only tool. Closed posts are moved to "older posts" and can be reopened by members.

**-forum lock**: Lock the post, moderator only tool. Only moderators can send messages in a locked post.  

**-forum closelock**: Close and lock the post at the same time, moderator only tool.  

**-forum expire [duration]**: Close and lock the post only after some time, moderator only tool. If you set a post to expire and changed your mind, you can cancel it by running **-forum expire** again.  

**-forum delete [reason]**: Delete the post, moderator only tool. You can optionally provide a reason, which is sent to a channel or thread of your choice, tagging the creator of said post to let them know. Good for transparency. If you do not provide a reason, the user is not notified at all and the post is deleted. If you somehow accidentally run this tool, you can cancel it in the ten seconds it takes YAGPDB to delete the post by running **-forum delete** again.  

**-forum [support tag]**: Add the support tag indicating the post is resolved and scheduling automatic closing and locking after 12 hours. Both moderators and post creator can use this tool, and you can optionally configure it to enable regular members to report posts that need to be marked as solved.  

🔘 **Accept**: Button in the member report which marks the post as resolved.  

🔘 **Decline**: Button in the member report which declines it and doesn't do anything, still marking the report itself as checked.  

## Set up instructions  
pieces of code have to be integrated as a custom command for each. Copy the code in each file and paste it in the response box of the corresponding custom command. Configure them as follows:  
___
### Code #1  
**Trigger type**: Command  
**Trigger**: forum  
**Response**: Paste code from file #1     
**Role restrictions**: You choose       
**Channel restrictions**: Enable in forum channels only  
  
:gear: **Extra configuration**: Configure the first section of the code as follows:  
- **{{$mod := 0}}**: Replace 0 for the role ID of the moderators who can manage forum posts.
- **{{$notificationChannel := 0}}**: Replace 0 for the channel/thread ID where members will receive their delete reasons if a moderator deletes a post. You can replace 0 for 1 instead of a channel/thread ID to use the pinned post of the current forum. Leave at 0 if you don't care about members receiving the reasons.
- **{{$supportSpecialTag := ""}}**: Fill the " "s with the name of the tag for the support forum that indicates the post has been resolved. Case sensitive. Once specified, this tool will become available for moderators and OPs use. Leave the " "s empty to keep this tool disabled.
- **{{$reportChannel := 0}}**: If the support tool is enabled, replace 0 for the channel/thread ID where member reports are going to be forwarded to, for moderators review. Leave at 0 if you do not want to enable reports from regular members.
___
You can begin use should everything be set up until this point.

# Forum Tools  
A collection of tools for managing forum posts, ranging from changing tags to automatically closing posts after a set period.  

# Use manual  
**-forum**: list all available tools.  

**-forum tags**: Modify the post tags. A menu pops up which can be used by moderators. 

**-forum close**: Close the post, moderator only tool. Closed posts are moved to "older posts" and can be reopened by members.

**-forum lock**: Lock the post, moderator only tool. Only moderators can send messages in a locked post.  

**-forum closelock**: Close and lock the post at the same time, moderator only tool.  

**-forum expire [duration]**: Close and lock the post only after some time, moderator only tool. If you set a post to expire and changed your mind, you can cancel it by running **-forum expire** again.  

**-forum delete [reason]**: Delete the post, moderator only tool. You can optionally provide a reason, which is sent to a channel or thread of your choice, tagging the creator of said post to let them know. Good for transparency. If you do not provide a reason, the user is not notified at all and the post is deleted. If you somehow accidentally run this tool, you can cancel it in the ten seconds it takes YAGPDB to delete the post by running **-forum delete** again.  

**-forum search [forum] [name]**: Search posts by name, includes a menu where you can filter by tags (or lack of them).

**-forum slowmode [seconds]**: Configure the current posts slowmode.  

**-forum pin [message link]**: Pin a message in the post.  


# Set up instructions  
Two pieces of code have to be integrated as a custom command for each. Copy the code in each file and paste it in the response box of the corresponding custom command. Configure them as follows:  
___
### Code #1  
**Trigger type**: Command  
**Trigger**: forum  
**Response**: Paste code from file #1     
**Role restrictions**: You choose       
**Channel restrictions**: Enable in forum channels only  
  
⚙️ **Extra configuration**: Configure the first section of the code as follows:  
- **{{$mod := 0}}**: Replace 0 for the role ID of the moderators who can manage forum posts.
- **{{$notificationChannel := 0}}**: Replace 0 for the channel/thread ID where members will receive their delete reasons if a moderator deletes a post. You can replace 0 for 1 instead of a channel/thread ID to use the pinned post of the current forum. Leave at 0 if you don't care about members receiving the reasons.
___
### Code #2  
**Trigger type**: Component   
**Trigger**: forumTools   
**Response**: Paste code from file #2    
**Role restrictions**: None     
**Channel restrictions**: None  
  
⚙️ **Extra configuration**: None  
___
You can begin use should everything be set up until this point.

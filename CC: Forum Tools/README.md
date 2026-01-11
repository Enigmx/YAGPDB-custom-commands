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

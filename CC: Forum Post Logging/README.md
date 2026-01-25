# Forum Post Logging
YAGPDB automatically logs every new post created in forum channels and pins the opening message inside the post itself, making it easier to find later. Each log message includes an interactive menu that allows moderators to manage the post directly — from adjusting tags to deleting or renaming the post, or marking the log as concluded for tracking or moderation purposes.

## Use manual
This tool is passive, meaning you do not use it like a traditional command. All interactions happen through the log message generated when a forum post is created.

In the log message, the following controls are available:

📃 **Post tags**: Displays a list of all tags available in the forum where the post was created. Select the tags you want to apply and click **Select** to update the post.

🔘 **Concluded**: Marks the log entry as concluded. This changes the log color from red to green, allowing moderators to visually identify resolved or handled posts.

🔘 **Erase post**: Deletes the forum post. Once clicked, a modal will appear:
- **Reason (optional)**: The reason for deleting the post. This message is sent to the member who created the post. Leave empty to delete the post silently.

🔘 **Rename**: Changes the name of the post. Once clicked, a modal will appear:
- **New name**: The new title that will be applied to the post.

## Set up instructions
Four pieces of code must be integrated as separate custom commands. Copy the code from each file and paste it into the response box of its corresponding custom command. Configure them as follows:
___

### Code #1
**Trigger type**: Regex  
**Trigger**: \A  
**Response**: Paste code from file #1  
**Role restrictions**: None  
**Channel restrictions**: At least enable in forum channels

⚙️ **Extra configuration**: Configure the first section of the code as follows:
- **{{$forumLogChannel := 0}}**: Replace 0 with the channel ID of the forum log channel.
- **{{$concludedButton := false}}**: Enable or disable the **Concluded** button. Set to `true` to enable it.
- **{{$deleteButton := true}}**: Enable or disable the **Erase post** button. Set to `false` to hide it.
- **{{$renameButton := true}}**: Enable or disable the **Rename** button. Set to `false` to hide it.

❗ **Warning**: This code is designed to run every time a message is sent. If you already have a custom command that runs on every message, you can safely append this code to the end of that command’s response.
___

### Code #2
**Trigger type**: Component  
**Trigger**: forum  
**Response**: Paste code from file #2  
**Role restrictions**: None  
**Channel restrictions**: None

⚙️ **Extra configuration**: None
___

### Code #3
**Trigger type**: Modal  
**Trigger**: forum  
**Response**: Paste code from file #3  
**Role restrictions**: None  
**Channel restrictions**: None

⚙️ **Extra configuration**:
- **{{$deleteNotificationChannel := 0}}**: Replace 0 with the channel or thread ID where members will receive delete reasons when their post is removed by a moderator. You may replace 0 with `1` to use the pinned post of the current forum instead. Leave at 0 if you do not want members to receive deletion notifications.
___
You can begin use should everything be set up until this point.

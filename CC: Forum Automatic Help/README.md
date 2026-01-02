# Forum Automatic Help
YAGPDB automatically sends a message to new forum posts when the post contains keywords you’ve configured. When a match is found, the command posts a custom response. It supports up to three automatic responses per post, along with images and optional buttons; useful for translations or extra details.
  
The command provides a simple interface where you can create, edit, and remove responses. It also includes a testing feature so you can preview how it behaves without needing to create a new post each time you change something. Members can read the information stored in the automatic responses, but they cannot add, edit, or delete responses or their settings.

## Use manual
**\-autohelp**: Open the list of custom responses, an unique ID is associated with each. If you have the moderator role you will see the "Create" button, which when clicked will prompt you to configure an automatic response. "Previous page" and "Next page" will be available if you have more than 10 custom responses.  
  
🔘 **Create**: Once clicked, a modal with four text boxes will pop up:
- **Name of this message**: An identifier which shows up in the responses list when you run "-autohelp". This does not actually show up when YAGPDB sends a response automatically upon creating a post.
- **Keywords**: The terms that will trigger the automatic response if YAGPDB finds them in the opening message or posts title. Case insensitive. Split each term using "/", for example "cannot register/cannot login/help with my profile".
- **Automatic response**: The custom message YAGPDB will send if one of the keywords is present in the posts creation.
- **Attachment (optional)**: an image or GIF which is attached as part of the custom response. It has to be an URL that embeds an image or GIF when sent in Discord as plain text.

**\-autohelp [ID]**: Open a specific custom response. [ID] is the number found besides the name of the response in the custom responses list. If you have the moderator role, you will see the "Add alternative response", "Edit response" and "Delete response".  

🔘 **Add alternative response**: You can attach buttons to each custom response that members can interact with, once clicked they see another response. Great for translations or follow-up information.  
- **Label of this response**: The name of the button. It is recommended to keep it short as it may look cluttered if you add a lot of buttons to a single response. You cannot change the name of the default response.
- **Response**: The content that will replace the original response.

🔘 **Edit response**: Modify the name, keywords, response or URL of a custom response. To edit the content of an alternative response, first select it and then click "Edit response".  

🔘 **Delete response**: Delete the custom response. You have to type "confirm" to ensure you are not accidentally deleting the response. To remove an alternative response, first select it and then click "Delete response", this will not delete the default or alternative responses.  

**\-autohelp [text]**: Test the behavior of YAGPDB through text, YAGPDB will read it and send automatic responses if keywords match, just as if a new post is being created.  

## Set up instructions
Four pieces of code have to be integrated as a custom command for each. Copy the code in each file and paste it in the response box of the corresponding custom command. Configure them as follows:  
___

### Code #1  
**Trigger type**: Regex  
**Trigger**: \A(-autohelp)\b  
**Response**: Paste code from file #1  
**Role restrictions**: You choose
**Channel restrictions**: You choose, at least enable in the support forum 
  
⚙️ **Extra configuration**: Configure the first section of the code as follows  
- **{{$adminRole := 0}}**: Replace 0 for the role ID that will enable members to add, modify or delete automatic responses.
- **{{forumChannelID := 0}}**: Replace 0 for the channel ID of the support forum.
- **{{$customMessage := "I have read your issue and thought this might be helpful:"}}**: Optionally change the message sent when YAGPDB is about to send an automatic response.
___   
### Code #2  
**Trigger type**: Regex  
**Trigger**: \A  
**Response**: Paste code from file #2  
**Role restrictions**: None  
**Channel restrictions**: At least enable in the support forum  

⚙️ **Extra configuration**: None  
❗ **Warning**: This code is designed to run every time a message is sent, if you already have a custom command running in every message sent, you can safely add this code at the end of the response.
___  
### Code #3  
**Trigger type**: Component  
**Trigger**: forumAutohelp  
**Response**: Paste code from file #3  
**Role restrictions**: None  
**Channel restrictions**: None  

⚙️ **Extra configuration**: None  
___
### Code #4  
**Trigger type**: Modal  
**Trigger**: forumAutohelp  
**Response**: Paste code from file #4  
**Role restrictions**: None  
**Channel restrictions**: None  

⚙️ **Extra configuration**: None
___  
You can begin use should everything be set up until this point.

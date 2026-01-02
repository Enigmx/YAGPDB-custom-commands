# Command  
Template that you can freely customize to produce your own embed message. You can change the title, description, message content, footer, and even attach a file.  
  
You can also optionally pair it with the crontab extra code, which sends a monthly summary of custom command usage in your server. Helpful for tracking which commands are used the least.

## Set up instructions 
One piece of code has to be integrated as a custom command. Copy the code in the file and paste it in the response box of the custom command. Configure it as follows:  
___
### Code #1    
**Trigger type**:  Starts with  
**Trigger**: You choose   
**Response**: Paste code from file #1    
**Role restrictions**: You choose     
**Channel restrictions**: You choose  
  
⚙️ **Extra configuration**:  Configure the first section of the code as follows
- **{{$cooldown := 5}}**: Command cooldown to avoid spam, in seconds. Replace 5 for your own interval of time.

On top of that, write the text of the embed within the boundaries found in the code (do not edit the boundaries themselves):  
----- CONTENT -----   
Type here the message sent when the custom command is ran. Maximum 2000 characters.  
----- CONTENT -----   
----- TITLE -----   
Type here the title of the embed sent when the custom command is ran. Maximum 250 characters.
----- TITLE -----  
----- DESCRIPTION -----  
Type here the description of the embed sent when the custom command is ran. Maximum 4000 characters.   
----- DESCRIPTION -----  
----- FOOTER -----  
Type here the bottom small text of the embed sent when the command is ran. Maximum 2000 characters.  
----- FOOTER -----  
----- ATTACHMENT -----   
Add an URL of an image or GIF and it will show in the embed sent when the custom command is ran.  
----- ATTACHMENT -----
___
You can begin use should everything be set up until this point.  
___  
### Code #2 (optional)    
**Trigger type**:  Crontab   
**Trigger**: 0 0 1 * *   
**Response**: Paste code from file #2    
**Channel**: You choose  
**Excluding hours**: None  
**Excluding weekdays**: None
  
⚙️ **Extra configuration**:  None  
___  

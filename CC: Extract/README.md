# Extract 
Send all the text of an embed message as plain text. Good for mobile users who need to copy something specific from the embed.  

# Use manual
**-extract**: Get the text from an embed. You have to reply to the message you want to get text from.  
**-extract [Number]**: Get the text from an embed. By default, the command only sends text from the first embed, if the message contains more than one embed, you have to specify which embed to extract by indicating its position, for example: -extract 2; get the text from the second embed.  

# Set up instructions  
One piece of code has to be integrated as a custom command. Copy the code in the file and paste it in the response box of the custom command. Configure it as follows:  
___  
### Code #1  
**Trigger type**: Regex   
**Trigger**: \A(-extract)\b   
**Response**: Paste code from file #1    
**Role restrictions**: You choose     
**Channel restrictions**: You choose  
  
⚙️ **Extra configuration**: None  
___
You can begin use should everything be set up until this point.

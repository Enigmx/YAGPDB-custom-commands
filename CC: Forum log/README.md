# Forum log
Creates log for new posts in forum channels. Good to centralize moderation into one channel.  

# Use  
This command is passive, does not need to be used by anyone.  

# Set up  
Create a new Custom Command, in the response box, paste the code found in "1. Regex: \A". Configure the trigger type and trigger as follows:  

![image](../ignore/forumlog1.png)  

This configures the Custom command to run in all messages. For that reason, if you already have a different Custom Command running in all messages, I recommend you paste the code in that response box. The code should work fine in the beginning of the response.  
There is a line of code which you have to edit:  

![image](../ignore/forumlog2.png)  

**{{$logChannel := 0}}** Here you configure the channel ID of the log channel. For example, {{$logChannel := 1234567890}}.  

Afterwards, create a new Custom Command. In the response box, paste the code found in "2. Component: forumEnigma". Configure the trigger type and trigger as follows:  

![image](../ignore/forumlog3.png)  

This Custom Command doesn't need further configuration. Afterwards, create a new Custom Command, in the response box, paste the code found in "3. Modal: forumEnigma". Configure the trigger type and trigger as follows:  

![image](../ignore/forumlog4.png)  

This Custom Command doesn't need further configuration.  
That's about it

# Pet
Send a randomly selected photo of someone's pet. Photos are manually added and removed by server moderators.

# Usage
**-pet** Send a random picture and a fact.  
**-pet admin** Admin tools where you can add or remove pictures  
**-pet admin database** secret command used to send the database of the bot where pictures are stored. May be useful for debugging but you shouldn't encounter an issue.

# Set up
Copy and paste the code "Regex: \A(-pet)\b" into a new custom command code box. As the title of the file implies, the trigger type must be set as "Regex", and the trigger must be set as "\A(-pet)\b". 

![pic](ignore/pet1.png)

The code has two lines of code at the beginning which can also be edited.  
{{$admin := cslice 0}} : IDs of the role which will have permission to add and remove pictures. Replace 0 with your role ID , for example, {{$admin := cslice 1234567890 0987654321}}.  
{{$channels := cslice 0}} IDs of the channels where regular members can use the command. Admins will be able to use the command anywhere else (unless you configure "Ignore the following channels" in the interface). Replace 0 with the channel IDs, for example, {{$channels := cslice 1234567890 0987654321}}.  

![pic](ignore/per2.jpg)

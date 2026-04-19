# Custom Command Triggers
Wraps the native `-dcct` command into a cleaner interface and allows you to customize who can use it. By default, YAGPDB restricts `-dcct` to administrators—this command removes that limitation.

The command helps you debug and search custom commands by showing which ones would trigger for a given input.

# Use manual
**-cct [input]**: Show which custom commands would trigger based on the provided input.

# Set up instructions
One piece of code has to be integrated as a custom command. Copy the code from the file and paste it into the response box of the custom command. Configure it as follows:
___

### Code #1
**Trigger type**: Command  
**Trigger**: cct  
**Response**: Paste code #1  
**Role restrictions**: You choose  
**Channel restrictions**: You choose  

⚙️ **Extra configuration**: None
___
You can begin use should everything be set up until this point.

# Threads Logging
Logs newly created threads in selected channels. Runs automatically every 5 minutes by checking which threads were created since the last execution.

# Use manual
This custom command is fully automatic and does not require any manual use.

# Set up instructions
One piece of code has to be integrated as a custom command. Copy the code from the file and paste it into the response box of the custom command. Configure it as follows:
___

### Code #1
**Trigger type**: Minute Interval  
**Interval**: 5  
**Channel**: Any  
**Excluding hours**: None  
**Excluding weekdays**: None  
**Response**: Paste code #1  

⚙️ **Extra configuration**: Configure the first section of the code as follows  
- `{{$threadLogChannelID := 0}}`: Replace `0` with the channel ID where thread logs will be sent  
- `{{$logFromTheseChannels := cslice 0 0 0}}`: Replace each `0` with channel IDs you want to monitor. You can add as many channels as needed  

___
You can begin use should everything be set up until this point.

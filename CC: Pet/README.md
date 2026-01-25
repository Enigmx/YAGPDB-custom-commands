# Pet
Send a randomly selected photo of someone’s pet. Images are manually added and removed by server moderators, allowing you to build and manage your own pet gallery.

## Use manual
**-pet**: Send a random pet picture along with a short fact.  

**-pet admin**: Open the admin tools menu used to manage pet pictures.  

**-pet admin add [Name] [Picture attachment]**: Add a new pet picture to the server. The image must be attached to the message.

**-pet admin remove [ID]**: Remove a pet picture from the server using its ID.

**-pet admin list [ID]**: Show a specific pet picture based on its ID.

**-pet admin list page [Page number]**: Display a paginated list of pet pictures along with their IDs.

**-pet admin database**: Send the internal database where all pet pictures are stored. This command is mainly intended for debugging purposes.

## Set up instructions
One piece of code has to be integrated as a custom command. Copy the code from the file and paste it into the response box of the custom command. Configure it as follows:  
___

### Code #1
**Trigger type**: Regex  
**Trigger**: \A(-pet)\b  
**Response**: Paste code from file #1  
**Role restrictions**: You choose  
**Channel restrictions**: You choose  

⚙️ **Extra configuration**: Configure the first section of the code as follows:
- **{{$admin := cslice 0}}**: Replace `0` with the role IDs that will have permission to add and remove pet pictures.  
  Example: `{{$admin := cslice 1234567890 0987654321}}`
- **{{$channels := cslice 0}}**: Replace `0` with the channel IDs where regular members are allowed to use the command. Administrators will be able to use the command in any channel unless additional channel restrictions are set in the interface.  
  Example: `{{$channels := cslice 1234567890 0987654321}}`

___
You can begin use should everything be set up until this point.

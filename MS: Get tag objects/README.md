# Get tag objects
Obtain full forum tag objects from the IDs provided. Useful if you have a list of IDs from `.Channel.AppliedTags` but need to retrieve information about those tags.

The tag object contains the following fields:  
`.ID`: ID of the tag  
`.Name`: Name of the tag  
`.Moderated`: Whether the tag can only be applied by moderators of the server  
`.EmojiName`: The emote of the tag, if it has one

# Use
Copy and paste the script into your code, then assign the tag IDs you want to process to the `{{$getTags}}` variable as a slice (`.Channel.AppliedTags` works if you are trying to get tag objects from the current channel).

The result will be stored in the `{{$resultTags}}` variable as a slice containing the objects of all valid tag IDs, ordered the same way the tags are ordered in the forum channel configuration. You can then use this variable in the rest of your code.

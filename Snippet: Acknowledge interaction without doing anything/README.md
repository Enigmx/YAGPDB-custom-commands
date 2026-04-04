# Acknowledge interaction without doing anything
Acknowledge a button, dropdown, or modal interaction without sending a visible response or modifying the message. This works by calling `updateMessage` while passing the message exactly as it currently is.

# Use
Copy and paste the script into your custom command. It works as-is and requires no additional configuration.

# Script  
```
{{$components := cslice}}
{{range .Message.Components}}
{{$components = $components.Append .Components}}
{{end}}
{{try}}
{{updateMessage (complexMessageEdit "content" .Message.Content "embed" .Message.Embeds "components" $components)}}
{{catch}}
{{end}}
```

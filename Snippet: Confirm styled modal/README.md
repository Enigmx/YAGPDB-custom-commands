# Confirm styled modal
Send a modal containing a required "confirm" checkbox that must be selected before submission. Useful for adding an extra safety step to dangerous actions.

# Use
Copy and paste the script into your component trigger custom command. Edit the custom ID and optionally the modal title to fit your use case.

# Script
```
{{$confirm := modalBuilder "insert_custom_id" "Confirm action" (clabel "label" "Are you sure?" "component" (ccheckboxGroup "required" true "custom_id" "a" "options" (cslice (sdict "value" "1" "label" "Confirm"))))}}
{{sendModal $confirm}}
```

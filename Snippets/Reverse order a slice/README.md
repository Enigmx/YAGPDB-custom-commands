# Reverse order a slice
Reverses the order of any slice you pass through, so the last element becomes the first, the second-to-last becomes the second, and so on. Useful for not having to use the sort function which is heavily limited.

# Use
Copy and paste the script into your code, then assign the slice you want to reverse to the `{{$toReverse}}` variable.  

The reversed slice will be stored in the `{{$reversed}}` variable, which you can then use in the rest of your code.

# Script
```
{{$toReverse := }}
{{$reversed := cslice}}
{{range (seq (mult -1 (sub (len $toReverse) 1)) 1)}}
{{$reversed = $reversed.Append (index $toReverse (mult -1 .))}}
{{end}}
{{$reversed}}
```

# String truncation
Truncate strings you pass through, adding "..." at the end if the string exceeds a specified length. Useful for fitting long text into embed or component fields.

# Use
Copy and paste the script into your code, then assign your string to the `{{$yourString}}` variable and the maximum length to `{{$stringLenLimit}}` as an integer.

The output will be stored in the `{{$truncated}}` variable, which you can then use in the rest of your code.

# Script
```
{{$stringLenLimit := }}
{{$yourString := }}
{{$truncation := ""}}
{{if ge (len $yourString) $stringLenLimit}}
{{$truncation = print (joinStr "" (slice (split $yourString "") 0 $stringLenLimit)) "..."}}
{{else}}
{{$truncation = $yourString}}
{{end}}
{{$truncation}}
```
# Compact script
```
{{$strlim := }}
{{$str := }}
{{$tr := ""}}{{if ge (len $str) $strlim}}
{{$tr = print (joinStr "" (slice (split $str "") 0 $strlim)) "..."}}{{else}}
{{$tr = $str}}{{end}}
```

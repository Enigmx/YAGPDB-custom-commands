# Slice Delete by Index

Deletes an entry from a slice by its index position.

# Use

Copy and paste the script into your code, then configure these variables:  
`{{$deleteIndex := }}`: set the index (integer) of the element you want to remove  
`{{$slice := }}`: the slice you want to modify  

# Script
```
{{$deleteIndex := }}
{{$slice := }}
{{$count := 0}}
{{$resultSlice := cslice}}
{{range $slice}}
{{if eq $count $deleteIndex}}
{{$count = add $count 1}}
{{continue}}
{{end}}
{{$resultSlice = $resultSlice.Append .}}
{{$count = add $count 1}}
{{end}}
```
# Compact script
```
{{$delIndex := }}
{{$slice := }}
{{$ccc := 0}}{{$res := cslice}}
{{range $slice}}
{{if eq $ccc $delIndex}}{{$ccc = add $ccc 1}}{{continue}}{{end}}
{{$res = $res.Append .}}{{$ccc = add $ccc 1}}
{{end}}
```

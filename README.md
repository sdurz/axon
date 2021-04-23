# axon
Access nested values for default JSON unmarshaled data

## Examples

```golang
func main() {
    value := map[string]interface{} {
        "child": map[string]interface{} {
            "intValue":     1,
            "stringValue":  "astring",
        }
    }

    var (
        o           O
        intVal      int64
        stringVal   string
    )
    o = value
    if intVal, err = o.GetInteger("child.intValue"); err == nil {
        fmt.Println(intVal)
    }
    if stringVal, err = o.GetString("child.mispelledName"); err != nil {
        fmt.Println(err)
    }    
}

```


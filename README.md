FAWS Cloud Formation Style Guide
================================

Source Code Layout
------------------
###Line Length
A line should be no more than 120 characters long.

###Indentation
* Each indentation should only have 2 spaces
* NO TABS

###White Space
* No empty lines should be present in the template.
* No white space at the end of a line.

There should be no white space between a key and the colon.

Good Example:
```json
{
  "key": "value"
}
```

Bad Example:
```json
{ "key" : "value" }
```

###Template Layout
Every Cloud Formation template should include the following sections:

* AWSTemplateFormatVersion
* Description - This must not be an empty string
* Resources

The Cloud Formation template should be in the following order:

1. AWSTemplateFormatVersion
2. Description
3. Metadata (if applicable)
4. Parameters (if applicable)
5. Mappings (if applicable)
6. Conditions (if applicable)
7. Resources
8. Outputs (if applicable)

###Lists
If the list item is not an integer or a string it must be one item per line.

Ex:
```json
{
  "foo": [
    "bar", "baz",
  ]
}
```

Or

```json
{
  "foo": [
    { "Ref": "foobar" },
    { "Ref": "bar" }
  ]
}
```

Single item lists should remain on the same line as the opening bracket.

Ex:
```json
{
  "foo": [ "bar" ]
}
```

###References
A reference should be declared on a single line unless it exceeds the max line length.

Good Ex:
```json
{ "Ref": "foobar" }
```

Bad Ex:
```json
{
  "Ref": "foobar"
}
```

###Userdata
It is acceptable to have a string and JSON object on the same line if the string is referencing
the JSON object as an argument.

Example:
```json
" --foo ", { "Ref": "bar" }
```

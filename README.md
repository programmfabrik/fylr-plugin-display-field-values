# fylr-plugin-display-field-values

This plugin provides a custom mask splitter for [fylr](https://fylr.io) that displays field values of the current object. The splitter renders a configurable markdown text inside the mask. Placeholders in the text are replaced with the values of the object.

## Configuration

Add the splitter "Display field values" in the mask editor. The splitter offers the following options.

### Output

This is the text that the splitter displays. The text is rendered as markdown. Placeholders of the form `%field-name%` are replaced with the field values of the object. Placeholders without a value are replaced with an empty string. The button "Show replacements" lists all placeholders that are available in the current mask.

### Supported placeholders:

| Placeholder | Replacement |
| --- | --- |
| `%<field>%` | The value of a simple field. |
| `%<field>:from%`,</br>`%<field>:to%` | The start and the end of a date range field. |
| `%<field>:best%` | The value of a localized text field in the best matching language. |
| `%<field>:<language>%` | The value of a localized text field in one database language, for example `%title:de-DE%`. |
| `%<field>:standard-1%` to </br>`%<field>:standard-3%` | The standard display values of a linked object. |
| `%pool.name%`,</br>`%pool.description%`,</br>`%pool.contact%` | Pool information. These placeholders are available when the object type has a pool. |
| `%object._system_object_id%`,</br>`%object._global_object_id%`,</br>`%object._uuid%`,</br>`%object._created%`,</br>`%object._last_modified%`,</br>`%object._owner%`,</br>`%object._version%` | Top level data of the object. Dates are formatted as date and time. |

Every placeholder also supports the suffix `:urlencoded`, for example `%title:urlencoded%`. This variant inserts the URL encoded value. Use it to build links in the markdown text.

### Hide text if no replacements are available

When this option is enabled, the text is hidden if none of the used placeholders has a value.

### Also render field values as markdown

By default, markdown characters in field values are escaped. When this option is enabled, the field values are rendered as markdown as well.

### PDF Creator

The plugin also adds the node "Display field values" to the PDF Creator. The node offers the same text and options as the mask splitter.

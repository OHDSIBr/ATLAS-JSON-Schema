# ATLAS-JSON-Schema
JSON Schema draft-04 for Atlas Cohort definition, Concept set and others.

Here you find a JSON Schema that validates JSON output exported by [Atlas Cohort Definitions](http://atlas-demo.ohdsi.org/#/cohortdefinitions) interface, as seen on the EXPORT/JSON tab.  
The motivation is to enable others tools, beyond OHDSI, to be able to import/export JSON cohort definitions having a way to validate it's contents.  
Atlas JSON Schemas are written agstain [JSON Schema draft-04](https://json-schema.org/specification-links.html#draft-4) specification because its large parser support on major languages and with the hope to be easy portable to more recent JSON Schema versions.

There are two kinds of the schemas:

- **multi**: Several small files referenced by "$ref" to each ohter's. You need to enable support to AJAX schema loading to use.
- **single**: One big file without JSON Editor options and descriptions suitable for just validation.

The **multi** kind of schemas have options to support [JSON Editor](https://github.com/json-editor/json-editor) project, which generates a form for data entry.  
As far as possible, it mimics the Atlas interface. This helped a lot to write and validate the schema, because it's easy to copy and paste the JSON definition output of a cohort from one tool to the other.  

Schemas are organized on branches by the version of the Atlas interface. Currently this means support for the Atlas Version 2.7.4.

So, to find the files of these release, you need to access:

- https://raw.githubusercontent.com/OHDSIBr/ATLAS-JSON-Schema/2.7.4/multi/atlas_cohort_definition.json

or:

- https://raw.githubusercontent.com/OHDSIBr/ATLAS-JSON-Schema/2.7.4/single/atlas_cohort_definition.json

To access from a Schema tool, use as schema:

    {
     "$ref": "https://raw.githubusercontent.com/OHDSIBr/ATLAS-JSON-Schema/2.7.4/multi/atlas_cohort_definition.json"
    }

and eable Ajax loading of schemas.

Or, if you want to browse the files, go to the 2.7.4 branch of this repository.

### Testing

- Load a Cohort Definition in the Atlas UI, go to the Export tab and select the JSON view. Click on the "Copy to Clipboard" button.   
- Use the [JSON-Editor Interactive Playground](https://pmk65.github.io/jedemov2/dist/demo.html?schema=EQbwOgdgBFbAJAJwKYDM4C44AsAuuAHAZwwHpTEBDAdwDoBzAS12wFcAjVo5RAYwHsIuZENoCAtqQDyACQAiAZQCSAIUSkAggBUAMhoUBaAFIKpAOQMLe2ZOMqkATLQDstACylxrADa5GpSlxvSiIAfQFsfkRcUIATNEYIZkZBWgArIkE4SABfYCA%3D%3D%3D&value=ETI%3D&code=EQehAIBUAsFNwGYHsA2KkHcCWA7A5uCrrAM7gCGATvALbk4Am5ALkpQJ4WPjXkNI4U7AHTgAmkgCu4AMb0KDBrMklWNWUgbxyAIyQA3bdx2x0GYQB0cWBOAAUAKxKwGWVpXC5V9GbCS3sRkxhACkAZQB5ADkAUVd3AEpwJxc3NmEtVUokdjsEgG4rFPi2cABecBxYDHBA%2FnNw6Li0yjt%2BGUkaWBxmYQBHSVgOMNNYGXc7C2AAYicBAFpU93nkShophIAaZJcWcgLgIA%3D&style=ETI%3D&theme=spectre&iconlib=fontawesome5&object_layout=normal&template=default&show_errors=interaction&required_by_default=0&no_additional_properties=0&display_required_only=0&remove_empty_properties=0&keep_oneof_values=0&ajax=1&ajaxCredentials=0&show_opt_in=0&disable_edit_json=0&disable_collapse=0&disable_properties=0&disable_array_add=0&disable_array_reorder=0&disable_array_delete=0&enable_array_copy=0&array_controls_top=0&disable_array_delete_all_rows=0&disable_array_delete_last_row=0&prompt_before_delete=1&lib_aceeditor=0&lib_autocomplete=0&lib_sceditor=0&lib_simplemde=0&lib_select2=0&lib_selectize=0&lib_choices=0&lib_flatpickr=0&lib_signaturepad=0&lib_mathjs=0&lib_cleavejs=0&lib_jodit=0&lib_jquery=0&lib_dompurify=1) - (Click on the link and wait at least one minute to parse and render the JSON Schema)
- Go to Output tab and paste the JSON data definition
- Click on Form tab, navigate to Concept Sets or Cohort Entry Events tabs, for example and modify anything you want
- Go to Output tab, select all (ctrl-a) and copy to clipboard (ctrl-c)
- Go back to Atlas UI, to the Export/JSon tab, select all and paste the new content from clipboard
- Click **Reload** on bottom rigth corner. This reloads the new JSon data on Atlas.
- Got to **Definition** tab, the modifications made must appear now.

Alternatively, you can use the [JSON-Editor interactive demo](https://json-editor.github.io/json-editor/?schema=N4IgJATgpgZiBcIAWAXFAHAzvA9DiAhgO4B0A5gJYpICuARjZlBAMYD2AdilFyewLY4A8gAkAIgGUAkgCEIOAIIAVADIKJAWgBSEoQDkNElkij8COAEwkA7CQAsOfjQA2KCjgIpnBTAH12SGwQKL4AJrAUHFQUnCQAVpicIAC+QA&value=N4Igwg9gdgxgpgBwC4GU5IM4gFwG0C6ANCAAoBOAlgLYCGZAnmJUnJTTqExS2wDIUYkOAsQDyAIwysAbjSQVoAdQpQAJhADuHUpQhkAIjXpZsABmIkIgw8ZymAvhcq0GXHhRr8q3bQBV6CHA4IABiFGSCIPaOIACKAK40ADYUAGYUcKpePtig/oHBYRFCMQCSsEnxGApQAErxSXAmIiAAogAeCGRN1dDZQrkg+UHYoeGRMZBJSTQIUmhI8lAA5iacENOzUsPBrbUAgiDErWQ0JDSqdjGtaihIpyzL9ByTcFAYeirLbqwewkTgN4fMjKNSaF7EGCqKgANVYvTqNBWIxAAD4ALwAVgAdKZcVEgA===&lib_switcher=&prompt_before_delete&upload=function(t,e,i){console.log(%22Upload%20handler%20required%20for%20upload%20editor%22)}&theme=bootstrap2&iconlib=fontawesome4&object_layout=normal&show_errors=interaction&ajax) with similar results.

A cohort example of [ACE inhibitor](http://atlas-demo.ohdsi.org/#/cohortdefinition/1770819), can be seen:
- with [JSON-Editor interactive demo](https://json-editor.github.io/json-editor/?schema=N4IgJATgpgZiBcIAWAXFAHAzvA9DiAhgO4B0A5gJYpICuARjZlBAMYD2AdilFyewLY4A8gAkAIgGUAkgCEIOAIIAVADIKJAWgBSEoQDkNElkij8COAEwkA7CQAsOfjQA2KCjgIpnBTAH12SGwQKL4AJrAUHFQUnCQAVpicIAC+QA&value=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&lib_switcher=&prompt_before_delete&upload=function(t,e,i){console.log(%22Upload%20handler%20required%20for%20upload%20editor%22)}&theme=bootstrap2&iconlib=fontawesome4&object_layout=normal&show_errors=interaction&ajax)

### Testing validation
To test validation can be used an online validator like:

- http://play-json-schema-validator.herokuapp.com/

On the JSON Schema side, paste:

```
{
"$ref":"https://raw.githubusercontent.com/OHDSIBr/ATLAS-JSON-Schema/2.7.4/single/atlas_cohort_definition.json"
}
```
On the JSON Instance side, paste a JSON Output exported from ATLAS and click on Validate button.

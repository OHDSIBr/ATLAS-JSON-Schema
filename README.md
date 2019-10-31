# ATLAS-JSON-Schema
JSON Schema draft-04 for Atlas Cohort definition, Concept set and others.

Here you find a JSON Schema that validates JSON output exported by [Atlas](http://atlas-demo.ohdsi.org/#/cohortdefinitions) Cohort Definitions interface, as seen on the EXPORT/JSON tab.  
The motivation is to enable others tools, beyond OHDSI, to be able to import/export JSON cohort definitions having a way to validate it's contents.  
Atlas JSON Schemas are written agstain [JSON Schema draft-04](https://json-schema.org/specification-links.html#draft-4) specification because its large parser support on major languages and with the hope to be easy portable to more recent JSON Schema versions.

There are two kinds of the schemas:
- **multi**: Several small files referenced by "$ref" to each ohter's. You need to enable support to AJAX schema loading to use.
- **single**: One big file without JSON Editor options and descriptions suitable for just validation.(In development)

The **multi** kind of schemas have options to support [JSON Editor](https://github.com/json-editor/json-editor) project, which generates a form for data entry.  
As far as possible, it mimics the Atlas interface. This helped a lot to write and validate the schema, because it's easy to copy and paste the JSON definition output of a cohort from one tool to the other.  

Schemas are organized on branches by the version of the Atlas interface. Currently this means support for the Atlas Version 2.7.4.

So, to find the files of these release, you need to access:

- https://raw.githubusercontent.com/OHDSIBr/ATLAS-JSON-Schema/2.7.4/atlas_cohort_definition.json

Or, if you want to browse the files, go to the 2.7.4 branch of this repository.




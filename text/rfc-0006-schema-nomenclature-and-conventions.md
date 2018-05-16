### Blueprints (_was: Plates or Templates_)
Blueprints are initial instructions for creating a new instances in Zesty.io stored on Github. They may include Modules, Plugins, Collections, and Contents. It may also include settings or content for head, robots text, forwarding, CORS headers, and external script or style files. References may be made to remote URLs or relative to the Github repository.

Blueprints are a quick start to an instance and are not synchronous to repositories. The Zesty.io instances references the blueprint only at the time of creation and is maintained separately afterwards. The Github integration with the template, style and javascript files is a separate repository specific to the instance. YAML files for Content Structure are not maintained on Github for an instance. Content Structure for an instance is only editable through the Zesty.io interface or through the Zesty.io API.

### Modules
Modules are a 3rd party installation for instances described [here](rfc-0003-embedded-3rd-party-interfaces.md).


### Plugins (_was: Recipes_)
Plugins are a set of instructions to build a Content Structure in Zesty.io, which includes at least one Collection that requires routing and may include multiple Collections. They may include HTML and Parsley template files, style sheets, javascript files, and media references. Modules may be installed at the initial creation from a blueprint or any time after.


### Collections  (_was: Sets, including Datasets, Pagesets, Templatesets_)
Collections describe the structure of content models by assigning sets of Fields. Each Collection functions as a table in a database where the fields are columns. Collection items are rows on the table with values able to be stored for each field.

### Fields (_was:  datatypes_ )
Fields are components of collections which define the name of a column and the type of data that can be stored. Fields may have options to validate or require types of data. Fields may be relational to Collections to store the ZUID of assigned Contents. The types of fields available are controlled by Zesty.io, a full list and description of each can be found here.


### Contents (_was: items_)
Contents are a one to one mappings of data to the Fields in a Collection. The data in the Contents must conform to the type of field described in the collection. Images must be relative URLs to the repository of the Collection or remote URLS.

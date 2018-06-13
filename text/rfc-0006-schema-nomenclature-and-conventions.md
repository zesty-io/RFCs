## Zesty.io RFC 0006 - Schema Nomenclature and Conventions

## Summary

This RFC seeks to define terms used when describing components of a Zesty.io instance, provide detail about them and how they relate to each other.

## Motivation

To ensure that there are public definitions of each of the terms used within the system, and a central place to refer to what those mean.

## Nomenclature

### Instance
An instance is a complete set of some or all of the following, that may be initiated from a Blueprint.

### Blueprints (_was: Plates or Templates_)
Blueprints are initial instructions for creating new instances in Zesty.io stored on GitHub. They may include Modules, Plugins, Collections, and Contents.  A blueprint may also include settings or content for head, robots text, forwarding, CORS headers, and external script or style files. References may be made to remote URLs or relative to the Github repository.

Blueprints are a quick start to an instance and are not synchronous to repositories. The Zesty.io instances reference the blueprint only at the time of creation and are maintained separately afterwards. The GitHub integration with the template, style and JavaScript files is a separate repository specific to the instance. YAML files for Content Structure are not maintained on GitHub for an instance. Content Structure for an instance is only editable through the Zesty.io interface or through the Zesty.io API.

### Modules
Modules are a 3rd party installation for instances described [here](rfc-0003-embedded-3rd-party-interfaces.md).

### Plugins (_was: Recipes and Garnishes_)
Plugins are a set of instructions to build a Content Structure in Zesty.io, which includes at least one Collection that requires routing and may include multiple Collections. They may include HTML and Parsley template files, style sheets, javascript files, and media references. Modules may be installed at the initial creation from a blueprint or at any time after.

### Content Models  (_was: Sets, including Datasets, Pagesets, Templatesets_)
Collections describe the structure of content models by assigning sets of Fields. Each Collection functions as a table in a database where the fields are columns. Collection items are rows on the table with values able to be stored for each field.

### Fields (_was:  datatypes_ )
Fields are components of collections which define the name of a column and the type of data that can be stored. Fields may have options to validate or require types of data. Fields may be relational to Collections to store the ZUID of assigned Contents. The types of fields available are controlled by Zesty.io, a full list and description of each can be found [here](https://developer.zesty.io/docs/content-schemas/set-fields/).

### Contents (_was: items_)
Contents are a one to one mapping of data to the Fields in a Collection. The data in the Contents must conform to the type of field described in the collection. Images must be relative URLs to the repository of the Collection or absolute remote URLS.

### Style Variables (_was: Plate Variables or LESS Variables_)
Style Variables are a collection of Fields specifically used for style atributes of an instance's front end. These variables can be referenced in custom LESS or SCSS files within the Zesty.io instance. The initial fields and values can be set with a Blueprint or Plugin and can be updated in the Config or Editor tab of the manager interface.

## Relationships between Entities

* An Instance is composed from a Blueprint
* A Blueprint may contain:
  * At least one Collection
  * 0 or more Modules
  * 0 or more Plugins
  * 0 or more Style Variables
* A Collection may contain one or more Fields
* A Plugin may contain:
  * 0 or more Collections
* A Module may contain:
  * 0 or more Collections
  
TODO Diagram, finalize this, work Content into it...


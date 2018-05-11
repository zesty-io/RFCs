# RFC 0005 - Template Schema Files (Blueprints) in YAML

## Summary

Templates (aka Blueprints) in the Zesty.io system are a collection files that determine the content schema of an instance with optional files to build out a websites that include head mapping, HTML views, JavaScript, and styling. Anyone can create a template on Github, where they loaded from Github. Templates install at instance creation, and run once. Once ran, the instance becomes independent from the template. The current format for schema in a template is written in XML, this RFC proposes a switch to [YAML](http://yaml.org/) 1.2.

## Motivation

Starting a new instance with a half baked content schema is a fast way to get going on a project, and creates a better experience. Allowing developer to control and maintain their own schema templates is important to the foundation of building fast websites and content APIs. The current format (XML) to write schemas is a bit sluggish and finicky. [YAML](http://yaml.org/) is a more human readable format that support comments, switch to this from XML will make it easier for developers to create, iterate, and share their creations. YAML over [JSON](https://www.json.org/) because of its readable format and its support for comments.

# Guide-level Explanation
[guide-level-explanation]: #guide-level-explanation

An example of a full Blueprint can see on [Github](https://github.com/zesty-io/plate-material-ui). This blueprint includes a very simple example of the schema https://raw.githubusercontent.com/zesty-io/plate-material-ui/master/plate.xml. It can be seen in the file that it conflates different concepts and assumes the instance will be launched with WWW components. Part of the switch from XML to YAML will included abstracting existing assumption into separate optional files.

**Changes**

* Head would be abstracted into a head.xml file, that is optional referenced in the Blueprint YAML
* Content that populates collection schemas will be abstracted to an optional content XML file
* Clippings will no longer have a special reference point, but be treated as any other Schema
* `Plate.xml` will be renamed to `blueprint.yaml`


## Handling Collection Schema

Previously Collection Schema, called "ingredients", was defined in groups in the XML file as so:

```
<ingredients>
		<templateset name="homepage" name_friendly="Homepage" view="homepage">
			<fields>
				<text name="title" name_friendly="Lead in Title" required="1" />
				<wysiwyg_advanced name="content" name_friendly="Intro Text" />
			</fields>

			<items>
				<item link_title="Homepage" path_part="zesty_home">
					<title><![CDATA[Material UI]]></title>
					<content><![CDATA[<p>MUI is a lightweight CSS framework that follows Google's Material Design guidelines</p>]]></content>
				</item>
			</items>
		</templateset>
	</ingredients>
```

Each Collection (ingredient) was named by its type `templateset`, `pageset`, and `dataset`. Each type had difference behaviors. Collections (ingredients) also defined their content (items) inline. If more than one item was defined or a single item with large text blocks was defined, bloat occurred in the file, making the XML file hard to follow. Abstracting content (items) into their own respective files will reduce bloat and keep the schema file to schema.

**Proposed definition in YAML**

```
Collections:
-
 label: Homepage
 name:  homepage
 view:  homepage.tpl
 type:  templateset # we need to update this naming convention
 fields:
  -
   label: Lead in title
   name: title
   type: text
   options:
    required: true
  -
   label: Intro Text
   name: content
   type: wysiwyg_advanced
```

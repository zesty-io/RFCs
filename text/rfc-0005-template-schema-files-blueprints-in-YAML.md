# RFC 0005 - Template Schema Files (Blueprints) in YAML

## Summary

Templates (aka Blueprints) in the Zesty.io system are a collection of files that determine the content schema of an instance.  Optionally, files can also be included to build out a website.  For example: head mapping, HTML views, JavaScript, and styling. Anyone can create a template on GitHub.

Templates install at instance creation, and run once. Once installed, the instance becomes independent from the template. The current format for schema in a template is written in XML, this RFC proposes a switch to [YAML](http://yaml.org/) 1.2.

## Motivation

Starting a new instance with a half baked content schema is a fast way to get going on a project, and creates a better experience. Allowing developers to control and maintain their own schema templates is important to the foundation of building fast websites and content APIs. The current format (XML) to write schemas is a bit sluggish and finicky. [YAML](http://yaml.org/) is a more human readable format that support comments.  A switch to this from XML will make it easier for developers to create, iterate, and share their creations. YAML is preferred over [JSON](https://www.json.org/) because of its readable format and support for comments.

# Guide-level Explanation
[guide-level-explanation]: #guide-level-explanation

An example of a full Blueprint can be seen on [GitHub](https://github.com/zesty-io/plate-material-ui). This Blueprint includes a very simple example of the schema https://raw.githubusercontent.com/zesty-io/plate-material-ui/master/plate.xml. It can be seen in the file that it conflates different concepts and assumes the instance will be launched with WWW components. Part of the switch from XML to YAML will included abstracting existing assumptions into separate optional files.

**Changes**

* Head would be abstracted into a `head.xhtml` file, that is optional referenced in the Blueprint YAML
* Content that populates collection schemas will be abstracted to an optional content XML file
* Clippings will no longer have a special reference point, but be treated as any other Schema
* `plate.xml` will be renamed to `blueprint.yaml`

## Handling Collection Schema

Previously a Collection Schema, called "ingredients", was defined in groups in the XML file as so:

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

Each Collection (ingredient) was named by its type `templateset`, `pageset`, and `dataset`. Each type had different behaviors. Collections (ingredients) also defined their content (items) inline. If more than one item was defined or a single item with large text blocks was defined, bloat occurred in the file, making the XML file hard to follow. Abstracting content (items) into their own respective files will reduce bloat and keep the schema file to schema.

### Proposed YAML format for Blueprints

Converted from the [Zesty.io Material UI Blueprint](https://raw.githubusercontent.com/zesty-io/plate-material-ui/master/plate.xml). The Blueprint.yaml can be seen in raw format [here](https://raw.githubusercontent.com/zesty-io/plate-material-ui/master/blueprint.yaml)

```
Name: Material UI
Meta:
 Author: Zesty.io
 Cover: cover.png
 Shield: shield.png
FileStructure:
 Head:  head.xhtml ## referenced below
 Views: views/
Collections:
-
 label: Homepage
 name:  homepage
 view:  views/homepage.tpl ### relative path
 type:  templateset ### we need to update this naming convention
 content: homepage-item.yaml ### referenced below
 fields:
  -
   name: title
   label: Lead in title
   type: text
   options:
    required: true
  -
   name: content
   label: Intro Text
   type: wysiwyg_advanced
-
 label: Clippings
 name:  clippings
 type:  dataset
 content: clippings-items.yaml
 fields:
  -
   name: site_name
   label: Site name
   type: text
   options:
    required: true
  -
   name: logo
   label: logo
   type: images
   options:
    limit: 1
  -
   name: footer_text
   label: Footer Text
   type: text
```

Notes: 

* Image paths are relative to the YAML file, or can be complete image URLs
* Field names cannot begin `_`, this is reserved
* There are a list of reserved words that cannot be used for field names

**homepage-item.yaml**

```
-
 link_title: homepage
 path_part: zesty_home
 title: Material UI
 content: |
  <p>MUI is a "lightweight" CSS framework that follows Google's Material Design guidelines</p>
```

**clippings-items.yaml**

```
-
 logo: assets/images/logo.jpg
 site_name: Material UI
 footer_text: Made with love by MUI
```

**head.xhtml**

```
<doctype>html5</doctype>
<meta http-equiv="Content-Type" content="text/html;charset=utf-8" />
<meta http-equiv="X-UA-Compatible" content="IE=edge"/>
<meta name="viewport" content="width=device-width, initial-scale=1"/>

<script src="//cdn.muicss.com/mui-0.2.3/js/mui.min.js"></script>
<script src="//code.jquery.com/jquery-2.1.4.min.js"></script>
<script src="//cdn.muicss.com/mui-0.2.3/webcomponents/mui-webcomponents.js"></script>

<!-- load icon font -->
<link href="//cdnjs.cloudflare.com/ajax/libs/font-awesome/4.2.0/css/font-awesome.min.css" rel="stylesheet" type="text/css" />

<!-- fonts -->
<link href="//fonts.googleapis.com/css?family=Roboto:300,400,400italic,500,700" rel="stylesheet" type="text/css" />

```

**views/homepage.tpl**

```
<h1>{{page.title}}</h1>
<hr>
<p>{{page.content}}</p>
```

### How the YAML file is Used

The file is read by javascript, and iterated through and executed against the instance-api.

# Testing

You can test your YAML files through an input here https://zesty-io.github.io/schema-reader-ui/

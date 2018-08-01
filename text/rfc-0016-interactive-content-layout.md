# RFC 0016 - Interactive Content Layout (ICL)

## Summary

An interactive drag and drop interface that enables a non-technical user to layout content in a grid-like manner. The interface would produce a set of Responsive HTML/CSS instructions which a web developer could use to plug into the body of their template.

## Motivation

An interactive feature to give control to marketers is important to further separate marketers from the needs of a developer. This request has come up in multiple conversations with prospective users of the platform. The availability of a feature like this greatly reduces the need for developer interaction, and overuse of WYSIWYG editors.

## Requirements

* New resource endpoints on the Instances API.
	* /content/models/layouts CRUD
	* /content/models/items/layouts CRUD
* New parsley call {{page.icl}} that returns the CSS/HTML
* Picking a lightweight CSS responsive grid system
* Drag n Drop Interface in Manager UI

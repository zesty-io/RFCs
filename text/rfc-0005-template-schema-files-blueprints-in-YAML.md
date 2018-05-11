# RFC 0004 - Template Schema Files (Blueprints) in YAML

## Summary

Templates (aka Plates or Blueprints) in the Zesty.io system are a collection files that determine the content schema of an instance with optional files to build out a websites that include head mapping, HTML views, JavaScript, and styling. Anyone can create a template on Github, where they loaded from Github. Templates install at instance creation, and run once. Once ran, the instance becomes independent from the template. The current format for schema in a template is written in XML, this RFC proposes a switch to [YAML](http://yaml.org/) 1.2.

## Motivation

Starting a new instance with a half baked content schema is a fast way to get going on a project, and creates a better experience. Allowing developer to control and maintain their own schema templates is important to the foundation of building fast websites and content APIs. The current format (XML) to write schemas is a bit sluggish and finicky. [YAML](http://yaml.org/) is a more human readable format that support comments, switch to this from XML will make it easier for developers to create, iterate, and share their creations. YAML over JSON because of its readable format and its support for comments.

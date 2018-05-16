# RFC 0008 - Blueprint Schema in YAML

## Overview
This is a description of the structure and syntax used in the YAML file for creating the initial Content Structure with a Zesty.io Instance build. The Blueprint YAML file defines the instance settings, the location of relavent files, which modules and plugins to include, and the initial Collections. 

## General Structure 
The outline for the Blueprint YAML is:
* name: Your Blueprint Name
* type: Can be blueprint, module, plugin, collection, or contents
* version: Your Version Number
* meta:
  * cover: Relative path to image or remote image URL
  * shield: Relative path to image or remote image URL
* settings: Initial site settings can be overridden here. All initial settings have a default value if not set in the Blueprint YAML.
* files:
  * head:  Relative path to your head.xhtml file
  * styleVariables: Relative path to your style-variables.yaml file
  * views: Relative path to your folder with all the TPL files
  * javascript: Relative path to your folder with all the javascript files
  * styles: Relative path to your folder with all the style files
* modules:
  * url: Direct URL to the Module Github Repo to Include (Recommend linking to specific version)
  * required: Must specify true or false, no default if omitted so will fail schema check
* plugins:
  * url: Direct URL to the Plugin Github Repo to Include (Recommend linking to specific version)
  * required: Must specify true or false, no default if omitted so will fail schema check
* collections: 
  * label: Content Display Name
  * name:  Parsley Reference Name
  * view:  Relative path to related view TPL
  * type:  Page, Page Group or Dataset
  * content: Relative Path to related Contents YAML
  * fields: See Fields YAML RFC
   
## Initial Settings and Default Values
* general:
  * robots_on: true
  * site_protocol: http
  * always_redirect_to_https: false
  * preferred_domain_prefix: false
  * show_in_title: true
* developer:
  * ajax_cors_allow_any_origin: false
  * parsley_debugger: false
  * tips: true
  * basic_content_api_enabled: false
  * basic_content_api_cors_allow_any_origin: false
  * auto_include_js_in_head: true 
* contact:
  * sending_email: NULL
  * recipients: NULL # sends
  * reply_email: NULL

# RFC 0018 - Single Page Head Tags (Meta Tags)

## Summary

A way to create and manage custom head tags for specific webpages that resolve on Zesty.io Site Engine.

## Motivation

Currently we offer an interface to create and edit head/meta tags that load globally on every page across the whole website. Some users are requesting specific meta tags that should only load on specific pages. Because this is not the case, it creates a poor user experience when sharing pages.

## Requirements

* New resource endpoints on the Instances API.
	* /content/models/headtags CRUD (for all content routes that resolve from a specific model)
	* /content/models/items/headtags CRUD (for individual specific routes)
* Site Engine update to check logic for custom Header Meta Tags on the model or the individual item
* An interface in Manager UI to manage these routes

## Details

Global WWW, Content Models, and Content Items will all have head tags.

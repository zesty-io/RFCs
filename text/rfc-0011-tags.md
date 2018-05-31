# RFC 0011 - Tagging in Zesty.io

## Summary

This is an RFC to propose the addition of the ability to tag instances in the Zesty.io content management platform for the purpose of creating a better management and organization experience for users owning or working with many sites in a single Zesty.io account.

## Motivation

Reasons for adding tagging:

* To allow instances to be identified by custom words that are meaningful to individuals / organizations
* Allows individuals and organizations to manage their workflow more effectively
* To permit filtering by instances that are in common states (e.g. "work in progress" and "bootstrap")
* TODO other reasons...

## Detailed Design

TODO implementation detail, rough ideas:

* Tags to be stored as metadata against instances
* Users should be able to create / update / delete tags
* Users should be able to filter instance list / card views by tag or tags (what about complex scenarios e.g. "bootstrap" and "spanish" and not "awaiting customer input")
* Changes needed in Accounts UI
* Changes needed in Manager?
* Changes needed in Accounts API

## Alternatives

Alternatives to the suggested approach could include:

* TODO

## Exising Examples

* [GitHub Topics](https://blog.github.com/2017-01-31-introducing-topics/)

## Unresolved Questions

TODO - what outstanding questions are there about this feature?

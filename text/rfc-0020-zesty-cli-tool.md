# RFC 0020 - Zesty CLI Tool

## Summary

A tool to quickly allocate .html, .css and .js files into their appropriate panes within the Content Manager

## Motivation

Getting a new site or template into Zesty will be more efficiently served with tool to quickly allocate assets into their appropriate destinations without copy/paste

# Guide-level explanation
[guide-level-explanation]: #guide-level-explanation


# Reference-level explanation
[reference-level-explanation]: #reference-level-explanation

Here are some ways the tool could work:

`zesty-cli push-css LOCAL_DIR INSTANCE_ZUID`

`zesty-cli push-js LOCAL_DIR INSTANCE_ZUID`

`zesty-cli push-html LOCAL_DIR INSTANCE_ZUID`

`zesty-cli push-all LOCAL_DIR INSTANCE_ZUID`

Other considerations

- Still have to determine the load order of scripts and stylesheets within the Zesty Editor

# Drawbacks
[drawbacks]: #drawbacks

There are syncing and overwrite considerations which may or may not be relevant for a first-time deploy

# Rationale and alternatives
[alternatives]: #alternatives

- This is potentially accomplished within the IDE plugins

# Prior art
[prior-art]: #prior-art

# Unresolved questions
[unresolved]: #unresolved-questions

- What should the load order be?
- What should the overwrite considerations be?
- Should we (could we) include media assets as well? (images, video, font files)

community# RFC 0018 - IDE Plugin

## Summary

Create a plugin for popular IDEs for synchronizes file creation and edit to and from the remote instance.

## Motivation

A big part of Zesty.io is editing views for both browser display and custom endpoints. Being that Zesty.io is 100% SaaS, it means all editing happens through the browser. Currently we use CodeMirror in the browser, but that experience lacks compared to the community plugin rich ATOM, VSCode, and Sublime Editors.

The goal is to allow developers to work in their favorite IDE while working on Zesty.io views.

## Considerations

We had a short polling between Atom and VS Code: https://zestyiodevs.slack.com/archives/C1RRP2B0A/p1536940558000100

VSCode won by a few votes


## Description of Behavior

Most IDE editors haver a tray that is visually located below the code editing area. The tray is where the Zesty.io integration will live.

From the tray, a view will require the input of a session code (used before we deploy developer tokens) and an instance ZUID. These two bit of information will allow the API calls from the user, and will be required.

### Writing Files

From there, files will be expects to share a filename with the view on the remote Zesty.io instance. On save, the file will be written to the instances api, since the instances api needs a zuid to write, on save the plugin will hit the `instances/web/views/` endpoint, and search a matching filename and zuid, then write to the `instances/web/view/:zuid` endpoint.

To speed up this action, we should consider storing a file name tree map to zesty.json to reference on save or creation.

By default, files saves will write the file to the Zesty.io instance's "dev" branch. Currently Zesty.io only supports a dev and live branch. You can only write to dev. This is a place holder for branches.

### Folder Structure

The folder structure on a Zesty.io instance is flat (for now, we are introducing a folder system soon), but that will not matter to the local folder structure with the exception of this rule: Styles sheets are stored under the top level `css/` directory, javascript under `js/`, and all other views and snippets under `views/`. File extensions do determine behavior on the API side, reference API docs for that.

The local folder structure under `css/`, `js/`, and `views/` won't matter because on file save the file will reference the remote views endpoint to match the filename to the zuid.

This will be the first MVP of the code editor.

Files to help determine behavior

* zesty.json *(a cached tree structure of filenames and types to zuids)*
* .zestyignore *possible file to ignore say distribution files or what not?*

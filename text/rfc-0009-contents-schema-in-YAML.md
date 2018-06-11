# RFC 0009 - Contents Schema in YAML

## Overview
This is a description of the structure and syntax used in the YAML file for creating the initial data for a Zesty.io Instance build. The Contents YAML file provides the initial content entries to populate the Fields and Content Structure described in the Blueprint YAML.

## General Structure
The outline for the Content YAML is:
* type: content
  * options:
    * path-part: path-part-for-content **OR** path-full: must begin with a `/` and will be prepended by the domain.
    * parent: your-contents-parent
    * link-title: link-title (i.e. the link title that will show in your navigation. `path-part` or `path-full` do not need to match `link-title`)
* content:
  -
  enter-your-content-here. Each collection of entries is separated into its own sequence.
  -
  For example this would be another collection.

##  Path-Part or Path-Full
### Example 1: path-part
`path-part` will prepend the path that you define with the defined parent. so the path will be: `my-domain.com/a-page/a`
                       ----------
                       | A page |
                       ----------
                            |
                            |
        ---------------------------------------------
        |            |             |                |
  ------------  ------------  ------------    ------------
  |    A     |  |    B    |   |    C    |     |     D    |
  ------------  ------------  ------------    ------------  

  * type: content
    * options:
      * path-part: A
      * parent: a-page
      * link-title: A

### Example 2: path-full
`path-full` will prepend the path that you define with the parent(if defined) and domain. The path in this example will be: `my-domain.com/A/A1` If a parent was not define the path would be: `my-domain.com/A1`
                              ---------
                              | A page |
                              ----------
                                  |
                                  |
              ---------------------------------------------
              |            |             |                |
        ------------  ------------  ------------    ------------
        |    A     |  |    B    |   |    C    |     |     D    |
        ------------  ------------  ------------    ------------  
              |
          ---------
          |  A1   |
          ---------

  * type: content
    * options:
      * path-full: /A1
      * parent: A
      * link-title: A1

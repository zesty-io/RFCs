# RFC 0007 - Field Schema in YAML

## Reserved Field Names

Field names may not begin with `_`.  Additionally, the following are reserved field names that may not be used:

|                         |                                   |                      |                                   |
|-------------------------|-----------------------------------|----------------------|-----------------------------------|
| `_meta_description`     | `_meta_title`                     | `_meta_keywords`     | `_meta_link_text`                 |
| `_created_by_user_zuid` | `_created_at`                     | `_item_zuid`         | `_version_zuid`                   |
| `_lang`                 | `_version`                        | `canonical_tag_mode` | `canonical_query_param_whitelist` | 
| `created_at`            | `created_by_user_zuid`            | `deleted_at`         | `garnish`                         | 
| `icon`                  | `land_id`                         | `last_edited_id`     | `last_updated`                    |
| `listed`                | `master_zuid`                     | `parent_zuid`        | `path_full`                       |
| `path_part`             | `recipe`                          | `seo_link_title`     | `seo_meta_description`            |
| `seo_meta_keywords`     | `set_name`                        | `set_zuid`           | `show_add_new_set_item`           |
| `sitemap_priority`      | `type`                            | `updated_at`         | `updated_by_user_zuid`            |
| `zid`                   | `zuid`                            |                      |                                   |

## Field Types

Available field types are as follows.  Existing documentation regardint fields can be [found here](https://developer.zesty.io/docs/content-schemas/set-fields/).

### article_writer

* Description: TODO

### brandisty

* Description: TODO

### color

* Description: TODO
* Limit: 150 characters
* Example: `blue` or `#0000ff`

### `currency`

* Description: TODO
* Limit: 150 characters, 2 decimal points
* Example: `$15.99`

### `date`

* Description: TODO
* Format: `YYYY-MM-DD`
* Example: `2018-05-16` 

### `datetime`

* Description: TODO
* Format: `YYYY-MM-DD HH-MM-SS` (24 hour clock)
* Example: `2018-05-16 14:54:06`

### `dropdown`

* Description: TODO

### `files`

* Description: TODO

### `fontawesome`

* Description: TODO

### `images`

* Description: TODO

### `internal_link`

* Description: TODO

### `link`

* Description: TODO
* Limit: 150 characters
* Example: `https://zesty.io`

### `markdown`

* Description: TODO

### `number`

* Description: TODO
* Limit: 150 characters, no comma or currency symbol allows.  Decimal places optional
* Example: `1`, `1.23`

### `one_to_many`

* Description: TODO

### `one_to_one`

* Description: TODO

### `sort`

* Description: TODO

### `text`

* Description: TODO
* Limit: 150 characters
* Example `Hello, World!`

### `wysiwyg_advanced`

* Description: TODO

### `yes_no`

* Description: TODO

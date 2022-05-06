# _common

The `_common` directory includes files that are common to several pages across the site, and which do not need to be included in the rendered site themselves.

Because the directory is prepended by an underscore, it will be ignored when rendering the site, so these files will not be included in the `_site` directory of the rendered site. This works for these files because their contents will be injected into the files that reference them.

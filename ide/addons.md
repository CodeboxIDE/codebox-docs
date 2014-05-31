---
layout: default
title: Addons
section: ide/addons
---

# Managing addons

### Define addons directories:

Codebox has three directories for managing addons:

* A directory for storing defaults addons: `WORKSPACE_ADDONS_DEFAULTS_DIR` (don't change if you don't know what you're doing)
* A directory for storing all the installed addons: `WORKSPACE_ADDONS_DIR`
* A directory for storing temporary data: `WORKSPACE_ADDONS_TEMP_DIR`

`WORKSPACE_ADDONS_DEFAULTS_DIR` can be accessible in read-only mode but `WORKSPACE_ADDONS_DIR` needs write permissions.

By default, Codebox will store the new addons into `.addons`.
Caution: If the directory doesn't exist, Codebox will recursively create it.

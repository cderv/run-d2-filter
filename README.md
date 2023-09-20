# Extension For Quarto to run D2-filter

***THIS IS NOW ARCHIVE AND YOU SHOULD USE https://github.com/data-intuitive/quarto-d2 INSTEAD***

This extension is simply a Lua wrapper to run JSON filter `d2-filter` which allow to use **d2** diagrams in Pandoc

- D2: https://d2lang.com/
- d2-filter: https://github.com/ram02z/d2-filter

> **This is a prototype as simple wrapper around an existing filter and not an extension running `d2` directly**
>
> Future and extended work would be to provide a Lua version of `d2-filter`

## Installing

This extension expects **d2** and **d2-filter** programs to be on PATH. 

### Installing d2

Follow step at <https://d2lang.com/tour/install> to run install script. 

For Windows user, **d2** is available through Scoop (https://scoop.sh/)

```powershell
scoop install d2
```

### Installing d2-filter

Follow step at <https://github.com/ram02z/d2-filter>. `d2-filter` is available as an NPM package and requires Node.js

### Installing this extension

```bash
quarto add cderv/run-d2-filter
```
This will install the extension under the `_extensions` subdirectory.
If you're using version control, you will want to check in this directory.

## Using

> Reminder: To use this filter, **d2** and **d2-filter** are required to be found on PATH

Add to your YAML header or config YAML the filter

```yaml
filters:
  - run-d2-filter
```

This Lua filter is only a wrapper that calls `pandoc.utils.run_json()` on the `d2-filter` JSON filter.

## Example

Here is the source code for a minimal example: [example.qmd](example.qmd).


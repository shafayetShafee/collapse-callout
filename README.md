# Collapse-callout

A very simple filter extension For Quarto that allows to set the Callout Blocks collapsibility from document yaml header. By specifying `true` or `false`, you can make the Callout blocks collapsed or keep them expanded by default.

And Note that, callout blocks collapsibility works only for `html` format.

## Installing

To install this extension in your current directory (or into the Quarto project that you're currently working in), use the following command:

``` bash
quarto add shafayetShafee/collapse-callout
```

This will install the extension under the `_extensions` subdirectory. If you're using version control, you will want to check in this directory.

## Using

### Collapsing all types of callout blocks

Add the following to the yaml header of your document to make all of the callout blocks in your document collapsed by default.

```
title: "Collapse-callout Example"
filters:
  - collapse-callout
collapse-callout:
  all: true
format: html
---
```

here `all` can be either `true` or `false`.

### Collapsing specific types of callout blocks

You can also set the collapsibility for specfic types of callout blocks in the following way,

```
---
title: "Collapse-callout Example"
filters:
  - collapse-callout
collapse-callout:
  tip: true
  note: false
  warning: false
  important: false
  caution: true
---
```

here `tip` and `caution` types Callout blocks will be in collapsed form and rest of the callout blocks will be in expanded form by default. 

If you do not want to make a specfic type of Callout Blocks collapsible, simply do not include its name under `collapse-callout` in the yaml header. 

Therefore, the following will not do anything for `important` type Callout blocks,

```
---
title: "Collapse-callout Example"
filters:
  - collapse-callout
collapse-callout:
  tip: true
  note: false
  warning: false
  caution: true
---
```

***Note that, if you set `collapse=false` or `collapse=true` manually in the document source file (that is in the qmd file), this filter will not overwrite that.***

## Example

Here is the source code for 

- a minimal example where all callout blocks are collapsed: [example_all.qmd](example_all.qmd).

- a minimal example where some specfic callout blocks are collapsed: [example_specific.qmd](example_specific.qmd).

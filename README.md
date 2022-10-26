# collapse-callout

A very simple filter extension For Quarto that provides options from document yaml header (i.e. global options) to make the [`Callout Blocks`](https://quarto.org/docs/authoring/callouts.html) in your document [`collapsible`](https://quarto.org/docs/authoring/callouts.html#collapse). By specifying `true` or `false`, you can either make the Callout Blocks collapsed or keep them expanded by default.

And Note that, Callout blocks collapsibility works only for `html` format.

## Installing

``` bash
quarto install extension shafayetShafee/collapse-callout
```

This will install the extension under the `_extensions` subdirectory. If you're using version control, you will want to check in this directory.

## Using

### Collapsing all types of callout blocks

Add the following to yaml header of your document to make all of the callout blocks in your document collapsed by default.

    title: "Collapse-callout Example"
    filters:
      - collapse-callout
    collapse-callout:
      all: true
    format: html
    ---

here `all` can be either `true` or `false`.

### Collapsing specific types of callout blocks

You can also set the collapsibility for specfic types of callout blocks in the following way,

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

here `tip` and `caution` types Callout blocks will be in collapsed form and rest of the callout blocks will be in expanded form by default.

If you do not want to make a specfic type of Callout Blocks collapsible, simply do not include its name under `collapse-callout` in the yaml header.

Therefore, the following will not do anything for `important` type Callout blocks,

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

A few things to note,

-   If you use `all` option, specfic options (i.e. `tip`, `important` etc.) will not be used.

-   **if you set `collapse=false` or `collapse=true` manually in the callout divs in the document source file (that is in the qmd file), this filter will not overwrite that.**

## Example

| **Source Files** | **Rendered HTML Output** |
|:---:|:---:|
| A minimal example where all `Callout Blocks` are collapsible and collapsed  (with `all: true`) [example_all_true.qmd](example_all_true.qmd) | [Rendered Output](https://shafayetshafee.github.io/collapse-callout/example_all_true.html) |
| A minimal example where all `Callout Blocks` are collapsible and expanded  (with `all: false`) [example_all_false.qmd](example_all_false.qmd) | [Rendered Output](https://shafayetshafee.github.io/collapse-callout/example_all_false.html) |
| A minimal example where some specific types of `Callout Blocks` are collapsible and  collapsed or expanded [example_specific.qmd](example_specific.qmd) | [Rendered Output](https://shafayetshafee.github.io/collapse-callout/example_specific.html) |
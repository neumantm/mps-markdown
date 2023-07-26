# mps-markdown

Implementation of the markdown language for JetBrains MPS

## Goal

- Represent markdown as close as possible to the [commonmark][] specification
- The texgen shall generate markdown in a way, such that the nodes of the model are transformed into text conforming to the definition of the corresponding (to the node) syntax element according to the [commonmark][] specification
- The editor shall be convenient and intuitive to use
- Eventually as much of the [commonmark][] specification as possible shall be implemented
    - Ideally any [commonmark][] document shall be able to be produced from this language via the textgen
    - However, the usability of the editor is more important than completeness in regards to the specification
- The language shall be extensible wherever possible
- Any extensions beyond the [commonmark][] specification not shall be implemented in this language but rather as language extensions

[commonmark]: https://commonmark.org/

## State

This repository/language is in a WIP / development state.
Nothing is stable, everything may change.

## Usage

### Editor

Most parts of the editor should be inuitive and self-explanatory.
Here are some notes on the less obvious parts.

#### Lists

- To quickly indent a list item, press `Tab` with the cursor on the list marker (the `-`)
    - Only possible if there is a list item on the current indentation somehwere earlier (above) in the list
- To quickly unindent a list item, press `Tab` with the cursor on the list marker (the `-`)
    - Only possible if the list item is indented
- To add a new line within a list item do the `INSERT BEFORE` action (usually Shift-Enter)
- To create a new normal line after a list press enter on an empty list item

## Development Notes

### Re-Generating TextGen

- Right-click the language and select Generate TextGen
- In `MdFile_TextGen` set extension to `.md` and path query to `node.path.isEmpty ? null : node.path;`
- In `MdLine_TextGen` and `MdLink_textGen` remove section creating whitespace between elements
- In `MdBulletListItem` add `boolean first = true;` before the loop and
  ```
  if (first) {
    first = false;
  } else {
    append indent;
  }
  ```
  before the `append ${elem};`

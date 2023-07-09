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

## Development Notes

### Re-Generating TextGen

- Right-click the language and select Generate TextGen
- In `Markdownfile_TextGen` set extension to `.md`
- In `MdTextLine_TextGen` remove section creating whitespace between elements

# mps-markdown

Implementation of the markdown language for JetBrains MPS

## State

This repository/language is in a WIP / development state.
Nothing is stable, everything may change.

## Development Notes

### Re-Generating TextGen

- Right-click the language and select Generate TextGen
- In `Markdownfile_TextGen` set extension to `.md`
- In `MdTextLine_TextGen` remove section creating whitespace between elements

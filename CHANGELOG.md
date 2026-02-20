# Changelog

All notable changes to the Zed Vento extension will be documented in this file.

## [1.0.0]

### Fixed

- **CRITICAL FIX:** Added literal keyword string highlighting
  - Keywords like `set`, `/set`, `echo`, `function`, `/function`, `slot`, `/slot`, `default`, and `/default` are now properly highlighted
  - Previously only the node types were highlighted, not the actual keyword text
  - All 26 literal keyword strings now have proper syntax highlighting

### Changed

- Updated to tree-sitter-better-vento commit `86de6ba38b6bde0253019cb7bbe0ce05bbd615a1`
- Improved syntax highlighting with more specific keyword scopes:
  - Control flow keywords now use `@keyword.control.conditional` and `@keyword.control.repeat`
  - Export keywords now use `@keyword.control.export` instead of `@keyword.control.import`
- Added explicit highlighting for tag delimiters (`{{`, `}}`, etc.)
- Added explicit highlighting for operators (`=`, `,`, `|>`)

### Added

- Support for new Vento keywords:
  - `{{ echo }}` - Output expressions
  - `{{ slot }}` / `{{ /slot }}` - Slot definitions
  - `{{ default }}` / `{{ /default }}` - Default content blocks
- Test file demonstrating new keywords (`corpus/new-keywords-test.vto`)
- Comprehensive keyword documentation in README
- Literal keyword highlighting for all 26 keyword strings:
  - Control: `if`, `/if`, `else`, `for`, `/for`, `await`, `of`
  - Layout: `layout`, `/layout`, `slot`, `/slot`, `default`, `/default`
  - Variables: `set`, `/set`, `echo`
  - Imports/Exports: `import`, `from`, `export`, `/export`, `include`
  - Functions: `function`, `/function`, `async`
  - Fragments: `fragment`, `/fragment`

### Technical Details

- Highlights file now includes both node-type patterns AND literal string patterns
- Node patterns: `(set_tag) @keyword` - highlights the entire node
- Literal patterns: `"set" @keyword` - highlights just the keyword text
- This dual approach ensures keywords are visible regardless of tree-sitter version or parsing state

## [0.0.1] - 2024-02-07

### Added

- Initial release with basic Vento support
- YAML front matter parsing and injection
- HTML content injection
- JavaScript code injection
- Support for all major Vento constructs:
  - Control flow (`if`, `else`, `for`)
  - Variables and templates
  - Functions and imports
  - Comments and filters

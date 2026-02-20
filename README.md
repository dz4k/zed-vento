# Zed-Vento

Adds support for the Vento template language to the Zed code editor.

## Features

- Syntax highlighting for Vento template files (`.vto`, `.vento`)
- YAML front matter support with proper language injection
- HTML injection for template content
- JavaScript injection for code blocks
- Complete support for all Vento keywords and constructs

### Supported Keywords

All Vento keywords are properly parsed and highlighted:

#### Control Flow

- `{{ if }}` / `{{ /if }}` - Conditional blocks
- `{{ else if }}` - Else-if branches
- `{{ else }}` - Else branches
- `{{ for }}` / `{{ /for }}` - Loop blocks (with optional `await`)

#### Variables and Output

- `{{ set }}` / `{{ /set }}` - Variable assignment (tag and block forms)
- `{{ echo }}` - Output expressions

#### Layout and Composition

- `{{ layout }}` / `{{ /layout }}` - Layout blocks
- `{{ slot }}` / `{{ /slot }}` - Slot definitions
- `{{ default }}` / `{{ /default }}` - Default content blocks
- `{{ include }}` - Include other templates
- `{{ fragment }}` / `{{ /fragment }}` - Fragment blocks (plugin)

#### Functions and Modules

- `{{ function }}` / `{{ /function }}` - Function definitions (with optional `export`, including `export async`)
- `{{ import }}` - Import from other templates
- `{{ export }}` / `{{ /export }}` - Export variables (tag and block forms)

#### Special Tags

- `{{> }}` - JavaScript execution tag
- `{{# #}}` - Comment tag

### Front Matter Support

This extension supports YAML front matter at the beginning of Vento templates:

```vento
---
title: My Page
date: 2024-01-01
tags:
  - vento
  - template
---

<h1>{{ title }}</h1>
```

The YAML content within the front matter delimiters (`---`) will be properly highlighted and treated as YAML.

## Installation

Install the extension as usual for Zed.

### From Source (Development)

1. Clone this repository
2. In Zed, open the command palette (`Cmd+Shift+P` on macOS, `Ctrl+Shift+P` on Linux/Windows)
3. Run the command "zed: install dev extension"
4. Select the cloned repository folder

## About Vento

Vento is a fast and modern template engine for JavaScript. Learn more at [vento.js.org](https://vento.js.org).

## License

MIT

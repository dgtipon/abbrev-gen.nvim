# abbrev-gen.nvim
  
<div align="center">

![Neovim](https://img.shields.io/badge/Neovim-0.8+-green)

![Lua](https://img.shields.io/badge/Lua-5.1-blue)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

</div>

A smart abbreviation expander tailored for Markdown files in Neovim. Inspired by Tim Pope's vim-abolish, but extended for modern workflows: type one or more characters and watch them expand intelligently into full words or phrases. The plugin comes preloaded with twenty two single letter abbreviations, over one hundred two letter abbreviations, and over 1700 root word abbreviations, each with multiple suffix variations. All abbreviations are stored in an easy to read and modify JSON data structure.

Quickly boost your Markdown productivity by taking advantage of abbreviations for over 10,000 commonly used words. Edit the JSON abbreviation file to improve your typing efficiency.

## Multiple aids help you quickly find the abbreviation you need.

As you type in the Neovim insert mode, the completion popup window suggests the next letter to type to match an abbreviation or words you can select that appear in your open buffer.

Built-in keymaps will popup windows to show you abbreviations.

```
<leader>1 → list all one-letter abbreviations in a popup window
<leader>2 → list all two-letter abbreviations in a popup window
<leader>p → list all prefixes in a popup window
<leader>a → show the abbreviation of the word under cursor in a popup window
```

[Abbrev-Demo1.webm](https://github.com/user-attachments/assets/2eab2072-5837-4ba3-8555-818bec64c1c7)



- Root + suffix system (`abn` → abandon, `abns` → abandons, `abng` → abandoning…)
- Prefix support (`rEaca` → reactivate, `uNaca` → unactivate…)
- Single letter abbreviations (`p` → people, `r` → are, `t` → the)
- Automatic possessive (`pS` → people's)
- Case handling (`Abn` → Abandon)
- Built-in nvim-cmp source with incremental suffix completion
- Escape mode with `>` (type `abn> ` to literally insert `abn` without treating it as an abbreviation)

## Installation

```lua
{
  "dgtipon/abbrev-gen.nvim",
  ft = "markdown",
  dependencies = { "hrsh7th/nvim-cmp" },
  config = function()
    require("abbrev-gen").setup({
      enable_keymaps = true,
      enable_escape = true,
      register_cmp_source = true,
    })
  end,
}
```

# Configuration

```
require("abbrev-gen").setup({
  enable_keymaps = true,        -- <leader>1, <leader>2, <leader>p, <leader>a
  enable_escape = true,         -- type abbrev> then punctuation to escape expansion
  register_cmp_source = true,   -- auto-registers the cmp source
})
```

# Keymaps (Markdown only)

```
<leader>1 → list all one-letter roots
<leader>2 → list all two-letter roots
<leader>p → list all prefixes
<leader>a → show breakdown of word under cursor
Type any abbreviation + Space, ,, ., !, ?, etc. → auto-expands
```

# How to add new abbreviations

Edit data/abolish_obj_data.json and send a PR — happy to merge!

# License

MIT

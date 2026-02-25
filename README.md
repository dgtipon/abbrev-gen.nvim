# abbrev-gen.nvim

Smart, JSON-driven abbreviation expander for Markdown files in Neovim.

Inspired by vim-abolish but heavily extended for modern Markdown workflows:

- Root + suffix system (`abn` → abandon, `abns` → abandons, `abng` → abandoning…)
- Prefix support (`rEaca` → reactivate, `uNaca` → unactivate…)
- Single letter abbreviations (`p` → people, `r` → are, `t` → the)
- Automatic possessive (`pS` → people's)
- Case handling (`Abn` → Abandon)
- Built-in nvim-cmp source with incremental suffix completion
- Escape mode with `>` (type `abn> ` to literally insert the abbreviation)
- Handy popups: `<leader>1`, `<leader>2`, `<leader>p`, `<leader>a`

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

. <leader>1 → list all one-letter roots
. <leader>2 → list all two-letter roots
. <leader>p → list all prefixes
. <leader>a → show breakdown of word under cursor
. Type any abbreviation + Space, ,, ., !, ?, etc. → auto-expands

# How to add new abbreviations

Edit data/abolish_obj_data.json and send a PR — happy to merge!

# License

MIT

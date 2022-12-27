# telescope-makefile
Simple telescope extension to run GNU Make targets in Neovim.

** This is a fork of https://github.com/sopa0/telescope-makefile **

*:+1:Supports GNU/BSD make*

Requires the [akinsho/nvim-toggleterm.lua](https://github.com/akinsho/nvim-toggleterm.lua) plugin for now.

## Install
For packer.nvim:
```lua
require('packer').startup(function(use)
  use {
    "de-passage/telescope-makefile",
    requires = {
      { "akinsho/toggleterm.nvim" },
      { 'nvim-telescope/telescope.nvim' }
    },
    config = function()
      require('telescope-makefile').setup({
        -- see below
      })
      require('telescope').load_extension('make')
    end
  }
end
```

For LunarVim, in your config.lua:
```lua
lvim.plugins = {
  {
    "de-passage/telescope-makefile",
  },
}
```

## Installation
```lua
require'telescope'.load_extension('make')
```
## Usage
```vim
:Telescope make
```
## Configuration
Default:
```lua
require'telescope-makefile'.setup{
  -- The path where to search the makefile in the priority order
  makefile_priority = { '.', 'build/' }
  default_target = '[DEFAULT]', -- nil or string : Name of the default target | nil will disable the default_target
  make_bin = "make", -- Custom makefile binary path, uses system make by def
}
```

Example keybinding in LunarVim and which-key:
```lua
lvim.builtin.which_key.mappings.M = {
  "<cmd>Telescope make<cr>",
  "Make Targets",
}
```

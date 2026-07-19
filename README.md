# Ask Without Bloat
Neovim plugin for quick in-file AI help. Code or comments are generated from your visual selection and written right under your cursor. If no selection is made the hovered line is used instead. The whole file is always in context.

![Demo GIF](demo.gif)

## Requirements
- [plenary.nvim](https://github.com/nvim-lua/plenary.nvim)
- API key for your chosen provider

## Setup

**Google Gemini (default)**
```lua
-- init.lua
vim.pack.add({
	{ src = "https://github.com/novrion/awb.nvim" }
})

require("awb").setup({
    provider = "gemini", -- default
    model = "gemini-3-flash-preview", -- optional
    api_key = "<your_gemini_api_key>",
    keymaps = {
		ask = { "<leader>a", { "n", "v" } }, -- optional
	},
})
```

**Amazon Bedrock**
```lua
require("awb").setup({
    provider = "bedrock",
    model = "anthropic.claude-sonnet-4-6", -- any Bedrock model ID
    api_key = "<your_bedrock_api_key>",
    region = "us-east-1", -- optional, default: us-east-1
    keymaps = {
		ask = { "<leader>a", { "n", "v" } }, -- optional
	},
})
```

## Default Keybindings
```
<leader>a    opens prompt dialogue
```

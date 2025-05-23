# 📝 Prompt Title: Conventional Commit Message Generator

## 🎯 Goal
Create or rename a Git commit message that follows the [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) specification, based on any combination of provided inputs such as existing commit names, diffs, branch names, or textual context.

## 📥 Input

I've added all my ./config/nvim (too lazy to add file one by one)
Tree: ```
```
├── init.lua
├── lazy-lock.json
└── lua
    ├── config
    │   ├── filetypes.lua
    │   ├── keymaps.lua
    │   ├── lazy.lua
    │   ├── options.lua
    │   └── utils.lua
    ├── nvim-kana.lua
    └── plugins
        ├── bufferline.lua
        ├── cmp.lua
        ├── colorscheme.lua
        ├── conform.lua
        ├── gitsigns.lua
        ├── lspconfig.lua
        ├── lualine.lua
        ├── obsidian.lua
        ├── snacks.lua
        ├── treesitter.lua
        ├── undotree.lua
        └── which-key.lua
```

## 📤 Output
A single, concise, clear commit message that strictly follows Conventional Commit format, including:

- A valid type (e.g., `feat`, `fix`, `docs`, `style`, `refactor`, `test`, `chore`, etc.)
- An optional scope if appropriate (e.g., `feat(auth): ...`)
- A succinct imperative mood description of the change
- Optionally, a footer if the commit relates to issues or breaking changes (only if clearly implied by input)

The output must be only the commit message text without additional explanation.

## 🧠 Context
Conventional Commits are a standardized format for commit messages to make changelogs and versioning easier. Examples include:

- `feat(auth): add OAuth2 login support`
- `fix(ui): correct button alignment on mobile`
- `docs(readme): update installation instructions`

If multiple inputs are given, use them together to infer the most accurate type and description. Prioritize existing commit message if it is clear and valid; otherwise, generate a new one based on diffs or context.

## 🔁 Format Constraints
- Use lowercase for the commit type
- Use imperative verb form in the description
- Limit description to about 50 characters (if possible)
- No extra commentary or formatting—output must be exactly the commit message text only
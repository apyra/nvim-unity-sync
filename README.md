# NvimUnitySync

**Nvim Unity Sync** is a lightweight Neovim plugin designed to enhance Unity development inside Neovim. It automatically manages `.csproj` files based on file events, helping you avoid the need to manually regenerate project files in Unity.

## Required

- [Nvim-tree](https://github.com/nvim-tree/nvim-tree.lua)

## ✨ Features

- Automatically adds or removes `<Compile>` tags from `.csproj` files when `.cs` files are created, deleted, or renamed.
- Hooks into `nvim-tree` and LSP events.
- Offers commands to manually manage project structure.

> Note that the Assembly-CSharp.csproj will be overwriten by Unity, but in this way you can work in your Unity project with lsp features like code completions without the need of unity to be open.


## 🔧 Plugin Commands

| Command        | Description |
|----------------|-------------|
| `:Ustatus`     | Show project status info. 
| `:Usync`       | If you have a valid unity project it will sync your files. |
| `:Uopen`       | Try to open Unity if there is a valid project folder  |


## 📂 Installation

Install via Lazy:

```lua
{
  "apyra/nvim-unity-sync",
  config = function()
    require("unity.plugin").setup({
        -- Configs here (Optional) 
        })
  end,
  ft = "cs",
}
```
Available Configs

```lua
.setup({
  unity_path = "path/to/unity/Unity.exe", -- Optional, to run the :Uopen command
  unity_cs_template = false --Optional, used to insert the unity MonoBehaviour template in new .cs files
})

```

## 🧩 Unity Editor Integration

To make the integration even smoother, you can install the Unity-side package:

📦 [`nvim-unity`](https://github.com/apyra/nvim-unity)

This Unity package:

- Adds a "Regenerate Project Files" button inside the Unity editor
- Lets you set Neovim as the external script editor
- Generates `.csproj` and `.sln` on demand

---

## 🧑‍💻 Contributing

PRs and suggestions welcome! This plugin is still under early development.

## 📜 License
MIT









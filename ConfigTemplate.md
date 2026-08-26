# Config Template

Here is my config file for anyone to use as a template for their own. All text with `//` on the back, wont be shown.

## `config.jsonc` file:

```jsonc
{
  "$schema": "[https://github.com/fastfetch-cli/fastfetch/raw/dev/doc/json_schema.json](https://github.com/fastfetch-cli/fastfetch/raw/dev/doc/json_schema.json)",

  "logo": {
    "type": "file",
    // Options: "auto", "file", "builtin", "iterm", "kitty", "nerdFont", "none"
    "source": "C:/ProgramData/fastfetch/_tva.txt",
    // Path to your custom text or image source file
    "width": 20,
    "padding": {
      "right": 5
    },
    "color": {
      "1": "38;2;0;120;212",
      // Note: '38;2' is required for true-color RGB (Red;Green;Blue)
      "2": "38;2;215;10;83",
      "3": "38;2;130;195;120"
    }
  },

  "display": {
    "separator": " ──> ",
    "color": {
      "keys": "38;2;0;120;212",
      // Uses 38;2 for custom RGB key coloring
      "title": "38;2;0;120;212",
      // Uses 38;2 for custom RGB title coloring
      "output": "38;2;200;200;200"
      // Uses 38;2 for custom RGB output coloring
    },
    "brightColor": false
  },

  "modules": [
    "title",
    "break",

    { "type": "custom", "format": "{#38;2;0;120;212}┌── 🖥️  HOST ──────────────────┐" },
    // Note: Inline format strings use '38;2;R;G;B' to colorize header text
    "host",
    "kernel",
    "uptime",
    "localip",

    "break",

    { "type": "custom", "format": "{#38;2;0;120;212}┌── 📦 SOFTWARE ──────────────┐" },
    "os",
    "de",
    // "wm",
    // Uncomment if you use a standalone window manager
    // "wmtheme",
    // Window manager theme
    // "theme",
    // Desktop UI theme
    // "icons",
    // Icon pack name
    // "cursor",
    // Cursor theme
    "terminal",
    // "terminalfont",
    // Terminal font style
    "shell",
    "packages",
    "locale",

    "break",

    { "type": "custom", "format": "{#38;2;0;120;212}┌── ⚡ HARDWARE ──────────────┐" },
    "cpu",
    "gpu",
    "memory",
    // "swap",
    // Virtual memory / swap usage
    "disk",
    "display",
    // "font",
    // System font
    "battery",
    "poweradapter",

    "break",
    "colors"
  ]
}

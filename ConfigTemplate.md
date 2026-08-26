# Config Template

Here is my config file for anyone to use as a template for their own. All text with `//` on the back, wont be shown.

## `config.jsonc` file:

```jsonc
{
  "$schema": "[https://github.com/fastfetch-cli/fastfetch/raw/dev/doc/json_schema.json](https://github.com/fastfetch-cli/fastfetch/raw/dev/doc/json_schema.json)",

  // 🎨 LOGO SETTINGS
  // Configure your custom text logo, size, padding, and RGB theme colors.
  // Note: Fastfetch uses '38;2;R;G;B' formatting for true-color RGB values.
  "logo": {
    "type": "file",
    "source": "C:/ProgramData/fastfetch/_tva.txt",
    "width": 20,
    "padding": {
      "right": 5
    },
    "color": {
      "1": "38;2;0;120;212",   // 38;2 specifies true-color RGB (Red;Green;Blue)
      "2": "38;2;215;10;83",
      "3": "38;2;130;195;120"
    }
  },

  // 📐 DISPLAY SETTINGS
  // Control separators, key/title/output colors, and bold text styling.
  // '38;2' is required here to define custom 24-bit RGB hex-equivalent colors.
  "display": {
    "separator": " ──> ",
    "color": {
      "keys": "38;2;0;120;212",   // Uses 38;2 for custom RGB key coloring
      "title": "38;2;0;120;212",  // Uses 38;2 for custom RGB title coloring
      "output": "38;2;200;200;200" // Uses 38;2 for custom RGB output coloring
    },
    "brightColor": false
  },

  // 🧩 MODULES
  // Add, remove, or uncomment modules depending on what info you want to display.
  "modules": [
    "title",
    "break",

    // HOST SECTION
    // The custom headers use inline format strings where '38;2;R;G;B' is 
    // necessary to colorize the text directly in the terminal output.
    { "type": "custom", "format": "{#38;2;0;120;212}┌── 🖥️  HOST ──────────────────┐" },
    "host",
    "kernel",
    "uptime",
    "localip",

    "break",

    // SOFTWARE SECTION
    { "type": "custom", "format": "{#38;2;0;120;212}┌── 📦 SOFTWARE ──────────────┐" },
    "os",
    "de",
    // "wm",          // Uncomment if you use a standalone window manager
    // "wmtheme",     // Window manager theme
    // "theme",       // Desktop UI theme
    // "icons",       // Icon pack name
    // "cursor",      // Cursor theme
    "terminal",
    // "terminalfont",// Terminal font style
    "shell",
    "packages",
    "locale",

    "break",

    // HARDWARE SECTION
    { "type": "custom", "format": "{#38;2;0;120;212}┌── ⚡ HARDWARE ──────────────┐" },
    "cpu",
    "gpu",
    "memory",
    // "swap",        // Virtual memory / swap usage
    "disk",
    "display",
    // "font",        // System font
    "battery",
    "poweradapter",

    "break",
    "colors"
  ]
}

    "break",
    "colors"
  ]
}

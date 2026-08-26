# SideFetch - Custom Fastfetch Config

Here is my custom config file tailored for a clean, organized terminal overview! Feel free to copy and use it.

## ⚙️ Configuration (`config.jsonc`)

```jsonc
{
  "$schema": "[https://github.com/fastfetch-cli/fastfetch/raw/dev/doc/json_schema.json](https://github.com/fastfetch-cli/fastfetch/raw/dev/doc/json_schema.json)",

  "logo": {
    "type": "file",
    "source": "C:/ProgramData/fastfetch/_tva.txt",
    "width": 20,
    "padding": {
      "right": 5
    },
    "color": {
      "1": "38;2;0;120;212",
      "2": "38;2;215;10;83",
      "3": "38;2;130;195;120"
    }
  },

  "display": {
    "separator": " ──> ",
    "color": {
      "keys": "38;2;0;120;212",
      "title": "38;2;0;120;212",
      "output": "38;2;200;200;200"
    },
    "brightColor": false
  },

  "modules": [
    "title",
    "break",

    { "type": "custom", "format": "{#38;2;0;120;212}┌── 🖥️  HOST ──────────────────┐" },
    "host",
    "kernel",
    "uptime",
    "localip",

    "break",

    { "type": "custom", "format": "{#38;2;0;120;212}┌── 📦 SOFTWARE ──────────────┐" },
    "os",
    "de",
    // "wm",
    // "wmtheme",
    // "theme",
    // "icons",
    // "cursor",
    "terminal",
    // "terminalfont",
    "shell",
    "packages",
    "locale",

    "break",

    { "type": "custom", "format": "{#38;2;0;120;212}┌── ⚡ HARDWARE ──────────────┐" },
    "cpu",
    "gpu",
    "memory",
    // "swap",
    "disk",
    "display",
    // "font",
    "battery",
    "poweradapter",

    "break",
    "colors"
  ]
}

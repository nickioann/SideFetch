# Config Template

Here is my config file for anyone to use as a template for their own. All text with `//` on the back, wont be shown.

## `config.jsonc` file:

```jsonc
# Fastfetch Config Template

My `fastfetch` config, shared as a starting template for anyone who wants one.

> **Note:** Lines starting with `//` are comments. Fastfetch ignores them when it reads the file.

## `config.jsonc`

```jsonc
{
  "$schema": "https://github.com/fastfetch-cli/fastfetch/raw/dev/doc/json_schema.json",
  "logo": {
    "type": "file",
    "source": "/home/nickioann/.config/fastfetch/onion.txt",
    "color": {
      //"1": "",
      //"2": "",
      "3": "green"
    }
  },
  "display": {
    "separator": " ",
    "color": {
      "keys": "blue",
      "title": ""
    },
    "brightColor": false
  },
  "modules": [
    { "type": "custom", "format": "{#white} ------ HOST ------ " },
    {
      "type": "host",
      "outputColor": "38;2;112;91;124"
    },
    "kernel",
    "bios",
    "uptime",
    "localip",
    "break",

    { "type": "custom", "format": "{#white} ------ SOFTWARE ------ " },
    {
      "type": "os",
      "outputColor": ""
    },
    "de",
    "terminal",
    "shell",
    "packages",
    "locale",
    "break",

    { "type": "custom", "format": "{#white} ------ HARDWARE ------ " },
    "cpu",

    // MULTI-DEVICE / jq:
    // Use JSON + jq when a module returns more than one result and you want
    // them listed separately (here: integrated GPU + external GPU).
    //
    // 1. Inspect the module's output first:
    //      fastfetch -s <module> --format json | jq
    // 2. jq indexes start at 0: [0] = first result, [1] = second, [2] = third.
    //    For GPU:
    //      .[0].result[0].name = GPU 1
    //      .[0].result[1].name = GPU 2
    // 3. Create one "command" module per GPU, e.g.:
    //      fastfetch -s gpu --format json | jq -r '.[0].result[1].name'
    // 4. Give each its own "outputColor" (colors the value) and, if wanted,
    //    "keyColor" (colors the label) so they're easy to tell apart.
    {
      "type": "command",
      "key": "GPU 1",
      "outputColor": "38;2;130;195;120",
      "text": "fastfetch -s gpu --format json | jq -r '.[0].result[0].name'"
    },
    {
      "type": "command",
      "key": "GPU 2",
      "outputColor": "red",
      "text": "fastfetch -s gpu --format json | jq -r '.[0].result[1].name'"
    },
    //"gpu",

    "memory",
    "disk",
    "display",
    "battery",
    "poweradapter",
    "break"
    //"colors"
  ]
}
```

# Config Template

Here is my config file for anyone to use as a template for their own. All text with `//` on the back, wont be shown.

## `config.jsonc` file:

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
    { "type": "host",
      "outputColor": "38;2;112;91;124" },
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
    // Use JSON + jq when a module has multiple results and you want them separately, in this scenario its the integrated and external gpu.
    // First inspect the module first:  fastfetch -s <module> --format json | jq
    // jq indexes start at 0: [0]=first, [1]=second, [2]=third
    // GPU:
    //   .[0].result[0].name = GPU 1
    //   .[0].result[1].name = GPU 2
    //
    // So we need to create a command type for both gpus: fastfetch -s gpu --format json | jq -r '.[0].result[1].name'
    // And since we want them separate we can also set their own signatire output and label using "outputColor" for the output and "keyColor" for the module
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
    "break",
   // "colors"
  ]
}


    "break",
    "colors"
  ]
}

# Harper Zed Extension

Zed extension for the
[Harper Grammar Checker](https://github.com/elijah-potter/harper) LS.

![Harper running inside zed](./images/zed_demo.png)

## Supported platforms

| Platform | X86_64 | ARM64 |
|---|---|---|
| Linux | ✅ | ✅ |
| MacOS | ✅ | ✅ |
| Windows | ✅ | ❌ |

## Install

1. [Open the Extension Gallery](https://zed.dev/docs/extensions/installing-extensions)
2. Search for `harper` in the Gallery
3. Click "Install"!

![Harper in the Zed Extension Gallery](./images/extension_in_gallery.png)

## Configuration

To disable specific rules, add following to `Zed/settings.json`. Consult diagnostic tooltips and [the list of Harper rules](https://writewithharper.com/docs/rules).
```
"lsp: {
    "harper-ls": {
        "settings": {
            "harper-ls": {
                "linters": {
                    // "RuleName": false,
                },
            },
        },
    },
}
```

## Acknowledgments

- [elijah-potter](https://github.com/elijah-potter) for creating Harper
- [WeetHet](https://github.com/WeetHet) for their
  [typst LS extension](https://github.com/WeetHet/typst.zed) which was used as
  inspiration for this repository :)

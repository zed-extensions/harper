# Harper Zed Extension

Zed extension for the
[Harper Grammar Checker](https://github.com/Automattic/harper) LS.

![Harper running inside zed](./images/zed_demo.png)

## Supported Platforms

| Platform | X86_64 | ARM64 |
| -------- | ------ | ----- |
| Linux    | ✅     | ✅    |
| macOS    | ✅     | ✅    |
| Windows  | ✅     | ❌    |

## Install

1. [Open the Extension Gallery](https://zed.dev/docs/extensions/installing-extensions)
2. Search for `harper` in the Gallery
3. Click "Install"!

![Harper in the Zed Extension Gallery](./images/extension_in_gallery.png)

## Usage

When Harper encounters a potentially misspelled word in the Zed editor, the word will be highlighted.

To view view more details, you can hover the highlighted word to see the warning and related Harper rule.

To fix the issue, click or move the cursor to the highlighted word and then open the Zed _code actions_ shortcut (default keyboard shortcut: `CTRL + .`) to see a list of suggested fixes. You can also click the lightning icon for the relevant line to see the same code actions.

For simple grammar and spelling mistakes, this is usually enough to quickly find and fix issues.

### Adding Custom Words to User, Workspace or File Dictionaries

You can add new words to your Harper dictionaries by using the Zed code action described above. There are three kinds of dictionaries available:

1. [User dictionary](https://writewithharper.com/docs/integrations/language-server#User-Dictionary) - Your global dictionary for all projects.
2. [Workspace dictionary](https://writewithharper.com/docs/integrations/language-server#Workspace-Dictionary) - Local project-specific dictionary. Useful to keep in version control to have a shared dictionary for your team.
3. [File-Local dictionary](https://writewithharper.com/docs/integrations/language-server#File-Local-Dictionary) - Custom words only for the current file.

You can configure where these dictionaries are stored. See below for more info.

## Configuration

To disable specific rules, add the following to `Zed/settings.json`:

```
"lsp: {
    "harper-ls": {
        "settings": {
            "harper-ls": {
                "linters": {
                    // "RuleName": false, // For rule names consult tooltips and https://writewithharper.com/docs/rules
                },
            },
        },
    },
}
```

To have a project-specific dictionary, create `.harper-dictionary.txt` in the project root or configure dictionary location by passing `"userDictPath": "%relative_path%",` inside `"settings": {"harper-ls": {...}}`. The dictionary should be a simple line-separated text file.

For additional info consult [Harper LS configuration page](https://writewithharper.com/docs/integrations/language-server#Configuration).

## Acknowledgments

- [elijah-potter](https://github.com/elijah-potter) for creating Harper
- [WeetHet](https://github.com/WeetHet) for their
  [typst LS extension](https://github.com/WeetHet/typst.zed) which was used as
  inspiration for this repository :)

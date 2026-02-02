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

To fix the issue, click or move the cursor to the highlighted word and then open the Zed _code actions_ (default keyboard shortcut: `CTRL + .`) to see a list of suggested fixes. You can also click the lightning icon for the relevant line to see the same code actions.

For simple grammar and spelling mistakes, this is usually enough to quickly find and fix issues.

### Adding Custom Words to User, Workspace or File Dictionaries

You can add new words to your Harper dictionaries by using the Zed code action described above. There are three kinds of dictionaries available:

1. [User dictionary](https://writewithharper.com/docs/integrations/language-server#User-Dictionary) - Your global dictionary for all projects.
2. [Workspace dictionary](https://writewithharper.com/docs/integrations/language-server#Workspace-Dictionary) - Local project-specific dictionary. Useful to keep in version control to have a shared dictionary for your team.
3. [File-Local dictionary](https://writewithharper.com/docs/integrations/language-server#File-Local-Dictionary) - Custom words only for the current file.

You can configure where these dictionaries are stored. See below for more info.

## Configuration

This extension lets you customise the [Harper LS configuration](https://writewithharper.com/docs/integrations/language-server#Configuration) by for example adding the following to your `Zed/settings.json`:

```jsonc
"lsp: {
    "harper-ls": {
        "settings": {
            "harper-ls": {
                // Use a specific English dialect
                "dialect": "British",
                "linters": {
                    // Disable specific rules
                    // For rule names consult tooltips and https://writewithharper.com/docs/rules
                    "RuleName": false,
                },
            },
        },
    },
}
```

Note that both of the two nested layers of `harper-ls` are required for the configuration to work.

### Configuring Dictionary Locations

Harper dictionary files should be simple line-separated text files. Learn more about how they work, and where you can find them in the [Harper documentation](https://writewithharper.com/docs/integrations/language-server#Dictionaries).

You can configure where to store your user dictionary, workspace dictionary and file dictionaries by editing `Zed/settings.json`:

```jsonc
"lsp: {
    "harper-ls": {
        "settings": {
            "harper-ls": {
                // Set the file path where the user dictionary is located
                "userDictPath": "%relative_path%",

                // Set the file path where the workspace dictionary is located
                "workspaceDictPath": ".harper-dictionary.txt",

                // Set the directory where the file-local dictionaries are located
                  "fileDictPath": "%relative_path%"
            },
        },
    },
}
```

For additional info consult [Harper LS configuration page](https://writewithharper.com/docs/integrations/language-server#Configuration).

## Acknowledgments

- [elijah-potter](https://github.com/elijah-potter) for creating Harper
- [WeetHet](https://github.com/WeetHet) for their
  [typst LS extension](https://github.com/WeetHet/typst.zed) which was used as
  inspiration for this repository :)

# Koshka for VS Code

This extension runs the Koshka language server and formatter, which are part
of the `kosh` binary.

## Installing a release

Download `kosh.vsix` from the
[releases](https://github.com/fennec-support/kosh-vscode/releases) page and
run:

```bash
code --install-extension kosh.vsix
```

The extension needs the `kosh` binary. It uses `kosh.path`, then `PATH`, and
otherwise offers to download the newest release of
[fennec-support/kosh](https://github.com/fennec-support/kosh).

## Building and installing

```bash
npm install
npm run compile
npm run package
code --install-extension kosh.vsix
```

## Formatting on save

The extension does not turn on formatting on save. Enable it in your settings:

```jsonc
{
  "[shellscript]": {
    "editor.formatOnSave": true
  }
}
```

Leave `editor.formatOnSaveMode` at its default, `file`. The server formats only
whole documents, so the `modifications` mode skips the file without an error.

## Settings

The values below are the defaults.

```jsonc
{
  // Start the Koshka language server.
  "kosh.enable": true,

  // Name or absolute path of the kosh binary. The extension looks up a bare
  // name in PATH.
  "kosh.path": "kosh",

  // Arguments placed before --as-language-server.
  "kosh.arguments": [],

  // Trace level for messages between VS Code and the server: "off",
  // "messages", or "verbose".
  "kosh.trace.server": "off"
}
```

The server reads these options once at startup, so the extension restarts it
when any of them changes.

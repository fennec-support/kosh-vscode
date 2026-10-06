# koshka for VS Code

This repository hosts [Koshka Shell](https://github.com/fennec-support/kosh)
tooling for VS Code and its descendants.

Currently that includes:
- Linter
- LSP/Symbols
- Formatter

You should probably install this extension from the Extension Marketplace.

### Installing a release

Download `kosh.vsix` from the
[releases](https://github.com/fennec-support/kosh-vscode/releases) page and
run:
```bash
code --install-extension kosh.vsix
```

### Manual installation

```bash
npm install
npm run compile
npm run package
code --install-extension kosh.vsix
```

### Settings

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

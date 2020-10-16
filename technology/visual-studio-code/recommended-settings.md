# Recommended settings

Here are some of my recommended settings. These are optional, but I get asked a lot for them, so here they are.

## Editor settings

```javascript
  "editor.autoIndent": true,
  "editor.codeActionsOnSave": {
    "source.organizeImports": false
  },
  "editor.codeLens": false,
  "editor.cursorBlinking": "solid",
  "editor.cursorSmoothCaretAnimation": true,
  "editor.cursorStyle": "line",
  "editor.fontSize": 16,
  "editor.fontFamily": "Dank Mono, Operator Mono, Fira Code, Inconsolata, Menlo",
  "editor.fontLigatures": true,
  "editor.formatOnPaste": true,
  "editor.formatOnType": false,
  "editor.formatOnSave": true,
  "editor.letterSpacing": 0.5,
  "editor.lineHeight": 25,
  "editor.minimap.enabled": false,
  "editor.renderWhitespace": "none",
  "editor.tabCompletion": "on",
  "editor.tabSize": 2,
  "editor.wordWrap": "off",
```

## File settings

```javascript
"files.autoSave": "afterDelay",
"files.autoSaveDelay": 1000,
"files.exclude": {
  "**/.git": true,
  "**/.DS_Store": true,
  "**/*.js": {
    "when": "$(basename).ts"
  },
  "**/*.js.map": {
    "when": "$(basename)"
  }
},
"files.hotExit": "onExit",
"files.defaultLanguage": "typescript",
"files.trimTrailingWhitespace": true,
```

## Prettier settings

```javascript
"prettier.singleQuote": true,
"prettier.printWidth": 120,
"prettier.tabWidth": 2,
"prettier.useTabs": false,
```


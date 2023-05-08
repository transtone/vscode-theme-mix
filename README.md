# kary-mix README

A theme with light UI and dark editor.

## editor theme

editor use [kary-dark](https://marketplace.visualstudio.com/items?itemName=karyfoundation.theme-karyfoundation-themes) theme.

## tips

* Editor's `foreground` color and `background` color set as light theme.
Because `editor.backgound` effect not only editor but also extension page, settings page etc..., but `editor.forground` not.
So it can get a dark backgound and dark text settings page.

```json
    "editor.background": "#FFFFFF",
    "editor.foreground": "#000000",
```

* Use [Custom CSS and JS Loader](https://marketplace.visualstudio.com/items?itemName=be5invis.vscode-custom-css) change editor's background and text color

save these css to `theme.css` , and set `"vscode_custom_css.imports": path/theme.css` in `settings.json` :

```css
/* globle backgound is white, need cover the editor backound */
#workbench\.parts\.editor .monaco-editor-background,
#workbench\.parts\.editor .monaco-editor .margin {
  background-color: #1a1a1a;
}

.monaco-workbench #workbench\.parts\.editor {
  --vscode-editor-background: #1a1a1a;
  --vscode-editor-foreground: #cccccc;
  --vscode-foreground: #cccccc;
}

/* globle forground is black，need cover the text color and floating widget color  */
#workbench\.parts\.editor .monaco-editor .mtk1,
.monaco-workbench .overflowingContentWidgets {
  --vscode-foreground: #cccccc;
  color: #CCCCCC;
}

/* becaouse "peekViewEditor.background" settings coved by upper settings, recover it */
#workbench\.parts\.editor .zone-widget .monaco-editor-background,
#workbench\.parts\.editor .zone-widget .monaco-editor .margin {
  background-color: #392620;
}

/* seachInput */
#workbench\.parts\.editor .suggest-input-container .lines-content.monaco-editor-background,
.settings-editor>.settings-body .settings-toc-container .monaco-list-row {
  background-color: #fff;
}

#workbench\.parts\.editor .settings-body {
  --vscode-editor-background: #fff;
  --vscode-editor-foreground: #262626;
}

#workbench\.parts\.editor .suggest-input-container .lines-content.monaco-editor-background .mtk1:not(.ghost-text-decoration) {
  color: #000000;
}

/* overlay message */
.monaco-editor .monaco-editor-overlaymessage .message {
  --vscode-inputValidation-infoForeground: #262626;
  color: var(--vscode-inputValidation-infoForeground);
}

/* minimap's shadow mast disable in light theme */
.monaco-editor .minimap-shadow-visible {
  box-shadow: none;
}

/* breadcrumb shadow */
.monaco-editor .scroll-decoration {
  box-shadow: #1a1a1a 0 6px 6px -6px inset;
}

/*  panel(file explorer, extension etc...) scroll shadow */
.monaco-scrollable-element>.shadow.top {
  box-shadow: #1a1a1a33 0 6px 6px -6px inset;
}

/* code suggest icon background */
.monaco-editor .lightBulbWidget:after,
.monaco-editor .contentWidgets .codicon.codicon-lightbulb-autofix,
.monaco-editor .contentWidgets .codicon.codicon-light-bulb {
  background-color: rgba(26, 26, 26, 0.7);
}
```

**Enjoy!**

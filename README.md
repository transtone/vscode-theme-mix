# kary-mix README

A theme with light UI and dark editor.

## editor theme

editor use [kary-dark](https://marketplace.visualstudio.com/items?itemName=karyfoundation.theme-karyfoundation-themes) theme.

## tips

* Editor's `foreground` color and `background` color is set as light theme.

```json
    "editor.background": "#FFFFFF",
    "editor.foreground": "#000000",
```

> Because `editor.backgound` effect not only editor but also extension page, settings page etc..., but `editor.forground` not.
> So it can get a dark backgound and dark text settings page.

* Use [Custom CSS and JS Loader](https://marketplace.visualstudio.com/items?itemName=be5invis.vscode-custom-css) change editor's background and text color

get [theme.css](https://raw.githubusercontent.com/transtone/vscode-theme-mix/main/Custom%20CSS%20and%20JS%20Loader/theme.css), 
and set `"vscode_custom_css.imports": path/theme.css` in `settings.json` :

**Enjoy!**

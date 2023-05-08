# vscode theme mixed with default light theme and kary

## doc

https://liiked.github.io/VS-Code-Extension-Doc-ZH/#/references/theme-color

## 方案说明

* 此主题为亮色主题，只代码编辑区为暗色
* 此主题由一个主题文件：`light_mix.josn` 和一个样式文件: `theme.css` 组成
* 采用 [kary-dark](https://marketplace.visualstudio.com/items?itemName=karyfoundation.theme-karyfoundation-themes) 配色(代码、弹窗、活动区及其他部分组件)
* 主题文件中强制设定背景为白色，字体为黑色
* 代码区的背景及字体，通过 `Custom CSS and JS Loader` 插件，覆盖vscode样式来设置
* 迷你地图调整为暗色
* 保持滚动条为亮色。如果强制设置为黑色，则代码修改色块及错误提示色块都会被覆盖

### 为什么不直接使用 theme-color，而采取 Custom CSS and JS Loader 方案？

theme-color 的几个主颜色变量( `editor.background` , `editor.foreground` , `foreground` )，也同时被插件页及设置页使用，不能在整体为亮色的前提下，将代码编辑区设置为暗色。

### [Custom CSS and JS Loader](https://marketplace.visualstudio.com/items?itemName=be5invis.vscode-custom-css)  参考样式

```css
/* 全局背景为白色，需要覆盖设置编辑区整体背景 */
#workbench\.parts\.editor .monaco-editor-background,
#workbench\.parts\.editor .monaco-editor .margin {
  background-color: #1a1a1a;
}

.monaco-workbench #workbench\.parts\.editor {
  --vscode-editor-background: #1a1a1a;
  --vscode-editor-foreground: #cccccc;
}

/* 全局前景为黑色，需要覆盖设置默认代码颜色，浮动窗前景色  */
#workbench\.parts\.editor .monaco-editor .mtk1,
.monaco-workbench .overflowingContentWidgets {
  --vscode-foreground: #cccccc;
  color: #CCCCCC;
}

/* 因为 "peekViewEditor.background" 设置值被上面的背景色所覆盖，所以要覆盖回来 */
#workbench\.parts\.editor .zone-widget .monaco-editor-background,
#workbench\.parts\.editor .zone-widget .monaco-editor .margin {
  background-color: #392620;
}

/* 搜索框 */
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

/* 消息弹窗 */
.monaco-editor .monaco-editor-overlaymessage .message {
  --vscode-inputValidation-infoForeground: #262626;
  color: var(--vscode-inputValidation-infoForeground);
}

/* 暗色模式下，迷你图边框阴影会被样式隐藏，亮色模式下需要强制关闭 */
.monaco-editor .minimap-shadow-visible {
  box-shadow: none;
}

/* 面包屑下边界阴影 */
.monaco-editor .scroll-decoration {
  box-shadow: #1a1a1a 0 6px 6px -6px inset;
}

/* 左侧面板(文件树,扩展列表等)滚动时上边界阴影 */
.monaco-scrollable-element>.shadow.top {
  box-shadow: #1a1a1a33 0 6px 6px -6px inset;
}

/* 代码提示图标背景 */
.monaco-editor .lightBulbWidget:after,
.monaco-editor .contentWidgets .codicon.codicon-lightbulb-autofix,
.monaco-editor .contentWidgets .codicon.codicon-light-bulb {
  background-color: rgba(26, 26, 26, 0.7);
}
```

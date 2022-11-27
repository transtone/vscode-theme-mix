# vscode theme mixed with default light theme and kary

## doc

https://liiked.github.io/VS-Code-Extension-Doc-ZH/#/references/theme-color

## 方案说明

* 此主题为亮色主题，只代码编辑区为暗色
* 此主题由一个主题文件：`light_mix.josn` 和一个样式文件: `theme.css` 组成
* 采用 kary-dark 配色(代码、弹窗、活动区及其他部分组件)
* 主题文件中强制设定背景为白色，字体为黑色
* 代码区的背景及字体，通过 `Custom CSS and JS Loader` 插件，覆盖vscode样式来设置
* 迷你地图调整为暗色
* 保持滚动条为亮色。如果强制设置为黑色，则代码修改色块及错误提示色块都会被覆盖

### 为什么不直接使用 theme-color，而采取 Custom CSS and JS Loader 方案？

theme-color 的几个主颜色变量( `editor.background` , `editor.foreground` , `foreground` )，也同时被插件页及设置页使用，不能在整体为亮色的前提下，将代码编辑区设置为暗色。

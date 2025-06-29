# Region Highlighter

**Region Highlighter** 增强了 Visual Studio Code 编辑器的默认区域功能。

支持通过命令快速生成或撤销区域，并提供丰富的区域着色方式。

> 🎉 优势：支持所有 Visual Studio Code 内置区域语言。

---

## 功能特性

### 命令: `Region Highlighter: Mark Region`

此命令为选中的文本生成区域块，可传入可选名称作为标识符：

![命令: Mark](https://github.com/Wiensss/vscode-region-highlighter/blob/1.0.0/assets/region_mark.gif?raw=true)

### 命令: `Region Highlighter: UnMark Region`

此命令撤销选中文本的区域块。

> 注意：选中文本必须包含起始和结束区域注释语句

![命令:Unark](https://github.com/Wiensss/vscode-region-highlighter/blob/1.0.0/assets/region_unmark.gif?raw=true)

### 忽略标志符

当区域标记外的第一个字符匹配标志符时，不装饰当前区域。

> 默认标志符为 `!`

![忽略标志符](https://github.com/Wiensss/vscode-region-highlighter/blob/1.0.0/assets/region_ignore_flag.gif?raw=true)

### 内置主题

![内置主题](https://github.com/Wiensss/vscode-region-highlighter/blob/1.0.0/assets/built_in_theme.png?raw=true)

---

## 扩展设置

### 语言支持

| **语言** | **起始区域** | **结束区域** |
| ------------ | ---------------- | -------------- |
| Bat | `::#region` 或 `REM #region` | `::#endregion` 或 `REM #endregion` |
| C#/Coffeescript/PHP/PowerShell |`#region` | `#endregion` |
| Python | `#region` 或 `# region` | `#endregion` 或 `# endregion` |
| Vue/TypeScript/JavaScript/Rust/Golang |`// #region` | `// #endregion` |
| C/C++ | `#pragma region` | `#pragma endregion` |
| Css/Less/Scss | `/*#region*/` | `/*#endregion*/` |
| F# | `//#region` 或 `(#_region)` | `//#endregion` 或  `(#_endregion)` |
| Java | `//#region` 或 `//<editor-fold>` | `// #endregion` 或 `//</editor-fold>` |
| Markdown/HTML | `<!-- #region -->` | `<!-- #endregion -->` |
| Perl5 | `#region` 或 `=pod` | `#endregion` 或 `=cut` |
| Visual Basic | `#Region` | `#End Region` |

### 配置选项

![配置界面](https://github.com/Wiensss/vscode-region-highlighter/blob/1.0.0/assets/configuration.png?raw=true)

#### `regionHighlighter.allowLanguageIDs`

扩展生效的语言ID列表。标识符需用逗号分隔。

`*` 表示支持所有语言。示例：`javascript,typescript`。

#### `regionHighlighter.ignoreFlag`

当区域标记外的第一个字符匹配此标志符时，不装饰当前区域。

#### `regionHighlighter.defaultTheme`

默认区域CSS样式，示例：`pink` / `rgb(255,192,203)` / `hsl(350deg,100%,88%)` / `#FFC2CC`。

#### `regionHighlighter.defaultColor`

默认区域背景色主题，可选值：

```javascript
[
  "Rainbow",
  "Day3024",
  "Morandi",
  "Custom Theme",
  "Default Color"
]
```

#### `regionHighlighter.customColor`

仅在 `regionHighlighter.defaultTheme` 设为 `Custom Theme` 时生效。

支持两种配置格式：`Array<颜色值>` 或 `Array<{label: string, color: string }>`. 示例：

```json
[
  "#FF00001A",
  "#FF45001A",
  "#FFFF0026",
  "#0000FF0D",
  "#8000801A"
]
or
[
  {
    "label": "红色",
    "color": "FF00001A"
  },
  {
    "label": "橙色",
    "color": "#FF45001A"
  },
  {
    "label": "黄色",
    "color": "#FFFF0026"
  },
  {
    "label": "绿色",
    "color": "#90EE9026"
  },
  {
    "label": "蓝色",
    "color": "#0000FF0D"
  },
  {
    "label": "紫色",
    "color": "#8000801A"
  }
]
```

> label属性将在未来用于自定义内嵌区域颜色

##### `regionHighlighter.decorationStyle`

默认区域装饰样式，可选值：

```json
[
  "border",
  "background"
]
```

#### `regionHighlighter.borderStyle`

装饰区域边框样式。仅在 `regionHighlighter.decorationStyle` 设为 `border` 时生效，可选值：

```json
[
  "solid",
  "dashed",
  "dotted",
  "double",
  "groove"
]
```

#### `regionHighlighter.borderWidth`

装饰区域边框宽度。仅在 `regionHighlighter.decorationStyle` 设为 `border` 时生效。

#### `regionHighlighter.extraColorStrategy`

当编辑器中的区域块数量超过预设颜色数量时的装饰策略，可选值：

```json
[
  "Default Color",
  "Custom Theme First Color",
  "Custom Theme Last Color"
]
```

---

## Release Notes

## [1.0.3] - 2025-06-30

by @LincZero

添加中文版README，修复旧README中的描述错误

## [1.0.2] - 2025-04-09

by @LincZero

修复了 #7

编译： (可用VSCode Codespace环境进行)

```bash
npm install
# npm audit fix --force
# npm install

npm install -g vsce
vsce package
y
```

fork版本的安装：

扩展面板右上角 > 从 `.vsix` 中下载

或 Ctrl Shift P: `Extension: install from VSIX...` | `扩展: 从 VSIX 安装`

## [1.0.2] - 2022-01-05

- `docs`: change description of Language support

- `feat`: support match language of golang and rust

## [1.0.0] - 2022-01-02

- first release!

---

## License

[MIT](https://github.com/Wiensss/vscode-region-highlighter/blob/1.0.0/LICENSE)

---

---
title: 排版
parent: 用户界面组件
nav_order: 1
---

# 排版
{: .no_toc }

## 页内目录
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## 字体栈

默认情况下，Just the Docs 使用原生的基于 sans-serif 字体的字体栈：

```scss
system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif, "Segoe UI Emoji"
```

ABCDEFGHIJKLMNOPQRSTUVWXYZ
abcdefghijklmnopqrstuvwxyz
{: .fs-5 .ls-10 .code-example }

对于等宽类型，例如代码片段或者 `<pre>` 元素，Just the Docs 使用原生系统字体栈：

```scss
"SFMono-Regular", Menlo, Consolas, Monospace
```

ABCDEFGHIJKLMNOPQRSTUVWXYZ
abcdefghijklmnopqrstuvwxyz
{: .fs-5 .ls-10 .text-mono .code-example }

---

## 自适应类型标准

Just the Docs 用一个自适应类型标准应对 Viewport 型号。

| 选择器              | 小屏类型 `font-size`    | 大屏类型 `font-size` |
|:----------------------|:---------------------------------|:------------------------------|
| `h1`, `.text-alpha`   | 32px                             | 36px                          |
| `h2`, `.text-beta`    | 18px                             | 24px                          |
| `h3`, `.text-gamma`   | 16px                             | 18px                          |
| `h4`, `.text-delta`   | 14px                             | 16px                          |
| `h5`, `.text-epsilon` | 16px                             | 18px                          |
| `h6`, `.text-zeta`    | 18px                             | 24px                          |
| `body`                | 14px                             | 16px                          |

---

## 标题

标题渲染如：

<div class="code-example">
<h1>Heading 1</h1>
<h2>Heading 2</h2>
<h3>Heading 3</h3>
<h4>Heading 4</h4>
<h5>Heading 5</h5>
<h6>Heading 6</h6>
</div>
```markdown
# Heading 1
## Heading 2
### Heading 3
#### Heading 4
##### Heading 5
###### Heading 6
```

---

## 正文字体

默认正文字体渲染如：

<div class="code-example" markdown="1">
Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
</div>
```markdown
Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
```

---

## 行内元素

<div class="code-example" markdown="1">
文字可以**加粗**，变_斜体_，或者加上~~横穿线~~。

[链接到另一个页面]({{site.baseurl}}/).
</div>
```markdown
文字可以**加粗**，变_斜体_，或者加上~~横穿线~~。

[链接到另一个页面]({{site.baseurl}}/).
```

---

## 排版工具

大量定制的排版工具类可以让你可以覆盖默认的样式（字号、粗细、行高和首字母大小写等）从而自由发挥和定制。

[查看排版工具类]({% link docs/utilities/typography.md %}){: .btn .btn-outline }

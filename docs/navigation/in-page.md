---
title: 页内导航
parent: 导航
nav_order: 5
---

# 页内导航
{: .no_toc }

## 目录
{: .no_toc .text-delta }

1. TOC
{:toc}

使用页内导航可生成如上的带链接的标题 **Table of Contents**（TOC)，以及返回顶部的链接。

## 生成目录

页面内生成**目录**使用 Kramdown 的 `{:toc}` 方法，可立即在页面开始处生成一个列表，列表项都带有自动生成的到页面内各层标题的页内链接。

{: .note }
`{:toc}` 每页仅限使用一次。

在拥有目录前你**必须**写个列表，列表类型决定了目录类型。

对于**有序**目录，用下面的 markdown 代码：

```md
1. TOC
{:toc}
```

`{:toc}` 行**必须**跟在 `1. TOC` 行下面，这将生成有序列表。

对于**无序**目录，用下面的 markdown 代码：

```
- TOC
{:toc}
```

## 从目录中需要忽略的标题

如果你想从目录中忽略掉特定标题，在该标题下添加 `{: .no_toc }` （可能还会有其他 CSS 类名）。

```markdown
# In-Page Navigation
{: .no_toc }

## Table of Contents
{: .no_toc .text-delta }

1. TOC
{:toc}
```

上例从目录中忽略掉了顶级标题（`In-Page Navigation`）以及*Table of Contents*自己的标题。

## 可折叠目录（用 `<details>` 和 `<summary>` 实现）

你可以使用 `<details>` 和 `<summary>` 元素创建可折叠目录，如下例。

```markdown
<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>
```

`open` 属性（默认打开目录）和样式（这里是 `text-delta`）可选。

## 返回顶部 {#back-to-top-doc}

{: .warning }
“Back to Top”标题的默认 ID 是 `"back-to-top"`。为避免 HTML 无效，站点设置 `back_to_top` 配置变量覆盖默认 ID。当前页 Markdown 源文件使用 `## Back to Top {#back-to-top-doc}`。

你可以为每页底部添加链接——这可以通过在站点 `_config.yml` 配置文件中设置 `back_to_top` 参数实现，还有 `back_to_top_text` 参数设置链接锚点。

### 示例
{: .no_toc }

```yaml
back_to_top: true
back_to_top_text: "Back to top"
```

{: .warning }
只有当 **other** 配置项需要生成 footer 时 Back-to-top 链接才会出现！

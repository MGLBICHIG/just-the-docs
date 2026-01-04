---
title: 排版
parent: CSS 工具类
---

# 排版实用类
{: .no_toc }

## 目录
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## 字号

用 `.fs-1` 到 `.fs-10` 精准设置 `font-size`。

| 类   | 小屏字号 `font-size`  | 大屏字号 `font-size` |
|:--------|:-------------------------------|:------------------------------|
| `.fs-1` | 9px                            | 10px                          |
| `.fs-2` | 11px                           | 12px                          |
| `.fs-3` | 12px                           | 14px                          |
| `.fs-4` | 14px                           | 16px                          |
| `.fs-5` | 16px                           | 18px                          |
| `.fs-6` | 18px                           | 24px                          |
| `.fs-7` | 24px                           | 32px                          |
| `.fs-8` | 32px                           | 38px                          |
| `.fs-9` | 38px                           | 42px                          |
| `.fs-10`| 42px                           | 48px                          |

<div class="code-example" markdown="1">
Font size 1 一号字
{: .fs-1 }
Font size 2 二号字
{: .fs-2 }
Font size 3 三号字
{: .fs-3 }
Font size 4 四号字
{: .fs-4 }
Font size 5 五号字
{: .fs-5 }
Font size 6 六号字
{: .fs-6 }
Font size 7 七号字
{: .fs-7 }
Font size 8 八号字
{: .fs-8 }
Font size 9 九号字
{: .fs-9 }
Font size 10 十号字
{: .fs-10 }
</div>
```markdown
用 Markdown，使用 `{: }` 包裹要定制的类：

Font size 1
{: .fs-1 }
Font size 2
{: .fs-2 }
Font size 3
{: .fs-3 }
Font size 4
{: .fs-4 }
Font size 5
{: .fs-5 }
Font size 6
{: .fs-6 }
Font size 7
{: .fs-7 }
Font size 8
{: .fs-8 }
Font size 9
{: .fs-9 }
Font size 10
{: .fs-10 }
```

## Font weight

用 `.fw-300` 到 `.fw-700` 精准设置 `font-weight`。

<div class="code-example" markdown="1">
Font weight 300 三百
{: .fw-300 }
Font weight 400 四百
{: .fw-400 }
Font weight 500 五百
{: .fw-500 }
Font weight 700 七百
{: .fw-700 }
</div>
```markdown
In Markdown, use the `{: }` wrapper to apply custom classes:

Font weight 300
{: .fw-300 }
Font weight 400
{: .fw-400 }
Font weight 500
{: .fw-500 }
Font weight 700
{: .fw-700 }
```

## 行高

用 `lh-` 类精准为文字设置行高。

| 类         | `line-height` 值  | 说明                         |
|:--------------|:---------------------|:------------------------------|
| `.lh-0`       | 0                    |                               |
| `.lh-tight`   | 1.1                  | 标题默认          |
| `.lh-default` | 1.4                  | 正文（段落）默认 |

<div class="code-example" markdown="1">
No Line height 没有行高
No Line height 没有行高
{: .lh-0 }

Tight line height 紧凑行高
Tight line height 紧凑行高
{: .lh-tight }

Default line height 默认行高
Default line height 默认行高
{: .fh-default }
</div>
```markdown
In Markdown, use the `{: }` wrapper to apply custom classes:

No Line height
No Line height
{: .lh-0 }

Tight line height
Tight line height
{: .lh-tight }

Default line height
Default line height
{: .fh-default }
```

## 文本对齐

默认情况下，文字左对齐，使用 `text-` 类覆盖默认设置：

| 类          | 效果         |
|:---------------|:---------------------|
| `.text-left`   | `text-align: left`   |
| `.text-right`  | `text-align: right`  |
| `.text-center` | `text-align: center` |

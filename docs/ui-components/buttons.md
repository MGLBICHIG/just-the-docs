---
title: 按钮
parent: 用户界面组件
nav_order: 2
---

# 按钮
{: .no_toc }

## 页内目录
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## 基础按钮样式

### 类似按钮样式的链接

<div class="code-example" markdown="1">
[链接按钮](https://just-the-docs.com){: .btn }

[链接按钮](https://just-the-docs.com){: .btn .btn-purple }
[链接按钮](https://just-the-docs.com){: .btn .btn-blue }
[链接按钮](https://just-the-docs.com){: .btn .btn-green }

[链接按钮](https://just-the-docs.com){: .btn .btn-outline }
</div>
```markdown
[链接按钮](https://just-the-docs.com){: .btn }

[链接按钮](https://just-the-docs.com){: .btn .btn-purple }
[链接按钮](https://just-the-docs.com){: .btn .btn-blue }
[链接按钮](https://just-the-docs.com){: .btn .btn-green }

[链接按钮](https://just-the-docs.com){: .btn .btn-outline }
```

### 按钮元素

GitHub Flavored Markdown 不支持 `button` 元素，所以你不得不用行为 HTML 来实现效果：

<div class="code-example">
<button type="button" name="button" class="btn">按钮元素</button>
</div>
```html
<button type="button" name="button" class="btn">按钮元素</button>
```

---

## 按钮工具类

### 按钮型号

在一个使用了[字号工具类]({% link docs/utilities/typography.md %})的容器里使用按钮从而让按钮大小继承父类：

<div class="code-example" markdown="1">
<span class="fs-6">
[大个的按钮](https://just-the-docs.com){: .btn }
</span>

<span class="fs-3">
[小个的按钮](https://just-the-docs.com){: .btn }
</span>
</div>
```markdown
<span class="fs-8">
[链接按钮](https://just-the-docs.com){: .btn }
</span>

<span class="fs-3">
[小个的按钮](https://just-the-docs.com){: .btn }
</span>
```

### 按钮间距

使用[外边距工具类]({% link docs/utilities/layout.md %}#spacing)在同一个块内的两个按钮间添加留白。

<div class="code-example" markdown="1">
[带留白的按钮](https://just-the-docs.com){: .btn .btn-purple .mr-2 }
[按钮](https://just-the-docs.com){: .btn .btn-blue }

[带有更多留白的按钮](https://just-the-docs.com){: .btn .btn-green .mr-4 }
[按钮](https://just-the-docs.com){: .btn .btn-blue }
</div>
```markdown
[带留白的按钮](https://just-the-docs.com){: .btn .btn-purple .mr-2 }
[按钮](https://just-the-docs.com){: .btn .btn-blue }

[带有更多留白的按钮](https://just-the-docs.com){: .btn .btn-green .mr-4 }
[按钮](https://just-the-docs.com){: .btn .btn-blue }
```

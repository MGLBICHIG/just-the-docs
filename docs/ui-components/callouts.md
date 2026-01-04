---
title: 标注
parent: 用户界面组件
nav_order: 7
---

# 标注
{: .d-inline-block }

新增 (v0.4.0)
{: .label .label-green }

Markdown 本身不支持标注，但是你可以通过 Markdown 的扩展——kramdown 的 [*block IALs*](https://kramdown.gettalong.org/quickref.html#block-attributes) 将文字样式定义为标注样式。

常用标注包括高亮（`highlight`）、重要（`important`）、新增（`new`）、谨记（`note`）和警告（`warning`）。

{: .warning }
这些标注的名字**并非**主题预置：你需要自行定制名字。

只有你在[配置]({% link docs/configuration.md %}#callouts)完标注的 `color` 和 `title`（可选）后才算激活标注，然后才能将其用于段落或者带有几个段落的引用块等，示例如下：[^postfix]

[^postfix]:
    标注的标记出现在内容的前面或者后面都可以。

## 一个未命名的标注
{: .no_toc .text-delta }

```markdown
{: .highlight }
A paragraph
```

{: .highlight }
A paragraph


## 一个单独段落的标注
{: .no_toc .text-delta }

```markdown
{: .note }
A paragraph
```

{: .note }
A paragraph

```markdown
{: .note-title }
> My note title
>
> A paragraph with a custom title callout
```

{: .note-title }
> My note title
>
> A paragraph with a custom title callout

## 多段落标注
{: .no_toc .text-delta }

```markdown
{: .important }
> A paragraph
>
> Another paragraph
>
> The last paragraph
```

{: .important }
> A paragraph
>
> Another paragraph
>
> The last paragraph

```markdown
{: .important-title }
> My important title
>
> A paragraph
>
> Another paragraph
>
> The last paragraph
```

{: .important-title }
> My important title
>
> A paragraph
>
> Another paragraph
>
> The last paragraph

## 缩进的标注
{: .no_toc .text-delta }

```markdown
> {: .highlight }
  A paragraph
```

> {: .highlight }
  A paragraph

## 缩进的多段标注
{: .no_toc .text-delta }

```markdown
> {: .new }
> > A paragraph
> >
> > Another paragraph
> >
> > The last paragraph
```

> {: .new }
> > A paragraph
> >
> > Another paragraph
> >
> > The last paragraph


## 内嵌的标注
{: .no_toc .text-delta }

```markdown
{: .important }
> {: .warning }
> A paragraph
```

{: .important }
> {: .warning }
> A paragraph

## 背景不透明
{: .no_toc .text-delta }

```markdown
{: .important }
> {: .opaque }
> <div markdown="block">
> {: .warning }
> A paragraph
> </div>
```

{: .important }
> {: .opaque }
> <div markdown="block">
> {: .warning }
> A paragraph
> </div>

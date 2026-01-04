---
title: 页面版型
layout: default
nav_order: 4.5
---

# 页面版型

页面的版型在 [front matter] 中指定。Just the Docs 几乎用于所有主题文档页面 `default` 版型有边栏，还有一个没有边栏的 `minimal` 版型。
{: .fs-6 .fw-300 }

## 版型概念

查看 [Jekyll 关于版型的文档页面]获取版型的基本理念和如何定制他们。

你可以通过用 [Jekyll 的默认 front matter] 来为一些页面指定相同版型。

## 默认 `default` 版型

本页面就是用了默认版型。本站配置为所有 `docs` 目录的页面设定 `layout: default` 做为[默认 front matter](https://jekyllrb.com/docs/configuration/front-matter-defaults/) 值。

The default layout of Just the Docs is a *responsive* layout: on medium and larger width displays, it displays a sidebar, including a navigation panel; on smaller width displays, the sidebar is automatically hidden under a button.

All pages except top-level pages automatically have a list of  so-called *breadcrumbs*: links to their parent pages and any higher-level ancestors. They show the breadcrumbs above the main content of the page.

Each page that has child pages generally has a list of links to those pages (you can suppress it by `has_toc: false` in the front matter). It shows the list as a *table of contents* below the main content.

## The `minimal` layout

A child and grandchild page of this page use the minimal layout. This differs from the default layout by omitting the sidebar---and thereby also the navigation panel. To navigate between pages with the minimal layout, you can use the breadcrumbs and the tables of contents.

## Selectively hiding or showing the sidebar

[Jekyll's front matter defaults] can be used to apply the `minimal` layout for many pages. But there are also other variables that can control the page layout. In `_config.yml`, you can set `nav_enabled: false` to disable the sidebar navigation panel across the entire site. This can then be selectively enabled on a page-by-page basis by assigning the `nav_enabled: true` page [front matter] variable. For instance, this could be used to enable sidebar navigation on a home page while all other pages have sidebar navigation disabled.

```yaml
---
layout: default
title: Home
nav_enabled: true
---

```

## Other layouts

Just the Docs has further layouts: `about`, `home`, `page`, and `post`. Currently, they are all based on the `default` layout. See the [Jekyll docs about inheritance] for how to customize them.

[front matter]: https://jekyllrb.com/docs/front-matter/ "Jekyll docs about front matter"
[Jekyll 关于版型的文档页面]: https://jekyllrb.com/docs/layouts/ "Jekyll docs about layouts"
[Jekyll 的默认 front matter]: https://jekyllrb.com/docs/configuration/front-matter-defaults/ "Jekyll docs about front matter defaults"
[Jekyll docs about inheritance]: https://jekyllrb.com/docs/layouts/#inheritance "Jekyll docs about inheritance"

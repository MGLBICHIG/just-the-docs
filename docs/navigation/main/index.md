---
title: 主导航
parent: 导航
nav_order: 1
---

# 主导航

主导航在大屏时显示在你的 Just the Docs 站点的页面左侧，小屏时在顶部（点击后）。

你需要在每页的 Front Matter 中设置 `title`。页面 `title` 独立于文件名和目录结构。导航用页面标题做为连接到其他页的锚点。

默认情况下，所有页面会出现在主导航顶级目录中，并且依页面 `title` 的字母顺序排列。通过进一步为每个页面在 Front Matter 中添加细分字段，你才能[调整它们的顺序]({% link docs/navigation/main/order.md %})，[剔除不想显示页面]({% link docs/navigation/main/exclude.md %})，修正他们的[上层页面]({% link docs/navigation/main/levels.md %})。

{: .new-title }
> 新功能 (始于 v0.10.0)
>
> 主导航可以构建一个不限层级的多层菜单：
> 页面都可以有子页面。

要使导航结构正常工作（避免浏览时的混淆错乱）***站点的页面标题需要满足下列要求：***

* 顶级页面标题必须唯一；
* 同一父页面的子页面标题必须唯一；
* 每个页面标题都不能同它们的子页面标题重复，也不能同它们的子页面标题重复；

{: .new-title }
> 新功能 (始于 v0.10.0)
>
> If *all* the pages of your site have different titles, you need only to specify the `title` of each page, and the `parent` title of each lower-level page.[^1]

[^1]: Previous versions of Just the Docs restricted the navigation to three levels. You also needed to specify `has_children: true` on all parent pages, and a `grand_parent` title on all grandchild pages. The `has_children` parameter is now redundant, and the `grand_parent` parameter can usually be omitted.

If your site has pages with the same title, you need to avoid confusion when you reference that title as `parent` on other pages. When the pages with the same title have different `parent` pages, you can distinguish between them using the `grand_parent` parameter.

{: .new-title }
> 新功能 (始于 v0.10.0)
>
> For deeper navigation structures, you can specify the title of a grandparent or higher level page as an `ancestor` title.

----

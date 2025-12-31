---
title: 定制
nav_order: 6
---

# 定制
{: .no_toc }

## 目录
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## 色系

Just the Docs 支持两个色系（Color Scheme）：亮色系（light）（默认）和暗色系（dark）。

启用一个色系需要在站点的 `_config.yml` 文件中设置 `color_scheme` 参数：

### 示例：预览暗色系
{: .no_toc .text-delta }

```yaml
# 色系支持亮色 "light" (默认) 和 暗色"dark"
color_scheme: dark
```

<button class="btn js-toggle-dark-mode">预览暗色系</button>

<script>
const toggleDarkMode = document.querySelector('.js-toggle-dark-mode');

jtd.addEvent(toggleDarkMode, 'click', function(){
  if (jtd.getTheme() === 'dark') {
    jtd.setTheme('light');
    toggleDarkMode.textContent = '预览暗色系';
  } else {
    jtd.setTheme('dark');
    toggleDarkMode.textContent = '返回亮色系';
  }
});
</script>

### 已废弃： `legacy_light`
{: .d-inline-block .no_toc }

新增 (v0.4.2)
{: .label .label-green }


In Just the Docs version `0.4.2`, we changed the default syntax highlighting theme for the `light` color scheme to have higher contrast. Users who want to use the old highlighting need to explicitly opt-in with the deprecated `legacy_light` color scheme. In a future major release of Just the Docs, we will remove this color scheme.

## 定制色系

### 定义一个色系

You can add custom schemes.
If you want to add a scheme named `foo` (can be any name) just add a file `_sass/color_schemes/foo.scss` (replace `foo` by your scheme name)
where you override theme variables to change colors, fonts, spacing, etc.

{: .note }
Since the default color scheme is `light`, your custom scheme is implicitly based on the variable settings used by the `light` scheme.

If you want your custom scheme to be based on the `dark` scheme, you need to start your file with the following line:

```scss
@import "./color_schemes/dark";
```

You can define custom schemes based on other custom schemes in the same way.

Available variables are listed in the [\_variables.scss](https://github.com/just-the-docs/just-the-docs/tree/main/_sass/support/_variables.scss) file.

For example, to change the link color from the purple default to blue, include the following inside your scheme file:

#### Example: custom link color
{: .no_toc .text-delta }

```scss
$link-color: $blue-000;
```

Keep in mind that changing a variable will not automatically change the value of other variables that depend on it.
For example, the default link color (`$link-color`) is set to `$purple-000`. However, redefining `$purple-000` in a custom color scheme will not automatically change `$link-color` to match it.
Instead, each variable that relies on previously-cascaded values must be manually reimplemented by copying the dependent rules from `_variables.scss` — in this case, rewriting `$link-color: $purple-000;`.

_Note:_ Editing the variables directly in `_sass/support/variables.scss` is not recommended and can cause other dependencies to fail.
Please use scheme files.

### 使用定制色系

To use the custom color scheme, only set the `color_scheme` parameter in your site's `_config.yml` file:

```yaml
color_scheme: foo
```

### 可转换定制色系

If you want to be able to change the scheme dynamically, for example via javascript, just add a file `assets/css/just-the-docs-foo.scss` (replace `foo` by your scheme name)
with the following content:

{% raw %}
    ---
    ---
    {% include css/just-the-docs.scss.liquid color_scheme="foo" %}
{% endraw %}

This allows you to switch the scheme via the following javascript.

```js
jtd.setTheme("foo")
```

## 覆盖和定义新变量
{: .d-inline-block }

New (v0.4.0)
{: .label .label-green }

To define new SCSS variables or functions, place SCSS code in `_sass/custom/setup.scss`. This should *not* be used for defining custom styles (see the next section) or overriding color scheme variables (in this case, you should create a new color scheme).

This is most commonly-used to define [custom callout colors]({% link docs/configuration.md %}#callouts). For example,

```scss
// _sass/custom/setup.scss
$pink-000: #f77ef1;
$pink-100: #f967f1;
$pink-200: #e94ee1;
$pink-300: #dd2cd4;
```

In particular: this file is imported *after* the theme's variables and functions are defined, but *before* any CSS classes are emitted.

## 覆盖和完全定制样式

For styles that aren't defined as SCSS variables, you may want to modify specific CSS classes.
Additionally, you may want to add completely custom CSS specific to your content.
To do this, put your styles in the file `_sass/custom/custom.scss`.
This will allow for all overrides to be kept in a single file, and for any upstream changes to still be applied.

### Example: custom print styles
{: .no_toc .text-delta }

For example, if you'd like to add your own styles for printing a page, you could add the following styles.

```scss
// Print-only styles.
@media print {
  .side-bar,
  .page-header {
    display: none;
  }
  .main-content {
    max-width: auto;
    margin: 1em;
  }
}
```

## 覆盖 includes

你可以通过覆盖主题提供的 [Jekyll includes](https://jekyllrb.com/docs/includes/) 文件来定制主题。

要想覆盖，可以创建 `_includes` 目录，然后拷贝你要定制的文件。文件中的内容将要覆盖掉原来主题的默认文件。更多信息可以参考 Jekyll 文档的[覆盖主题默认文件](https://jekyllrb.com/docs/themes/#overriding-theme-defaults)。

Just the Docs 提供下面可以定制的 includes 文件：

### 定制 TOC 标题
{: .d-inline-block }

新增 (v0.4.0)
{: .label .label-green }

`_includes/toc_heading_custom.html`

如果一个页面有子页面且 `has_toc` 没有设置为 `false`，那么这个内容将出现在[自动生成子页面列表]({% link docs/navigation/children.md %})的顶部，其后为页面内容。

#### 示例：修改 TOC 标题
{: .no_toc }

修改默认 TOC 标题为 "目录"，创建 `_includes/toc_heading_custom.html` 并添加：
```html
<h2 class="text-delta">目录</h2>
```

`text-delta` 类（可选）使标题出现类似 **目录**{:.text-delta} 的效果。

### 定制 Footer

`_includes/footer_custom.html`

此内容出现每页主要内容的底端。更多关于这个 include 的信息可参考[配置 - Footer 内容]({% link docs/configuration.md %}#footer-content)。

### 定制 Head

`_includes/head_custom.html`

添加到此页的任何 HTML 都会在 `<head>` 标签关闭之前插入。这包括 `<meta>`、`<link>`、`<script>` 等。

如果你在配置文件中已经设置了 `favicon_ico` 的路径，`<head>` 标签自动包含一个到已存在的 favicon 的链接，否则路径默认为 `/favicon.ico`。

### 定制 Header

`_includes/header_custom.html`

此文件内容会出现在每页的主要内容和站点搜索之间。如果 `search_enabled` 设置为 `false` 且 `aux_links` 移除，`header_custom.html` 内容将占据每页的顶端。

### 定制 Nav Footer
{: .d-inline-block }

新增 (v0.4.0)
{: .label .label-green }

`_includes/nav_footer_custom.html`

此文件所有内容会出现在页面左侧的导航栏下部。默认显示为 `This site uses Just the Docs, a documentation theme for Jekyll.`。

### 定制搜索占位符
{: .d-inline-block }

新增 (v0.4.0)
{: .label .label-green }

`_includes/search_placeholder_custom.html`

添加到这个文件的内容将替换搜索框默认的占位文字 (and its `aria-label`)，同时去掉 HTML 标签和开始/结尾的空白。默认内容包含：

{% raw %}

```liquid
Search {{site.title}}
```

{% endraw %}

覆盖这个文件重新渲染定制的占位符。常用于国际化，例如

{% raw %}

```liquid
Chercher notre site
```

{% endraw %}

占位符为 "Chercher notre site"。[Liquid 代码](https://jekyllrb.com/docs/liquid/) (支持包含 [Jekyll 变量](https://jekyllrb.com/docs/variables/))。

## 定制 layouts 和 includes
{: .d-inline-block }

新增 (v0.4.0)
{: .label .label-green }

高级
{: .label .label-yellow }

Just the Docs 利用 Jekyll 的高效 [layouts](https://jekyllrb.com/docs/layouts/) 和 [includes](https://jekyllrb.com/docs/includes/) 特色生成和组合各种站点元素。Jekyll 用户和开发者可以扩展或者替换已存在的 layouts 和 includes 来定制整个站点 layout。

### 默认 layout 和可包含组件

`default` 版式被 Just the Docs 的绝大部分“开箱即用”页面继承。它由各种可重用组件构成——sidebar、navbar、footer、breadcrumbs 和各种的导入组件。大部分用户创建新页面或者 layouts 都要从 `default` 继承。

这是一个简化的代码示例：

{% raw %}

```liquid
<!-- a simplified version of _layouts/default.html -->
<html>
{% include head.html %}
<body>
  {% include icons/icons.html %}
  {% include components/sidebar.html %}
  {% include components/header.html %}
  {% include components/breadcrumbs.html %}

  {% if site.heading_anchors != false %}
    {% include vendor/anchor_headings.html html=content ... %}
  {% else %}
    {{ content }}
  {% endif %}

  {% if page.has_children == true and page.has_toc != false %}
    {% include components/children_nav.html %}
  {% endif %}

  {% include components/footer.html %}

  {% if site.search_enabled != false %}
    {% include components/search_footer.html %}
  {% endif %}

  {% if site.mermaid %}
    {% include components/mermaid.html %}
  {% endif %}
</body>
</html>
```

{% endraw %}

#### 组件概述
{: .no_toc }

{: .warning }
Defining a new `_includes` with the same name as any of these components will significantly change the existing layout. Please proceed with caution when adjusting them.

To briefly summarize each component:

- `_includes/head.html` is the entire `<head>` tag for the site; this imports stylesheets, various JavaScript files (ex: analytics, mermaid, search, and Just the Docs code), and SEO / meta information.
- `_includes/icons/icons.html` imports all SVG icons that are used throughout the site. Some, such as those relating to search or code snippet copying, are only loaded when those features are enabled.
- `_includes/components/sidebar.html` renders the sidebar, containing the site header, navigation links, external links, collections, and nav footer.
- `_includes/components/header.html` renders the navigation header, containing the search bar, custom header, and aux links
- `_includes/components/breadcrumbs.html` renders the breadcrumbs feature
- `vendor/anchor_headings.html` is a local copy of Vladimir Jimenez's [jekyll-anchor-headings](https://github.com/allejo/jekyll-anchor-headings) snippet
- `_includes/components/children_nav.html` renders a list of nav links to child pages on parent pages
- `_includes/components/footer.html` renders the bottom-of-page footer
- `_includes/components/search_footer.html` renders DOM elements that are necessary for the search bar to work
- `_includes/components/mermaid.html` initializes mermaid if the feature is enabled

Each of these components can be overridden individually using the same process described in the [Override includes](#override-includes) section. In particular, the granularity of components should allow users to replace certain components (such as the sidebar) without having to adjust the rest of the code.

Future versions may subdivide components further; we guarantee that we will only place them in folders (ex `components/`, `icons/`, or a new `js/`) to avoid top-level namespace collisions.

### 替换 layouts 和示例 (`minimal`)

Users can develop custom layouts that compose, omit, or add components differently. We provide one first-class example titled `minimal`, which disables the navigation sidebar. To see an example, visit the [minimal layout test]({{site.baseurl}}/docs/minimal-test/) page.

Users can indicate this alternative layout in page front matter:

{% raw %}

```
---
layout: minimal
title: Minimal layout test
---
```

{% endraw %}

Similarly, users and developers can create other alternative layouts using Just the Docs' reusable includable components.

### 默认 layout 和继承链

Under the hood,

- `default` inherit from the `table_wrappers` layout, which wraps all HTML `<table>` tags with a `div .table-wrapper`
- `table_wrappers` inherits from `vendor/compress`, which is a local copy of Anatol Broder's [jekyll-compress-html](https://github.com/penibelst/jekyll-compress-html) Jekyll plugin

The `minimal` layout inherits from the `default` but assigns `nav_enabled: false` to disable the navigation sidebar.

### 覆盖默认 Jekyll layouts

By default, Jekyll (and its default theme `minima`) provide the `about`, `home`, `page`, and `post` layouts. In Just the Docs, we override all of these layouts with the `default` layout. Each of those layouts is simply:

{% raw %}

```
---
layout: default
---

{{ content }}
```

{% endraw %}

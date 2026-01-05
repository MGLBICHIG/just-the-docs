---
title: 配置
nav_order: 2
---

# 配置
{: .no_toc }

Just the Docs 是一款基于 Jekyll 软件的主题。所以，有些参数在站点的 Jekyll 配置文件 \_config.yml 中设定。
{: .fs-6 .fw-300 }

## 页面目录
{: .no_toc .text-delta }

1. TOC
{:toc}

---

查看站点的 [\_config.yml](https://github.com/just-the-docs/just-the-docs/tree/main/_config.yml) 文件示例。

## 站点 logo

```yaml
# 设置一个指向站点要显示的 Logo 路径或者 URL，替换原来的站点标题
logo: "/assets/images/just-the-docs.png"
```

## 站点 favicon

```yaml
# 设置要浏览器显示的 favicon 的路径或者 URL
favicon_ico: "/assets/images/favicon.ico"
```

如果站点的 favicon 路径是 `/favicon.ico`，可以不设置，因为系统默认就是。

## 搜索

```yaml
# 启用或者关闭站点搜索
# 支持布尔值 true （默认）或者 false
search_enabled: true

search:
  # 将页面分为可独立搜索的碎片
  # 支持值 1 - 6，默认值是 2
  heading_level: 2
  # 每个搜索结果容许的最多条目数
  # 默认值为 3
  previews: 3
  # 预览命中结果前最多显示单词数目
  # 默认值为 5
  preview_words_before: 5
  # 预览结果命中后最多显示单词数目
  # 默认值为 10
  preview_words_after: 10
  # 设置搜索的词根分割符
  # 默认值为 /[\s\-/]+/
  # 示例：启用连接符号作为检索词
  tokenizer_separator: /[\s/]+/
  # 检索结果中显示相对 URL
  # 支持布尔值 true （默认）或者 false
  rel_url: true
  # 启用或者关闭在每页的右下角出现的搜索按钮
  # 支持布尔值 true 或者 false （默认值）
  button: false
  # 通过按压 `ctrl + focus_shortcut_key` （或在 macOS 系统上的 `cmd + focus_shortcut_key`）聚焦搜索框)
  focus_shortcut_key: 'k'
```

## Mermaid 表
{: .d-inline-block }

新功能 (v0.4.0)
{: .label .label-green }

至少需要在 `_config.yml` 中设置 `version` ([from jsDelivr](https://cdn.jsdelivr.net/npm/mermaid/)) 关键字：

```yaml
mermaid:
  # Mermaid 库的版本
  # 从 https://cdn.jsdelivr.net/npm/mermaid/ 挑选一个可用版本
  version: "9.1.3"
```

如果是从本地文件加载 Mermaid 库需要将关键字 `version` 替换为 `path`。

更多配置信息查阅[代码文档]({% link docs/ui-components/code/index.md %}#mermaid-diagram-code-blocks)。

## Aux links

```yaml
# Aux links 在导航的右上方
aux_links:
  "Just the Docs on GitHub":
    - "//github.com/just-the-docs/just-the-docs"

# 可以使 Aux links 在新标签页打开。默认 false
aux_links_new_tab: false
```

## 边栏导航

```yaml
# 启用或者关闭边栏/移动设备上的菜单
# 导航菜单也可以用页面变量或者采用 minimal 版式或者选择性的启用或者关闭
nav_enabled: true
```

## 标题锚点链接

```yaml
# 标题锚点链接当在页面内容的 h1 到 h6 的标题上悬停时会出现，
# 用于读者在一个页面内需要精准定位到特定标题。
#
# 支持布尔值 true （默认）或者 false
heading_anchors: true
```

## 扩展导航链接
{: .d-inline-block }

新增 (v0.4.0)
{: .label .label-green }

扩展链接可以通过 `nav_external_links` 选项添加到导航。查阅[导航结构]({% link docs/navigation/main/external.md %})获取更多信息。

## Footer 内容

```yaml
# Footer 内容
# 出现在每页主要内容底部
# 注意：footer_content option 选项已经废弃，而且会在将来的主要版本中剔除。推荐使用 `_includes/footer_custom.html`
# 内容基于标记语言 liquid。
footer_content: "Copyright &copy; 2017-2020 Patrick Marsceill. Distributed by an <a href=\"https://github.com/just-the-docs/just-the-docs/tree/main/LICENSE.txt\">MIT license.</a>"

# Footer 最后修改时间戳
last_edit_timestamp: true # 显示或隐藏编辑时间 - 页面必须有 `last_modified_date` 在 frontmatter 中定义
last_edit_time_format: "%b %e %Y at %I:%M %p" # 使用 Ruby 时间格式: https://ruby-doc.org/stdlib-2.7.0/libdoc/time/rdoc/Time.html

# Footer 链接文字"在 GitHub 编辑此页内容"
gh_edit_link: true # 显示或隐藏编辑此页的链接
gh_edit_link_text: "Edit this page on GitHub."
gh_edit_repository: "https://github.com/just-the-docs/just-the-docs" # 你的代码托管库的 GitHug URL
gh_edit_branch: "main" # 你的文档服务分支
# gh_edit_源：docs
# 你的文件来自哪里
gh_edit_view_mode: "tree" # "tree" 或者如果你想让你的用户马上成为编者启用 "edit"
```
{: .note}
_注意：`footer_content` 已经废弃，但是目前仍然支持。为了有更好的体验我们已经将其移入 `_includes/footer_custom.html`，因为这样更能体现体现纯标记和基于 Liquid 的内容_

- "页面最后编辑时间" 数据只有在页面有一个关键词叫做 `last_modified_date` 时显示，格式用某些可读时间格式
- `last_edit_time_format` 使用 Ruby 的 DateTime 格式化输出；示例请参考[官方 Ruby 文档关于 `strftime` 格式](https://docs.ruby-lang.org/en/master/strftime_formatting_rdoc.html)获取更多信息
- `gh_edit_repository` 是项目在 GitHub 仓库的 URL
- `gh_edit_branch` 是文档站点服务的分支，默认为 `main`
- `gh_edit_source` 工程文件存储的源目录（应该同[site.source](https://jekyllrb.com/docs/configuration/options/)一样）
- `gh_edit_view_mode` 默认为 `"tree"`，会带用户进入 GitHub 的页面，转换为 `"edit"` 将带用户进入编辑模式

## 色系

```yaml
# Color scheme supports "light" (default) and "dark"
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

查阅[定制]({% link docs/customization.md %})获取更多信息。

## 标注
{: .d-inline-block }

新增 (v0.4.0)
{: .label .label-green }

{: .note}
Callout 翻译为标注，也不知道是否准确。标注通常是一段类似于引用块的具有彩色标识并且具备警醒作用的文字块。就如对当前这段文字就是。

要使用这个功能，需要为每一种想用的标注配置 `color` 和可选的 `title`，例如：

```yaml
callouts:
  warning:
    title: Warning
    color: red
```

这将启用 `$red-000` 颜色做为标注的背景色，`$red-300` 颜色做为标题和文字块的装饰[^dark]。你可以为一个段落启用 `warning` 标注样式：

```markdown
{: .warning }
A paragraph...
```

[^dark]:
    如果你启用 `dark` 暗色系，这个标注将使用 `$red-300` 颜色作为背景色，`$red-000` 为标题颜色。

颜色 `grey-lt`、`grey-dk`、`purple`、`blue`、`green`、`yellow`、`red` 都是应定义好的；要使用一个自定义颜色，需要在你的 SCSS 文件中定义其从 `000` 到 `300` 层级变化。例如，要使用 `pink`，需要在你的 `_sass/custom/setup.scss` 文件中添加：

```scss
$pink-000: #f77ef1;
$pink-100: #f967f1;
$pink-200: #e94ee1;
$pink-300: #dd2cd4;
```

你可以覆盖掉背景色中默认的 `opacity` 从而设定一个特定的标注，例如：

```yaml
callouts:
  custom:
    color: pink
    opacity: 0.3
```

你可以修改所有标注的默认 opacity (`0.2`)，例如：

```yaml
callouts_opacity: 0.3
```

你可以整体调整标注的级别。`callouts_level` 要么是 `quiet`，要么是 `loud`；`loud` 会增加背景的饱和度和对比度。默认 `quiet` 用于亮色系 `light` 或者定制色系，`loud` 用于 `暗色系`。

查阅[标注]({% link docs/ui-components/callouts.md %})获取更多信息。

## Google 分析

{: .warning }
> [Google Analytics 4 将取代 Universal Analytics](https://support.google.com/analytics/answer/11583528). 从**2023年7月1日**开始，标准 Universal Analytics 属性将停止处理新的点击。你越早迁移，你的历史数据和报告将越早启用 Google Analytics 4。

Universal Analytics (UA) 和 Google Analytics 4 (GA4) 属性都支持。

```yaml
# Google Analytics Tracking (optional)
# Supports a CSV of tracking ID strings (eg. "UA-1234567-89,G-1AB234CDE5")
ga_tracking: UA-2709176-10
ga_tracking_anonymize_ip: true # Use GDPR compliant Google Analytics settings (true/nil by default)
```

### 多 ID
{: .d-inline-block .no_toc }

新增 (v0.4.0)
{: .label .label-green }

本主题支持用逗号隔开的多个 ID。这将有助于顺利从 UA 属性向 GA4 属性迁移，应为可以两者可以同时使用。

```yaml
ga_tracking: "UA-1234567-89,G-1AB234CDE5"
```

## 文档集合

默认情况下，导航和搜索只包括普通[页面](https://jekyllrb.com/docs/pages/)。你也可以使用基于语义分组的 [Jekyll 集合](https://jekyllrb.com/docs/collections/)。

{: .warning }
> 集合文件夹名字用下划线（`_`）开始，例如 `_tests`。如果你省略了这个前缀，你就找不到你的集合了。

例如，把你的测试文件都放入 `_tests` 文件夹，然后创建 `tests` 集合：

```yaml
# 定义 Jekyll 集合
collections:
  # 定义一个叫做 "tests" 的集合，其文档都在 "_tests" 文件夹内
  tests:
    permalink: "/:collection/:path/"
    output: true

just_the_docs:
  # 定义用于 just-the-docs 的集合
  collections:
    # 参考 "tests" 集合
    tests:
      # 设定集合名字
      name: Tests
      # 从导航中去掉集合
      # 支持布尔值 true 或 false (default)
      # nav_exclude: true
      # 导航中的集合能否折叠
      # 支持布尔值 true 或者 false (default)
      # nav_fold: true  # note: this option is new in v0.4
      # 从搜索中去除集合
      # 支持布尔值 true 或 false (default)
      # search_exclude: true
```

导航会显示所有除了集合的页面。

<span>新增 (v0.4.0)</span>{: .label .label-green }
在一个集合的配置中如果包含 `nav_fold: true` 则会**折叠**集合：一个打开符号会跟在集合名字后面，通过点击会显示或隐藏集合的顶级页面。[^js-disabled]

[^js-disabled]: <span>新增 (v0.6.0)</span>{: .label .label-green }
    当 JavaScript 在浏览器中未启用时，因为点击已经不起作用，所以所有折叠的集合会自动展开。（在前一个版本中，导航进入集合需要启用 JavaScript。）
    
你可以使用多个集合。这将在导航中用配置的名字创建分类目录。

```yaml
collections:
  tests:
    permalink: "/:collection/:path/"
    output: true
  tutorials:
    permalink: "/:collection/:path/"
    output: true

just_the_docs:
  collections:
    tests:
      name: Tests
    tutorials:
      name: Tutorials
```

当**所有**页面在一个集合里时，名字将不显示。

导航为每个集合创建一个独立的页面命名空间：一个页面不能同时是不同集合的子页面，或者普通页面。

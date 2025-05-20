---
title: 搜索
nav_order: 7
---

# 搜索
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

Just the Docs 使用 [lunr.js](https://lunrjs.com) 来实现客户端搜索——由 Jekyll 生成 JSON 格式索引。
所有搜索结果以一个自动完成样式界面显示（没有单设的搜索结果页面）。
默认情况下，所有生成的 HTML 页面基于以下信息点进行排序：

- 页面标题
- 页面内容
- 页面 URL

## 在配置中启用搜索

在站点的 `_config.yml` 中启用搜索：

```yaml
# 启用和关闭站点搜索
# 支持 true (默认) 或者 false
search_enabled: true
```

### 搜索力度

页面分成可搜索的章节。章节通过页面标题定义。每个章节可成为一个独立的搜索单元。

```yaml
# 将页面分成可被搜索的独立部分
# 支持 1 - 6, default: 2
search.heading_level: 2
```

### 搜索预览

搜索结果包含有搜索词的章节的预览。

```yaml
# 每个搜索结果的最大预览数
# Default: 3
search.previews: 3

# Maximum amount of words to display before a matched word in the preview
# Default: 5
search.preview_words_before: 5

# Maximum amount of words to display after a matched word in the preview
# Default: 10
search.preview_words_after: 10
```

### 搜索分词器（tokenizer）

默认使用连字符`-`对搜索词进行分词：`gem-based` 等同于 `gem based` 搜索每一个词。允许搜索中使用连字符词：

```yaml
# 设置搜索分词器符号
# Default: /[\s\-/]+/
# 示例：启用连字符搜索词支持
search.tokenizer_separator: /[\s/]+/
```

### 在搜索结果中显示 URL

```yaml
# Display the relative url in search results
# Supports true (default) or false
search.rel_url: false
```

### 显示搜索按钮

搜索按钮在屏幕的右下方，点击可触发搜索。

```yaml
# Enable or disable the search button that appears in the bottom right corner of every page
# Supports true or false (default)
search.button: true
```

### 用键盘快捷键聚焦搜索框

Just the Docs 支持通过键盘快捷键聚焦搜索框。通过设置 `search.focus_shortcut_key` 配置项，用户按压 <kbd>Ctrl</kbd> + `search.focus_shortcut_key` （或者在 macOS 上，<kbd>Command</kbd> + `search.focus_shortcut_key`）将会聚焦到搜索框上。

注意这个功能**默认启用**。`search.focus_shortcut_key` 应该是一个[来自 `KeyboardEvent.key` 的有效值](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/key)；这包括了所有的 ASCII 字母数字值以及修改键值。

例如：

```yaml
search:
    focus_shortcut_key: 'k'
```

将会使得 Windows 用户的 <kbd>Ctrl</kbd> + <kbd>K</kbd> 聚焦到搜索框（macOS 用户为 <kbd>Command</kbd> + <kbd>K</kbd>）。

## 对搜索引擎隐藏

有时有些页面不需要被索引、搜索和出现在搜索结果中，例如 404 页面。
从搜索中除掉这些页面，需要添加 `search_exclude: true` 参数到页面的 YAML front matter 中：

{: .no_toc }

```yaml
---
layout: default
title: Page not found
nav_exclude: true
search_exclude: true
---

```

## 使用 GEM 时生成搜索索引

如果你使用 Just the Docs 做为远程主题，则不需要下面步骤。

如果你使用 GEM 主题，你必须通过运行这个 `rake` 命令结合 `just-the-docs` 来初始化搜索：

```bash
$ bundle exec just-the-docs rake search:init
```

这个命令创建了 `assets/js/zzzz-search-data.json` 文件来创建搜索索引。
另外，你也可以通过参考[这个内容]({{ site.github.repository_url }}/blob/main/assets/js/zzzz-search-data.json)手动创建索引。

## 定制搜索索引内容
{: .d-inline-block }

新功能 (v0.4.0)
{: .label .label-green }

高级
{: .label .label-yellow }

默认情况下，搜索功能索引一个页面的 `.content`、`.title` 和**一些** `.content` 内的标题。其它数据（例如 front matter、`_data` 和 `assets` 中的文件)不会被索引。用户可以定制索引内容。

{: .warning }
> 定制搜索索引是一个需要 Javascript 和 Liquid 知识的高级功能。

1. When Just the Docs is a local or gem theme, ensure `assets/js/zzzz-search-data.json` is up-to-date with [Generate search index when used as a gem](#generate-search-index-when-used-as-a-gem).
2. Add a new file named `_includes/lunr/custom-data.json`. Insert custom Liquid code that reads your data (e.g. the page object at `include.page`) then generates custom Javascript fields that hold the custom data you want to index. Verify these fields in the generated `assets/js/search-data.json`.
3. Add a new file named `_includes/lunr/custom-index.js`. Insert custom Javascript code that reads your custom Javascript fields and inserts them into the search index. You may want to inspect `assets/js/just-the-docs.js` to better understand the code.

### 示例：添加定制的 `usage` 和 `examples` 字段
{: .text-delta }

This example adds front matter `usage` and `examples` fields to the search index.

`_includes/lunr/custom-data.json` custom code reads the page `usage` and `examples` fields, normalizes the text, and writes the text to custom Javascript `myusage` and `myexamples` fields. Javascript fields are similar yet [not the same as JSON](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON#javascript_and_json_differences). `jsonify` will probably work for most scenarios.

{% raw %}
```liquid
{%- capture newline %}
{% endcapture -%}
"myusage": {{ include.page.usage | markdownify | replace:newline,' ' | strip_html | normalize_whitespace | strip | jsonify }},
"myexamples": {{ include.page.examples | markdownify | replace:newline,' ' | strip_html | normalize_whitespace | strip | jsonify }},
```
{% endraw %}

`_includes/lunr/custom-index.js` custom code is inserted into the Javascript loop of `assets/js/just-the-docs.js`. All custom Javascript fields are accessed as fields of `docs[i]` such as `docs[i].myusage`. Finally, append your custom fields on to the already existing `docs[i].content`.

```javascript
const content_to_merge = [docs[i].content, docs[i].myusage, docs[i].myexamples];
docs[i].content = content_to_merge.join(' ');
```

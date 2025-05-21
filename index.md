---
title: 主页
layout: home
nav_order: 1
description: "Just the Docs is a responsive Jekyll theme with built-in search that is easily customizable and hosted on GitHub Pages."
permalink: /
---

# 聚焦编写好文档
{: .fs-9 }

Just the Docs 助力文档快速启动——给你一个易定制的 Jekyll 文档主题且可在 GitHub Pages 免费托管！
{: .fs-6 .fw-300 }

[现在上手](#快速上手){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }
[去 GitHub 查看源码][Just the Docs 代码库]{: .btn .fs-5 .mb-4 .mb-md-0 }

---

{: .warning }
> 当前站点文档的功能就是使用的 Just the Docs 主题的 `main` 分支。查看 [the CHANGELOG]({% link CHANGELOG.md %}) 获取发布清单、新功能及问题修正等。

Just the Docs 是一款利用 [Jekyll] 生成静态网站的软件主题。你可以利用 [Markdown]、[Liquid] 模板语言和 HTML[^1] 编写网页源文件，然后用 Jekyll 转换这些带有 [front matter] 的源文件为 HTML。你的 [Jekyll 配置文件]文件决定使用什么主题、设置你的站点的常用参数等，例如主页的 URL。

Jekyll 构建这个 Just the Docs 主题文档就是使用的自己的主题。这些网页所展示的就是当你使用这个主题时**默认**情况下应该看到的。当然，你可以很容易的通过**[定制]**主题来使其看起来完全不同！

查阅文档学习更多如何使用这个主题。

## 快速上手

[Just the Docs 模板]提供了利用 Just the Docs 主题的最简单、最迅速和最容易的创建站点方式。快速上手创建站点，只需点击“[使用模板]”！

{: .note }
使用本主题，你**不需要**克隆或者复刻 [Just the Docs 代码库]！只有在你需要本地计算机上浏览主题文档、辅助开发主题或者基于 Just the Docs 开发新主题时克隆或者复刻。

你通过发布在 [GitHub Pages] 的模板很容易就能创建站点——[模板 README] 文件解释了如何操作及其他一些细节。

如果你的计算机已经安装了 [Jekyll]，你也可以在**本地**构建和预览创建的站点。这让可以在提交修改前测试预览，从而避免在只有发布到 GitHub Pages 后才能看到修改效果。[^2]当然你也可以部署你在本地构建的站点到 GitHub Pages 以外的平台。

更多创建站点的特殊细节：

- 用基于 GEM 的方法，例如，使用 `Gemfile` 加载 `just-the-docs` GEM
- 在 GitHub Pages 用 [GitHub Pages / Actions workflow] 构建和发布站点

除此以外，你可以根据自己的喜好自由定制用模板创建的站点。你可以很容易的改变所使用的 `just-the-docs` 和 Jekyll 的版本，以及插件等。

{: .note }
查看主题 [README][Just the Docs README] 获取更多使用 GEM 做为主题而不是区创建站点的细节。

## 关于本项目

Just the Docs &copy; 2017-{{ "now" | date: "%Y" }} 由 [Patrick Marsceill](https://patrickmarsceill.com) 所有。

### 许可

Just the Docs 基于 [MIT 许可](https://github.com/just-the-docs/just-the-docs/tree/main/LICENSE.txt) 分发。

### 贡献

当你为软件做贡献时，请首先通过 Issue、电子邮件或者其他方法同代码库管理员讨论你所设想的修改后再做代码完善。更多如何成为一名贡献者的细节参考[我们的 GitHub 代码库](https://github.com/just-the-docs/just-the-docs#contributing)。

#### 诚挚感谢所有的 Just the Docs 的贡献者！

<ul class="list-style-none">
{% for contributor in site.github.contributors %}
  <li class="d-inline-block mr-1">
     <a href="{{ contributor.html_url }}"><img src="{{ contributor.avatar_url }}" width="32" height="32" alt="{{ contributor.login }}"></a>
  </li>
{% endfor %}
</ul>

### 行为准则（Code of Conduct）

Just the Docs 承诺发展为一个友善的社区。

查看在我们的 GitHub 代码库的[行为准则](https://github.com/just-the-docs/just-the-docs/tree/main/CODE_OF_CONDUCT.md)。

----

[^1]: [本页的源文件]使用了三种标记语言。

[^2]: [在 GitHub，十分钟即可完成站点的修改提交发布](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/creating-a-github-pages-site-with-jekyll#creating-your-site)。

[Jekyll]: https://jekyllrb.com
[Markdown]: https://daringfireball.net/projects/markdown/
[Liquid]: https://github.com/Shopify/liquid/wiki
[Front matter]: https://jekyllrb.com/docs/front-matter/
[Jekyll 配置文件]: https://jekyllrb.com/docs/configuration/
[本页的源文件]: https://github.com/just-the-docs/just-the-docs/blob/main/index.md
[Just the Docs 模板]: https://just-the-docs.github.io/just-the-docs-template/
[Just the Docs]: https://just-the-docs.com
[Just the Docs 代码库]: https://github.com/just-the-docs/just-the-docs
[Just the Docs README]: https://github.com/just-the-docs/just-the-docs/blob/main/README.md
[GitHub Pages]: https://pages.github.com/
[Template README]: https://github.com/just-the-docs/just-the-docs-template/blob/main/README.md
[GitHub Pages / Actions workflow]: https://github.blog/changelog/2022-07-27-github-pages-custom-github-actions-workflows-beta/
[定制]: {% link docs/customization.md %}
[使用模板]: https://github.com/just-the-docs/just-the-docs-template/generate

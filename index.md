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
[去 GitHub 查看源码][Just the Docs repo]{: .btn .fs-5 .mb-4 .mb-md-0 }

---

{: .warning }
> 当前站点文档的功能就是使用的 Just the Docs 主题的 `main` 分支。查看 [the CHANGELOG]({% link CHANGELOG.md %}) 获取发布清单、新功能及问题修正等。

Just the Docs 是一款利用 [Jekyll] 生成静态网站的软件主题。你可以利用 [Markdown]、[Liquid] 模板语言和 HTML[^1] 编写网页源文件，然后用 Jekyll 转换这些带有 [front matter] 的源文件为 HTML。你的 [Jekyll configuration] 文件决定使用什么主题、设置你的站点的常用参数等，例如主页的 URL。

Jekyll 构建这个 Just the Docs 主题文档就是使用的自己的主题。这些网页所展示的就是当你使用这个主题时**默认**情况下应该看到的。当然，你可以很容易的通过**[定制]**主题来使其看起来完全不同！

查阅文档学习更多如何使用这个主题。

## 快速上手

[Just the Docs 模板]提供了利用 Just the Docs 主题的最简单、最迅速和最容易的创建站点方式。快速上手创建站点，只需点击“[使用模板]”！

{: .note }
使用本主题，你**不需要**克隆或者复刻[Just the Docs repo]！只有在你需要本地计算机上浏览主题文档、辅助开发主题或者基于 Just the Docs 开发新主题时克隆或者复刻。

You can easily set the site created by the template to be published on [GitHub Pages] – the [template README] file explains how to do that, along with other details.

If [Jekyll] is installed on your computer, you can also build and preview the created site *locally*. This lets you test changes before committing them, and avoids waiting for GitHub Pages.[^2] And you will be able to deploy your local build to a different platform than GitHub Pages.

More specifically, the created site:

- uses a gem-based approach, i.e. uses a `Gemfile` and loads the `just-the-docs` gem
- uses the [GitHub Pages / Actions workflow] to build and publish the site on GitHub Pages

Other than that, you're free to customize sites that you create with the template, however you like. You can easily change the versions of `just-the-docs` and Jekyll it uses, as well as adding further plugins.

{: .note }
See the theme [README][Just the Docs README] for how to use the theme as a gem without creating a new site.

## About the project

Just the Docs is &copy; 2017-{{ "now" | date: "%Y" }} by [Patrick Marsceill](https://patrickmarsceill.com).

### License

Just the Docs is distributed by an [MIT license](https://github.com/just-the-docs/just-the-docs/tree/main/LICENSE.txt).

### Contributing

When contributing to this repository, please first discuss the change you wish to make via issue,
email, or any other method with the owners of this repository before making a change. Read more about becoming a contributor in [our GitHub repo](https://github.com/just-the-docs/just-the-docs#contributing).

#### Thank you to the contributors of Just the Docs!

<ul class="list-style-none">
{% for contributor in site.github.contributors %}
  <li class="d-inline-block mr-1">
     <a href="{{ contributor.html_url }}"><img src="{{ contributor.avatar_url }}" width="32" height="32" alt="{{ contributor.login }}"></a>
  </li>
{% endfor %}
</ul>

### Code of Conduct

Just the Docs is committed to fostering a welcoming community.

[View our Code of Conduct](https://github.com/just-the-docs/just-the-docs/tree/main/CODE_OF_CONDUCT.md) on our GitHub repository.

----

[^1]: [本页的源文件]使用了三种标记语言。

[^2]: [It can take up to 10 minutes for changes to your site to publish after you push the changes to GitHub](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/creating-a-github-pages-site-with-jekyll#creating-your-site).

[Jekyll]: https://jekyllrb.com
[Markdown]: https://daringfireball.net/projects/markdown/
[Liquid]: https://github.com/Shopify/liquid/wiki
[Front matter]: https://jekyllrb.com/docs/front-matter/
[Jekyll configuration]: https://jekyllrb.com/docs/configuration/
[本页的源文件]: https://github.com/just-the-docs/just-the-docs/blob/main/index.md
[Just the Docs 模板]: https://just-the-docs.github.io/just-the-docs-template/
[Just the Docs]: https://just-the-docs.com
[Just the Docs repo]: https://github.com/just-the-docs/just-the-docs
[Just the Docs README]: https://github.com/just-the-docs/just-the-docs/blob/main/README.md
[GitHub Pages]: https://pages.github.com/
[Template README]: https://github.com/just-the-docs/just-the-docs-template/blob/main/README.md
[GitHub Pages / Actions workflow]: https://github.blog/changelog/2022-07-27-github-pages-custom-github-actions-workflows-beta/
[定制]: {% link docs/customization.md %}
[使用模板]: https://github.com/just-the-docs/just-the-docs-template/generate

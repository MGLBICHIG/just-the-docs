---
title: Markdown 用法展示
nav_order: 99
---

<button class="btn js-toggle-dark-mode">预览暗色模式</button>

<script>
const toggleDarkMode = document.querySelector('.js-toggle-dark-mode');

jtd.addEvent(toggleDarkMode, 'click', function(){
  if (jtd.getTheme() === 'dark') {
    jtd.setTheme('light');
    toggleDarkMode.textContent = '预览暗色模式';
  } else {
    jtd.setTheme('dark');
    toggleDarkMode.textContent = '返回亮色模式';
  }
});
</script>

文字可以是**粗体**，_斜体_，或者~~删除线~~。

[链接到其它页面]({{site.baseurl}}/)。

通过空白行生成段落。

段落之间应该有空白行。我们推荐要有一个 README，或者其他有关你的项目的说明文件。

# 1 级标题

这是一个跟随标题的普通段落。GitHub 是一个版本控制和集散的代码托管平台——它让你和其他来自世界各地的开发人员共同参与一个项目的开发。

## 2 级标题

> 这是一个跟随标题的块引用。
>
> 当有些东西很重要时，即使明知不可为也必为。

### 3 级标题

```js
// Javascript code with syntax highlighting.
var fun = function lang(l) {
  dateformat.i18n = require('./lang/' + l)
  return true;
}
```

```ruby
# Ruby code with syntax highlighting
GitHubPages::Dependencies.gems.each do |gem, version|
  s.add_dependency(gem, "= #{version}")
end
```

#### `带有不转换代码的` 4 级标题

*   This is an unordered list following a header.
*   This is an unordered list following a header.
*   This is an unordered list following a header.

##### 5 级标题

1.  This is an ordered list following a header.
2.  This is an ordered list following a header.
3.  This is an ordered list following a header.

###### 6 级标题

[This is a very long link which wraps and therefore doesn't overflow
even when it comes at the beginning](.) of the line.

- [This is a very long link which wraps and therefore doesn't overflow the line
  when used first in an item ](.) in a list.

| head1        | head two          | three |
|:-------------|:------------------|:------|
| ok           | good swedish fish | nice  |
| out of stock | good and plenty   | nice  |
| ok           | good `oreos`      | hmm   |
| ok           | good `zoute` drop | yumm  |

### 下面这是一个水平线

* * *

### 这是一个无序列表：

*   Item foo
*   Item bar
*   Item baz
*   Item zip

### 这是有序列表：

1.  Item one
1.  Item two
1.  Item three
1.  Item four

### 有一个有序列表，继续：

1.  Item one
1.  Item two

Some text

{:style="counter-reset:none"}
1.  Item three
1.  Item four

### 一个从 42 开始的有序列表：

{:style="counter-reset:step-counter 41"}
1.  Item 42
1.  Item 43
1.  Item 44

### 和一个内嵌列表：

- level 1 item
  - level 2 item
  - level 2 item
    - level 3 item
    - level 3 item
- level 1 item
  - level 2 item
  - level 2 item
  - level 2 item
- level 1 item
  - level 2 item
  - level 2 item
- level 1 item

### 嵌入 ol 到 ul 到 ol

- level 1 item (ul)
  1. level 2 item (ol)
  1. level 2 item (ol)
    - level 3 item (ul)
    - level 3 item (ul)
- level 1 item (ul)
  1. level 2 item (ol)
  1. level 2 item (ol)
    - level 3 item (ul)
    - level 3 item (ul)
  1. level 4 item (ol)
  1. level 4 item (ol)
    - level 3 item (ul)
    - level 3 item (ul)
- level 1 item (ul)

### 和一个任务列表

- [ ] Hello, this is a TODO item
- [ ] Hello, this is another TODO item
- [x] Goodbye, this item is done

### 嵌入任务列表

- [ ] level 1 item (task)
   - [ ] level 2 item (task)
   - [ ] level 2 item (task)
- [ ] level 1 item (task)
- [ ] level 1 item (task)

### 嵌入一个 ul 到一个任务列表

- [ ] level 1 item (task)
   - level 2 item (ul)
   - level 2 item (ul)
- [ ] level 1 item (task)
- [ ] level 1 item (task)

### 嵌入一个任务列表到一个无序列表

- level 1 item (ul)
   - [ ] level 2 item (task)
   - [ ] level 2 item (task)
- level 1 item (ul)
- level 1 item (ul)

### 小图

![](../../assets/images/small-image.jpg)

### 大图

![](../../assets/images/large-image.jpg)

"[Wroclaw University Library digitizing rare archival texts](https://www.flickr.com/photos/97810305@N08/9401451269)" by [j_cadmus](https://www.flickr.com/photos/97810305@N08) is marked with [CC BY 2.0](https://creativecommons.org/licenses/by/2.0/?ref=openverse).

### 标签

I'm a label
{: .label }

blue
{: .label .label-blue }
green
{: .label .label-green }
purple
{: .label .label-purple }
yellow
{: .label .label-yellow }
red
{: .label .label-red }

**bold**
{: .label }
*italic*
{: .label }
***bold + italic***
{: .label }

### 用 HTML 语法写定义列表

<dl>
<dt>Name</dt>
<dd>Godzilla</dd>
<dt>Born</dt>
<dd>1952</dd>
<dt>Birthplace</dt>
<dd>Japan</dd>
<dt>Color</dt>
<dd>Green</dd>
</dl>

#### 多术语和释义

Term
: Brief description of Term

Longer Term
: Longer description of Term,
  possibly more than one line

Term
: First description of Term,
  possibly more than one line

: Second description of Term,
  possibly more than one line

Term1
Term2
: Single description of Term1 and Term2,
  possibly more than one line

Term1
Term2
: First description of Term1 and Term2,
  possibly more than one line

: Second description of Term1 and Term2,
  possibly more than one line

### 更多代码

```python{% raw %}
def dump_args(func):
    "This decorator dumps out the arguments passed to a function before calling it"
    argnames = func.func_code.co_varnames[:func.func_code.co_argcount]
    fname = func.func_name
    def echo_func(*args,**kwargs):
        print fname, ":", ', '.join(
            '%s=%r' % entry
            for entry in zip(argnames,args) + kwargs.items())
        return func(*args, **kwargs)
    return echo_func

@dump_args
def f1(a,b,c):
    print a + b + c

f1(1, 2, 3)

def precondition(precondition, use_conditions=DEFAULT_ON):
    return conditions(precondition, None, use_conditions)

def postcondition(postcondition, use_conditions=DEFAULT_ON):
    return conditions(None, postcondition, use_conditions)

class conditions(object):
    __slots__ = ('__precondition', '__postcondition')

    def __init__(self, pre, post, use_conditions=DEFAULT_ON):
        if not use_conditions:
            pre, post = None, None

        self.__precondition  = pre
        self.__postcondition = post
{% endraw %}```

```
Long, single-line code blocks should not wrap. They should horizontally scroll if they are too long. This line should be long enough to demonstrate this.
```

### Mermaid 图表

当 `mermaid` 值在 `_config.yml` 中设定后，下面的代码会展示一个图表。

```mermaid
graph TD;
    accTitle: the diamond pattern
    accDescr: a graph with four nodes: A points to B and C, while B and C both point to D
    A-->B;
    A-->C;
    B-->D;
    C-->D;
```

### 折叠内容

下面使用 [`<details>`](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/organizing-information-with-collapsed-sections) 标记创建一个可折叠内容。

<details markdown="block">
<summary>购物清单（点击我！）</summary>

这是一个置于`<details>`下拉菜单内的内容。

- [ ] 苹果
- [ ] 橘子
- [ ] 牛奶

</details>

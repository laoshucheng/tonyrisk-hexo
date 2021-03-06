---
title: Markdown Cheatsheet
tags: [markdown]
---

参考：

1. [markdown](http://daringfireball.net/projects/markdown/)
2. [Github 风格 Markdown](https://help.github.com/categories/writing-on-github/)

说明：

- markdown 块元素之间用空行来识别
- 基本上 markdown 语法互相之间都能嵌套，更多玩法自己 `try it out`
- markdown 在不同解释器上表现可能不一致（特别是扩展语法，如表格等）
- 反斜杠 `\` 用来转义

<!-- more -->

# 基本语法

## 标题

| 语法 | example | 效果 |
| --- | --- | --- |
| `#` | `# 我是第一标题` | <h1>我是第一标题</h1> |
| `##` | `## 我是第二标题` | <h2>我是第二标题</h2> |
| ... | ... | ... |
| `######` | `###### 我是第六标题` | <h6>我是第六标题</h6> |

## 分割线

| 语法 | example | 效果 |
| --- | --- | --- |
| `--`/`---`/`***` | `--` | <hr> |

## 列表

| 语法 | example | 效果 | 说明 |
| --- | --- | --- | --- |
| `-` / `+` / `*` | `- xxxxx` <br/> `- yyyyy` | <ul><li>xxxxx</li><li>yyyyy</li></ul> | 可以自我嵌套 |
| `1.` / `2.` / `3.` | `1. 111` <br/> `2. 222` <br/> `3. 333` | <ol><li>111</li><li>222</li><li>333</li></ol> | 可以自我嵌套 |

**【注】**
- *无序列表和有序列表可以互相嵌套*
- *列表的项目如果加了空行则在解析时项目中的内容会被 `<p>` 标签包起来*
- *行首出现`数字-句点-空白`组合，要避免被解析，你可以在句点前面加上反斜杠 `\`, 如： `1993\. dddd`*

## 引用
| 语法 | example | 效果 | 说明 |
| --- | --- | --- | --- |
| `>` | `> 文字` | 见下面 | 引用之间还可以嵌套 |

> 文字
> > 嵌套1
> > > 嵌套2

## 代码块

| 语法 | example | 效果 | 说明 |
| --- | --- | --- | --- |
| `[TAB]` | `[TAB] 代码块` | 如下 | 如果在和其他元素嵌套的时候要多相应 `[TAB]` |
| \`\`\`（语言）\`\`\` | \`\`\` ruby <br/> 代码块2 <br/>\`\`\` | 如下 | 推荐使用 |
| \` code  \` | \`行内代码\` | `行内代码` | 一般也用来标记引用 |


	代码快1


``` ruby
代码块2
```

## 块内元素
| 语法 | example | 效果 | 说明 |
| --- | --- | --- | --- |
| `_` | `_文字_` | _文字_ | 下划线 |
| `*` | `*文字*` | *文字* | 斜体 |
| `**` / `__` | `**文字**` | **文字** | 粗体 |
| `~~` | `~~文字~~` | ~~文字~~ | 删除线 |

**【注】**

- *以上语法都可以互相嵌套*

## 链接
| 语法 | example | 效果 | 说明 |
| --- | --- | --- | --- |
| `[文字](url "title")` | `[百度](https://www.baidu.com "首页")` | [百度](https://www.baidu.com "首页") | 链接 |
| `![Alt text](/path/to/img.jpg "Optional title")` | `![示例图片](http://y0.ifengimg.com/dbcc8e45854c158f/2014/0114/rdn_52d4f3b6cbbc9.jpg "示例标题")` | ![示例图片](http://y0.ifengimg.com/dbcc8e45854c158f/2014/0114/rdn_52d4f3b6cbbc9.jpg "示例标题") | 图片 |

# Github Style 语法

## 任务列表

| 语法 | example | 效果 | 说明 |
| --- | --- | --- | --- | --- |
| `- [] task text` | `- [x] task text` | 如下 | 一般在 github 里支持 |

## 表格
| 左对齐 Title | 居中对齐 | 右对齐 Title |
| :--- | :---: | ---: |
| 左对齐 | 居中 | 右对齐 |

---------- EOF ----------

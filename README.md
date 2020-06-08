git# tinybg

#### 介绍
极小的个人博客网站实现。总共不到五百行的后台代码，实现一简约清新的个人博客网站。

预览地址：http://121.36.253.86/,

或域名访问: http://yangqq.xyz

但功能也不弱，支持文章的分页展示，表格，图片和代码语法高亮，文章分类，按访问量统计，按时间和按点击量排序，展示最新文章，最热文章，文章留言评论，最新评论等功能。

获得了阮一峰的科技爱好者周刊（第 109 期 https://mp.weixin.qq.com/s/0GHTm6hToNzPTtQMcEZalw ）推荐。

Go语言爱好者周刊：第 45 期（https://mp.weixin.qq.com/s/7HBSRCeEmPMUszyXnYZuxw ）推荐。

后台使用了Golang+ Gin web框架,整个后台代码就一个main.go。

使用github.com/radovskyb/watcher，监控文件目录改变。

前端使用了流行的markdown-it(MarkDown渲染),highlight.js（语法高亮）和mermaid.js（画流程图、时序图等的js库）组件。

博客介绍地址:https://blog.csdn.net/yyz_1987/article/details/106228599

三两天的业余时间能够快速的实现，得益于站在巨人的肩膀上选择合适的利器为我所用。

留言评论界面爬取自网络大神阮一峰的个人博客界面样式，改了过来。

如果你也想拥有一个属于自己的个性博客，这种尝试将大幅降低准入门槛，让你看到实现一个个人博客网站是多么的简单。

其它的又是建库建表，或是需要登录管理后台管理的，我还是觉得不够简单好用。写篇文章就要登录后台在网页上现场发挥编辑一遍吗？如果写着写着忘词了咋办？保存为草稿下次来过？

而这种思路写博客就是在电脑上写好md格式的文章后往目录丢写好的md文件，一样达到同样的目的，唯一需要熟悉下mardown的写法和遵循一定的格式。且可以提前在电脑上写好md的文章，等想要发布时，一次发布多个文件也可以。

软件架构 软件架构说明，参见个人博客：http://blog.csdn.net/yyz_1987
最新维护地址：https://gitee.com/yyz116/tinybg

安装教程 直接执行 go run main.go即可。 或者go bulid main.go 后，把可执行文件main跑起来即可。

使用说明 直接执行 go run main.go即可，无需建库，建表。使用超级简单。

唯一需要注意的是，需要熟悉markdown文档的写法。并且，写的格式要符合特定要求。

文件名称可以任意，不要有空格即可。

前6行必须按这个格式写，分别是 文章标题，日期，简介，头部展示图片，文章分类，作者。后面的才是为文章内容。

发布时，只需要把test.md 文件提交到后台/posts目录即可。这样便完成了文章的发布。

至于提交的方式有很多，比如我计划跟微信的个人公众号打通，发布文章就是往聊天窗口丢md文件。前台留言自动推送到我的个人公众号中。 想建一个新的文章分类怎么办？文章中的头部信息中，即第四行，指定一个新分类名字即可。 
如以下， test1.md文件内容:

```
现在，我相信爱情！
2020-09-29
我希望我的爱情是这样的，相濡以沫，举案齐眉，平淡如水。我在岁月中找到他，依靠他，将一生交付给他。做他的妻子，他孩子的母亲，为他做饭，洗衣服，缝一颗掉了的纽扣。然后，我们一起在时光中变老。
03.jpg
随笔
yangyongzhen


茫茫人海里遇见一个人有多难？有时候很难，几十亿人，一生也难见一次。有时却很容易，人群中第一眼就能把他认出来。我们总在不设防的时候喜欢上一些人。没什么原因，也许只是一个温和的笑容，一句关切的问候。可能未曾谋面，可能志趣并不相投，可能不在一个高度，却牢牢地放在心上了。冥冥中该来则来，无处可逃，就好像喜欢一首歌，往往就因为一个旋律或一句打动你的歌词。喜欢或者讨厌，是让人莫名其妙的事情。

居中的图片: ![Alt](/assets/images/03.jpg)
Name    | Age
--------|------
Bob     | 27
Alice   | 23

你好！ 这是你第一次使用 **Markdown编辑器** 所展示的欢迎页。如果你想学习如何使用Markdown编辑器, 可以仔细阅读这篇文章，了解一下Markdown的基本语法知识。

```golang
package main

import "fmt"

func main() {
	fmt.Println("hello ")
}
```
```

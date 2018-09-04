# 以Dubbo为例，聊聊如何向开源项目做贡献
---

Github 上有众多优秀的开源项目，大多数 IT 从业者将其当做了予取予求的工具库，遇到什么需求，先去 Github 搜一把，但有没有想过有一天自己也可以给开源事业做一些贡献呢？本文将会以 incubator-dubbo 项目为例，向你阐释，给开源项目做贡献并不是一件难事。

## 1 为何要给开源贡献力量

为开源项目做贡献得到的收益是多方面的，为了让你有足够的信心加入到开源项目中，我在文章最开始列举出它的诸多好处。

### 1.1 巩固技能

无论你是提交代码，撰写文档，提交 Issue，组织活动，当你切身参与到一个开源项目中，相关的技能都会得到历练，并且在开源项目中找到自己的位置。一方面，日常工作中我们中的大多数人接触到的是业务场景，并没有太多机会接触到基础架构组件，开源项目为我们提供了一个平台，在这里，你可以尽情挑选自己熟悉的项目为它添砖加瓦（以 Dubbo 为例，并不是所有 IT 公司都有能力自研服务治理框架）；另一方面，你所提交的代码，会有管理员协助审核，他们会给出专业的建议，更好的代码规范以及更优的编程思路最终都会变成你的经验。

### 1.2 结交朋友

开源社区为你提供了一个平台，在这里，你可以认识很多纯粹的技术爱好者，开源贡献者是最符合 geek 定义的那群人，你所接触到的往往是某个领域最厉害的那批人。

### 1.3 建立口碑

这是一个很好的展示个人实力的地方，俗话说：talk is cheap，show me the code. 作为技术人员，没有什么比一个漂亮的 Github 主页更有说服力的了。如果你能够为开源项目做出可观的贡献，你也将收获到业界的知名度，此时开源项目的成就和你是密不可分的。

### 1.4 传承开源精神

只有源源不断的贡献者给开源项目添砖加瓦，才可以为 Github 一类的开源社区形成良好的开源风气。否则，只有输出没有输入，开源会失去活力。

### 1.5 养成习惯

相信我，一旦养成了每天提交代码的习惯，就像你不想中断打卡一样，你绝不想中断 commit。不止有英语打卡，健身打卡，还有开源打卡！

![开源程序员的日常](http://ov0zuistv.bkt.clouddn.com/image-20180827141007663.png)

## 2 贡献代码时的一些疑难杂症

如果你是一名开源界的新手，可能会对贡献的流程心生畏惧。比如：我该怎么修改代码并提交？我的代码要是存在bug怎么办？我的代码别人会不会很 low？我该如何寻找合适的开源项目？开源社区那么多的工具和词汇都是什么意思？

文章的第二部分将从一个**小白**的角度，介绍一下开源中的一些常见问题。

### 2.1 git 常规操作

一般而言，我们选择使用 git 来作为版本管理的工具，你不一定要非常熟练的使用它，在我看来掌握 clone，add，commit，pull，push 即可，遇到复杂的场景，你还有谷歌。

**fork 与 clone**

![fork 与 clone](http://ov0zuistv.bkt.clouddn.com/image-20180827143942178.png)

如果你只是想下载源码，查看他的源码实现，使用 Clone or download 按钮即可。

如果你想要给开源项目做改动，并且最终请求合并，让开源项目存在你贡献的代码，就应该使用 fork。

fork 将会复制一份当前主分支的代码进入到你的仓库中，之后你所有的修改，应当基于自己的仓库进行，在功能开发/bug 修复之后，可以使用你的仓库向源仓库提交 pull request。只有源仓库的管理员才有权利合并你的请求。

一些可能对你有帮助的高级指令。

```shell
# 设置源仓库
git remote add upstream https://github.com/apache/incubator-dubbo.git
# 拉取源仓库的更新
git fetch upstream
# 将自己仓库的主分支合并源仓库的更新
git checkout master
git merge upstream/master
```

**pull request**

![pull request](http://ov0zuistv.bkt.clouddn.com/image-20180827150703869.png)

pull request 经常被缩写为 PR，指的是一次向源仓库请求合并的行为，如上是我 fork 了 incubator-dubbo 的仓库之后才存在的操作按钮。

**源仓库视角的 pull request**

![pull request management](http://ov0zuistv.bkt.clouddn.com/image-20180827155239155.png)

管理者会对 pull request 涉及的改动进行 review，以确保你的代码是符合规范的，逻辑有没有偏差，以及符合框架的功能需求。

### 2.2 Travis CI

一些自动化的 CI 流程被植入在每一次 pull request 的构建之中，用于给开源仓库去校验提交者的代码是否符合既定的规范，如：是否有编译问题，单元测试是否通过，覆盖率是否达标，代码风格是否合规等等。

![CI报告](http://ov0zuistv.bkt.clouddn.com/image-20180827160503114.png)

一般情况下，必须通过 CI，你的 pull request 才会被管理 review。

### 2.3 Mailing list

每个开源项目都会有自己的贡献规范，可以参考首页的 Contributing，来获取具体的信息。incubator-dubbo 作为一个孵化中的 apache 项目，遵守了 apache 的传统，在 [Contributing](https://github.com/apache/incubator-dubbo/blob/master/CONTRIBUTING.md) 中描述道：当你有新特性想要贡献给 Dubbo 时，官方推荐使用 Mailing list 的方式描述一遍你想要做的改动。

Mailing list 简单来说，就是一个邮件通知机制，所有的 Dubbo 开发者都会订阅该邮箱：dev@dubbo.incubator.apache.org。有任何新特性的改动，或者什么建议想要通知其他开发者，都可以通过向该邮箱发送邮件来达到这个目的，相同地，你也会收到其转发的其他开发者的邮件。

或者你是一个 Dubbo 的使用者，你想要得知开发者的改造方向，也可以订阅，这个[指南](https://github.com/apache/incubator-dubbo/wiki/Mailing-list-subscription-guide)可以帮助你订阅 Dubbo 的 Mailing list。

> 作为一个 modern developer，你可能觉得 mailing list 的交流方式存在滞后性，这样的沟通方式不是特别的高效，但它作为 apache 项目的推荐交流方式存在其特殊的原因，在此不多赘述。总之遵循一个原则：bug fix或者讨论，可以在 github issue 中进行，影响较大的特性和讨论则推荐在 mailing list 中展开。

## 3 其他贡献形式

不仅仅只有贡献代码，修复 bug 等行为才算作为开源做贡献，以下这些行为也属于主要形式：

### 3.1 撰写文档

 [Dubbo文档](http://dubbo.apache.org/zh-cn/)是其开源组成成分的重要一环，其内容源文件位于：https://github.com/apache/incubator-dubbo-website。同样也是一个 Git 仓库，任何你想要对 dubbo 知识点的补充，都可以在这儿提交 pull request，只需要一些 markdown 的语法知识，和一些可有可无的 npm 语法即可。如果你觉得贡献代码对于现在的自己仍然有点难度，不妨从贡献文档开始接触开源。

### 3.2 ISSUE

无论是 Github 中的 Issue 还是 mailing list 中的讨论，无论是提出问题，汇报 bug，还是回答问题（bugfix 则不仅仅需要 Issue 了），协助管理者 review pull request，都是贡献的一种形式，勿以善小而不为。

### 3.3 其他行为

任何你能够想到的，可以帮助开源项目变得更好的的行为，都属于开源贡献。例如，给每个 Issue 打上合适的 tag，关闭重复的 Issue，链接相关联的 Issue，线下组织沙龙，回答 Stack Overflow 上相关的问题，以及文档中一个错别字的修改等等。

## 4 开源最佳实践

### 4.1 有效沟通

无论你处于什么样的目的：仅仅是一次性的贡献，亦或是永久性的加入社区，都的和他人进行沟通和交往，这是你要在开源圈发展必须修炼的技能。

在你开启一个isse或PR之前，或者是在聊天室问问题之前，请牢记下面所列出的几点建议，会让你的工作更加的高效。

**给出上下文** 以便于让其他人能够快速的理解。比方说你运行程序时遇到一个错误，要解释你是如何做的，并描述如何才能再现错误现象。又比方说你是提交一个新的想法，要解释你为什么这么想，对于项目有用处吗（不仅仅是只有你！）

> 😇 *“当我做 Y 的时候 X 不能工作”*
>
> 😢 *“X 出问题! 请修复它。”*

**在进一步行动前，做好准备工作。** 不知道没关系，但是要展现你尝试过、努力过。在寻求帮助之前，请确认阅读了项目的 README、文档、问题（开放的和关闭的）、邮件列表，并搜索了网络。当你表现出很强烈的求知欲的时候，人们是非常欣赏这点的，会很乐意的帮助你。

> 😇 *“我不确定 X 是如何实现的，我查阅了相关的帮助文档，然而毫无所获。”*
>
> 😢 *“我该怎么做 X ?”*

**保持请求内容短小而直接。** 正如发送一份邮件，每一次的贡献，无论是多么的简单，都是需要他人去查阅的。很多项目都是请求的人多，提供帮助的人少。相信我，保持简洁，你能得到他人帮助的机会会大大的增加。

> 😇 *“我很乐意写 API 教程。”*
>
> 😢 *” 有一天我驾驶汽车行驶在高速公路上，在某个加油站加油的时候，突发奇想，我们应该这么做，不过在我进一步解释之前，我先和大家展示一下。。。”*

**让所有的沟通都是在公开场合下进行。** 哪怕是很不起眼的小事，也不要去给维护者发私信，除非是你要分享一些敏感信息（诸如安全问题或严重的过失）。你若能够保持谈话是公开的，很多人可以你们交换的意见中学习和受益。

> 😇 *(评论) “@维护者 你好！我们该如何处理这个PR？”*
>
> 😢 *(邮件) “你好，非常抱歉给发信，但是我实在很希望你能看一下我提交的PR。”*

**大胆的提问（但是要谨慎！）。** 每个人参与社区，开始的时候都是新手，哪怕是非常有经验的贡献者也一样，在刚进入一个新的项目的时候，也是新手。出于同样的原因,甚至长期维护人员并不总是熟悉一个项目的每一部分。给他们同样的耐心,你也会得到同样的回报。

> 😇 *“感谢查看了这个错误，我按照您的建议做了，这是输出结果。”*
>
> 😢 *“你为什么不修复我的问题？这难道不是你的项目吗？”*

**尊重社区的决定。** 你的想法可能会和社区的优先级、愿景等有差异，他们可能对于你的想法提供了反馈和最后的决定的理由，这时你应该去积极的讨论，并寻求妥协的办法，维护者必须慎重的考虑你的想法。但是如果你实在是不能同意社区的做法，你可以坚持自己！保持自己的分支，或者另起炉灶。

> 😇 *“你不能支持我的用例，我蛮失望，但是你的解释仅仅是对一小部分用户起作用，我理解是为什么。感谢你的耐心倾听。”*
>
> 😢 *“你为什么不支持我的用例？这是不可接受的！”*

**以上几点，要铭记在心。** 开源是由来自世界各地的人们共同协作实现的。面临的问题是跨语言、跨文化、不同的地理为止、不同的时区，另外，撰写文字的沟通更是难上加难，无法传达语气和情绪。请让这些会话都充满善意吧！在以下情形中请保持礼貌：推动一个想法、请求更多的上下文、进一步澄清你的立场。既然你在互联网找到了自己的所需，那么请尝试让它变得更好！

### 4.2 创建 issue

你应该在遇到下列情况下，去创建一个 issue：

- 报告你自己无法解决的错误
- 讨论一个高级主题或想法
- 期望实现某新的特性，或者其它项目的想法

在 issue 的沟通中几点实用的技巧:

- **如果你刚好看到一个开放的issue，恰是你打算解决的，** 添加评论，告诉他人你将对此展开工作，并及时响应。这样的话，可以避免他人重复劳动。
- **如果说某个issue已经开放很久了，** 这可能是已经有人正在解决中，又或者是早已经解决过了，所以也请添加评论，在打算开始工作之前，最好是确认一下。
- **如果你创建了一个issue，但是没多久自己解决了，** 也要添加评论，让其他人知道，然后关闭该issue。记录本身就是对社区的贡献。

### 4.3 创建 pull request

在下面的情形时，请你务必使用 PR：

- 提交补丁 (例如，纠正拼写错误、损坏的链接、或者是其它较明显的错误）
- 开始一项别人请求的任务，或者是过去在issue中早就讨论过的

一个 PR 并不代表着工作已经完成。它通常是尽早的开启一个PR，是为了其他人可以观看或者给作者反馈意见。只需要在子标题标记为“WIP”（正在进行中）。作者可以在后面添加很多评论。

如果说项目是托管在 GitHub上的，以下是我们总结出的提交RP的建议：

- **Fork 代码仓库** 并克隆到本地，在本地的仓库配置“上游”为远端仓库。这样你可以在提交你的PR时保持和“上游”同步，会减少很多解决冲突的时间。(更多关于同步的说明，请参考[这里](https://help.github.com/articles/syncing-a-fork/).)
- **创建一个分支** 用于自己编辑。
- **参考任何相关的issue** 或者在你的RP中支持文档(比如. “Closes #37.”)
- **包含之前和之后的快照** 如果你的改动是包含了不同的 HTML/CSS。在你的PR中拖拉相应的图片。
- **测试你的改动！** 若测试用例存在的话，跑一遍，以覆盖你的更改，若没有的话，则创建相应的用例。无论测试是否存在，一定要确保你的改动不会破坏掉现有的项目。
- **和项目现有的风格保持一致** 尽你最大的努力，这也就是意味着在使用缩进、分号、以及注释很可能和你自己的风格大相径庭，但是为了节省维护者的精力，以及未来他人更好的理解和维护，还请你容忍一下。

## 5 成为一个开源贡献者

如果你有志于参与开源事业，可以尝试从自己最熟悉的项目开始，开源并不是属于高级开发者的专属词汇，它就是由你我这样的人在需求，修复，构建中演进下去的。Let's try it !
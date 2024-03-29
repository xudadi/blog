---
title: '如何设计精准的推送通知？【译】'
date: 2019-09-19 14:11:28
tags: [推送]
published: true
hideInList: false
feature: 
---
 


> * 原文地址：[What You Must Know To Build Savvy Push Notifications](http://firstround.com/review/what-you-must-know-to-build-savvy-push-notifications/)
* 原文作者：[First Round](https://twitter.com/firstround)
* 译文出自：[掘金翻译计划](https://github.com/xitu/gold-miner)
* 译者：[写代码的猴子](https://github.com/laobie)
* 校对者：[Ruixi](https://github.com/Ruixi), [rccoder \(Shangbin Yang\)](https://github.com/rccoder)
<!-- more -->


智能手机面世已经近十年时间，但根据 [First Round 对初创公司的调查报告](http://stateofstartups.firstround.com/#highlights) 来看，创始人们仍然宣称移动端是最被低估的技术。推送通知在移动设备上潜力极大。企业家 [Ariel Seidman](https://www.linkedin.com/in/aseidman) 在 [改进移动端的推送通知](http://arielseidman.com/post/62564939335/fixing-mobile-push-notifications) 这篇文章中提到：“确实很难再夸大推送通知的潜力。这是在人类历史上第一次可以同时拍着近 200 万人的肩膀，说‘嘿!注意这个！’” 这也是 [**Slack**](https://slack.com/) 的 [**Noah Weiss**](https://www.linkedin.com/in/noahw) 一直笃信世界会通过智能设备变得越来越亲近的原因。

供职 Slack 之前，Weiss 在 Foursquare 工作，当时它 [通过原生广告服务获利](http://techcrunch.com/2013/10/14/with-an-eye-to-more-revenue-foursquare-opens-its-ads-platform-to-all-small-businesses/) ，并在 2014 年大胆地分成 [两个应用](https://medium.com/foursquare-direct/the-lego-block-exercise-4c7d60eeb38f#.tmyz2j5o0)。那时候，每月活跃用户增长五倍之多。 Weiss 还是 Google 结构化数据搜索项目的首席产品经理。最近，Weiss 加入 Slack [建立其纽约办事处，领导新的搜索、学习和智能项目组](https://medium.com/@noah_weiss/starting-up-slack-s-search-learning-intelligence-group-in-the-new-nyc-office-af6523090789#.sqly156er)，其任务是开发[新的功能](http://www.recode.net/2016/6/6/11863534/slack-artificial-intelligence-AI-noah-weiss) ，使其他公司在使用 Slack 时更加高效。

在这次采访中，Weiss 描绘了推送通知的动态演变 —— 阐释了智能手表和应用布满屏幕主屏时代关键的范式转变。在此，他还分享了一些关于初创公司寻求制定推送通知策略、投入、指标和指南的小秘诀。任何想要控制这种高风险、高回报渠道的创业公司都会从 Weiss 这里受益。

> 一个好的推送通知有三个特性：及时性，个性化和可行性。

### 推送通知的演进

在分享他的策略之前，Weiss 总结了推送通知的演变，因为它涉及到**三种强大的特质：及时性，个性化和可行性。**他将他们的历史和进展看作是建立未来时的基础。以下是简化的推送通知演变历史的四个阶段：

**电子邮件是推送通知的前身。** 网络时代初期的推送通知是电子邮件。“在电子邮件和推送通知之间有很多类似的地方。” Weiss 说，“在过去，你通过提供电子邮件地址，允许与网站进行开放式沟通。电子邮件成为将人带回网站的可靠的主要方式，它不是通过门户或书签。并且，电子邮件中有一个取消订阅选项。通知的等效选项是调整推送设置，或者更常见的是卸载应用程序。

**进化到移动时代。** 当用户在手机上投入更多时，电子邮件开始衰退。“可能很难回想起智能手机之前的时代，人们并不习惯在他们的收件箱里生活。他们每天在电脑上检查电子邮件好几次。“ Weiss 说。 “即使是那些拥有非常成功的电子邮件营销策略的公司也会使用移动设备。还记得 Groupon 提供激光脱毛服务吗？你为什么收到它？你什么时候对脱毛表现出兴趣，或者表示你在手机上做出这种类似的购买决定时？绑定到用户，位置和一天中的某个时间，推送通知变得更有效。他们有着及时性、个性化和可行性的潜力，当然如果做的不好，用户也会感到厌烦。

**与短信竞争，而不是电子邮件。** 在移动设备上，推送通知更像是短信，而不是电子邮件。“推送的内容是与此刻发生的事物紧密相关的。当你可能不指望你的内容在几天内被阅读，你可以发送一封电子邮件，这对于业内通讯或文摘来说是可以的。” Weiss 说，“然而，实时推送通知所需的及时性或注意力是完全不同的。通过推送通知，你可以有效地与短信和其他个性化的沟通方式竞争。如果别的通知来自某人的配偶、最好的朋友或妈妈，你如何做到个性化？它们必须在同一水平竞争。

**切割所有应用程序。** 当人们首次使用智能手机时，他们的应用可以摆放在 4x4 网格的主屏幕上。而现在，美国用户的手机上大约平均有 55 个应用。“你需要知道的是，无法让这些应用都被定期使用。如今也很难开发一个应用，让该应用的使用变成日常习惯。” Weiss 说，“开发者的现实是，你的应用可能不会在某人的主屏上，用户也可能不会有一天使用它多次的习惯。这就是通知变得越来越重要的原因。对于大多数应用，推送通知可以完美地提供紧急信息：Uber 到达，登机口变更提醒或者你在 Slack 中被提及。如果用户被 50 多个应用程序淹没，你不能指望他们记住在正确的时间和地点使用你的应用，你需要主动引导他们打开。


### 围绕以下原则构建你的推送通知策略

深度通知策略可以权衡和组织多个因素，例如附近的 WiFi，个性化，社交因素和实时捕捉到的位置等等，都可以用来驱动推送通知。但对于刚刚开始接触推送通知技术的初创公司来说，有一些基本因素需要考虑。从基本到更高级的诀窍，Weiss 讲述了他在开发推送通知系统时学到的基本经验。

**在应用程序之外促进用户留存**

从用户保留角度来看，当你的应用超越了功能下限后，用户返回你的应用的次数会减少。你只能在你的应用中塞入那么多功能，并期望新用户在一开始的几个会话中发现这些功能。“移动领域最大的挑战是留住新用户，已经有得到证明的战术来引进新用户：高效的应用安装营销、社交渠道、SEM 和 SEO。然而，真正困难的是让新用户养成一种习惯。” Weiss 说，“有时候，你的应用的改进不会显著影响用户留存的顶峰值，但是在应用之外的投资却可以做到，这里即推送通知的投资。因为一旦有人关闭了你的应用，他们错过了第四个 Tab 下的神奇体验就变得无关紧要了。因为如果他们再也没有打开你的应用，他们永远不会知道他们错过了什么。

在为你的应用设计最佳用户体验的过程中，请不要忘记，只有在用户打开应用时，才会享受到这种体验 —— 才会继续回到你的应用。“这总是让我感到惊讶和痛苦：当我看到对一个应用投入令人难以置信的时间和精力，却没有一个策略重新吸引我。” Weiss 说，“当然，大多数年轻的开发人员都不考虑通知。不要犯这个错误。这也是目前移动产品开发中最大的疏忽。”

> 客户需求推进了一个应用，用户留存成了一笔生意。

**不要在有权限的情况下错误下载。**

请求获取发送通知的权限不仅是良好的形式，而且在技术上也是必要的。“如果你在 iOS 平台上开发，发送通知是用户必须授权的权限。与 Android 不同，下载应用默认授予权限，你必须提示用户。” Weiss说，“这是一个很关键的时刻，如果用户拒绝授权，应用无法引导用户重新进入授权页面，这极大地降低了他们变成活跃用户的可能性。即使他们接受，这也不是个有约束力的合同。”

如果用户厌倦了你的推送通知，最好的情况是他们可以选择在应用中保留哪些通知是活动的，但更可能的是导致他们到手机设置中关闭所有通知或者卸载应用。这实际上是不可逆的。注：提升给用户的第一个通知体验，否则他们会关闭通知渠道。

因此，第一步是提示用户在一开始同意接收通知 —— 如果他们说不，其余的建议将变得不再重要。它涉及用户教育，在用户发现有价值的内容之后再弹出提示，或者授权绿灯亮起来时再申请授权许可，可以提升转化率。然后是关于保持信任和保持开放的沟通，这两个步骤有一些不错的文献可以参考，Weiss 推荐了以下的文章：

*   [移动端请求用户权限的正确方式](https://library.launchkit.io/the-right-way-to-ask-users-for-ios-permissions-96fa4eb54f2c#.3u7waqk3w) —— [Brenden Mulligan](https://twitter.com/mulligan)

*   [为什么 60％ 的用户选择停用推送通知，如何应对这种状况](http://andrewchen.co/why-people-are-turning-off-push/) ——[Andrew Chen](https://twitter.com/andrewchen)

*   [让用户再次回到你的应用的正确方式](https://medium.com/circa/the-right-way-to-ask-users-to-review-your-app-9a32fd604fca#.iz4jrwiin) ——[Matt Galligan](https://twitter.com/mg)

考虑到获取通知权限的高风险，这些文章的重点默认是如何规避风险。“如果你足够聪明，那么实际上涉及到通知你会变得非常谨慎。在所有实验中建立安全网，因为任何失误都会产生很大的影响。” Weiss 说，“例如，如果我每周发布一次推送，所有用户都会收到，我会将它作为一个 5％ 或 10％ 的实验，以覆盖任何导致用户选择退出通知的潜在缺陷。”

**指定三个指标来衡量通知**

为了评估你的通知策略，需要给出以下三个指标：**1）选择取消通知权限的用户比率 2）卸载率 和 3）每百次推送的操作次数**。

“要评估一个好的通知，你必须在用户主动参与和取消通知之间达到平衡。这是一个棘手的平衡，因为你可能会比较一个短期的主动参与用户数的提升与长期下来的卸载用户数，不能再重新参与。” Weiss 说。 “从设定卸载率和通知禁用率开始，如果你的应用程序是面向消费者的，而且卸载率低于 2％，则表示你处于安全区。所以如果你的每周流失率为 1％，你的增长率为 1.02％ 到 2％，这不是毁灭性的。监测所有剧烈的波动，因为一周一周的叠加效应可能会造成损失。”

为了评估通知策略的回报，不要考虑打开率而是衡量具体操作。“我建议的一个方法是监控推送通知的时间窗口，统计到达绑定到原始通知的操作的数目。例如，如果通知鼓励用户评价他们最近访问过的地方，分析用户在 2-6 小时的窗口内每百次推送通知的评分数。” Weiss 说，“总是有归属的问题，但如果你在发送通知后定义一个固定的时间窗口进行评估，结果会让你更能接受。

**...校准指标以用来比较 iOS 和 Android 上的表现。**

对于那些想要将打开率作为指标进行追踪的人，Weiss 对不同操作系统上的通知的性质有几点看法。“通过电子邮件跟踪打开率是很容易的，但是你要知道 iOS 的打开率远远低于 Android;进行相同的推送，Android 可以显示多达 iOS 平台五倍的打开率。” Weiss 说，“在 Android 用户倾向于处理通知，因为只有在你手动打开每个通知时，通知才会清除，而在 iOS 上，一旦你从锁定屏幕打开一个通知，其他通知就会清除。

与其他功能一样，不同的操作系统在收到通知时表现也不同。“例如，Android 上的通知可以内置图片，这样可以提高 15-20％ 的互动概率。由于大多数开发人员通常在 iOS 平台上工作，他们认为发送 Android 推送通知也不可以附带图片。” Weiss 说，“还有内置操作按钮，让用户可以直接从通知进行操作。这些也提升了更高的互动概率。即使作为一个 iPhone 用户，我也不得不说，从根本上来说，Android 的通知开发都是更好的。

> 用个性化的内容填充推送通知，让他们听起来像来自一个亲密的朋友。

**抵制新奇性效应**

运行推送通知的实验至少六周，12 周是一个不错的选择。 Weiss 明白，进行更长时间的测试是必要的，以表现出所有负面影响。“一般用户将忽略不必要的推送大约一个月，而不采取任何操作，如更改设置或卸载应用。一旦超过这个阈值，烦人的通知很快被清除。” Weiss 说。

通知具有强烈的新奇性倾向，这延迟了用户的真实反应。Weiss 曾发起了一个实验来测试用户对表情符号的反应。“我们将文本的长度减半，并添加了相关的表情符号。在实验的前两个星期，我们统计指标达到了顶峰。用户打开应用的操作明显。每周活跃用户数( WAUs )上升。它迷惑性地宣称未来是表情符号的。” Weiss 说，“随着时间的推移，我们继续监控它，增长放缓，然后变平。最后，影响是中性的。这并不是一件坏事，但如果我们基于初步结果就分配资源，那就会导致问题。因此最好花几个月时间而不是几个星期来测试推送通知。

**如何测试？何时测试？在哪测试？**

推送通知的“为什么”和“谁”是比较直接的 —— 目标是提升所有用户的参与。然而，在推送通知的方式上却有各种各样的想法。Weiss 在他的职业生涯中，帮助启动了 100 多个通知实验 —— 测试了从一天时间内到触发，到回到首屏。 [与运输软件一样，没有“正确的方式”](http://firstround.com/review/the-right-way-to-ship-software/) ，但在这里他分享一些无可争议的点：

* **只有最紧急的通知才需要开启振动。** “通过推送，你可以控制默认设置是手机振动还是静音。从我所有的用户研究中我发现这是最高风险的决策之一。如果一个通知振动了用户，她发现并不紧急，那么应用程序被卸载的可能性立即暴增。” Weiss 说，“如果它是紧急的 —— 就像你即将错过你的飞机或直接来自同事的紧急消息 —— 一个嗡嗡声可以是一个非常强大和值得称赞的工具。如果没有，这将会产生危险、发生意外，因此，对于从朋友那得到一个赞或者喜欢，不要使用振动。用户平均每天查看手机的时间为 70 到 100 次，他们很可能在接下来的 15 分钟内看到你的消息。”

*   **匹配用户的生物节律。** “推送的时间很重要，但没有一个规则来规定绝对最好的窗口时间。但请花一点时间思考下如何监控用户作息进度，避免在用户睡着时发送通知，因为这样你将吵醒他们，或者他们会在早上发现一堆来自你的应用的推送消息。” Weiss 说，“也要考虑你的内容的性质，在上午发送新闻效果不错，以及在上下班路上时发送通知也不错。通过监控用户的参与来提升你的策略。”

*   **在你的通知副本中使用各种个性化。** “它产生了巨大的差异。插入用户的名字不算在内，例如' Noah，这里是你星期二的每日交易！'在你的通知副本中显示你知道的有关用户的信息 —— 否则他们将激活他们天生的过滤器来应对爆炸营销。” Weiss 说到，“ 当用户查看他们的时间线时，Twitter 有一个好的做法，该服务提示你查看 Evelyn，Marcos 和Lydia 的最近一天的推文。这些都是你关注的、可以叫出名字的人。Spotify 对于你经常听的艺术家的新歌也一样处理。

*   **像 Uber 一样思考你的推送。** “如果你的 Uber 司机在曼哈顿的任一个街区上放下了你，当你要求在下东区一个特定的街区下车，你会高兴吗？这很显然，但初创公司可能忘记将他们的用户指引到在通知中提示的**准确**界面上。” Weiss 说，“如果通知引导用户进到他们期望的界面，人们就会点击它。如果没有，他们下一次就会忽略它。许多电子商务应用通过将用户引导到通用界面而不是特定项目或页面来解决这个问题。

> 魔术师把你的选中的牌变到一副牌的最上面。拥有智能通知的应用将拥有更多的手法，在适当的时间将他们的服务呈现到人们的手机上。

### 通知的未来

智能手机和智能手表的屏幕不断变化，但主屏幕的实际空间始终是有限的，无论大小。考虑到手机上保存的应用程序数量激增，此限制是一个约束。以下是 Weiss 从移动操作系统的演变得到对未来通知的想法：

**让锁屏成为新的主屏幕。** 事实上，人们看到的比手机主屏幕更多的唯一地方就是手机锁屏界面。“你的主屏幕上放置的你想要触手可及的应用，通常限制在不到 20 个。你的锁屏则列出了手机上的数百个应用最近的通知。” Weiss 说，“我认为锁屏将取代主屏幕，将会有一个全新的主屏体验，将应用以流的方式呈现给你。最终排名将不仅仅是取决于最近使用和使用频率。系统通知将感觉像 Twitter 的实时动态，嘈杂的信息流让人感觉像 Facebook 的热门动态。

> 你可以随时切换到某个应用，但通知将是你坚定不移的向导。

[应用绑定和解绑的自然现象](http://ben-evans.com/benedictevans/2014/8/1/app-unbundling-search-and-discovery) ，Weiss 看到一个潮汐般的转变：锁屏将再次重新绑定它们。“在过去三年中，应用生态系统中出现了一个渐进的、巨大的分裂。应用程序已变得针对单一使用场景更加专业化。” Weiss 说，“但随着用户聚集了一堆应用，在正确的时间选择正确的服务变得越来越困难。通知给用户提供及时有用的信号。将会有一个新的导航范例，当用户正在考虑使用某些应用时，智能地控制这些应用。

**丰富的上下文感知。** 如果用户越来越多地通过发送到锁屏界面的通知流来与应用交互，这将是因为他们确信他们被发送了最及时、最相关的警报。这只会发生在一个强大的的上下文感知中。“手机上的传感器使你能够在移动设备上建立一个感知上下文级别的服务，你永远不可能在桌面或电子邮件上进行这样的感知。你如何把这种感知翻译成真正可行的、及时的、相关的通知？”魏斯问，“这是一个令人振奋的新领域，想象一个服务，可以区分是否有人一个特定的场所停驻，无论是咖啡馆，机场还是健身房。对上下文的独特感知创造了大量发送相关推送通知的新机会。”

> 最好的应用将是那些你不必记住他们的应用，他们会主动提醒你。这种应用将是未来的唯一类型应用。

“我最喜欢 Foursquare 在一个城市新的或热门的场所的推送通知。根据你的手机的定位，它可以将你与实际访问的地方关联起来。” Weiss 说，“它给你一个通知，通常每周一次，'嘿，这里有三个城市热门地方，你还没有去过。’这是一个神奇的时刻，当你意识到你仅仅是带着口袋里的手机在周围走了走，也许你甚至整整一个星期都没使用过这个应用。你不需要做任何事，它就将你拉回这个应用，并给你惊喜。”

完整利用移动设备上的传感器具有挑战性，但可以从一些基本的方向开始。“虽然大多数开发人员无法简单地建立这种类型的位置解析，但是基于后台定位构建一个模型用来解析一个人在家还是在工作是很容易的。这是两个用来触发相关的推送非常丰富的上下文。” Weiss 说。

### 总结

虽然通知可以提高留存率和互动率，但不要将其视为增长的黑科技。他们有潜力成为与用户互动的最直观、最亲密的方式。为了建立这种可靠的关系，他们必须是及时的、个性化的、可操作的。通知策略必须请求用户的授权，并根据其停用、卸载和每100次通知点击次数来权衡。更好地方式是根据用户主动输入和被动地感知上下文来定制通知。

“我们还在移动时代的早期。设备继续改进，将会拥有更大的屏幕，更长的电池寿命或者变成可穿戴的。” Weiss 说，“然而无论硬件如何发展，通知将是你的移动设备最亲密的功能。像亲密的朋友或家人一样，智能通知会记住你的偏好和历史。他们会准确地指引你，让你与亲人保持联系，并在最合适的时间提醒你重要的事情。这大概就是技术的力量。”

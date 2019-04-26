## 网购有助"脱单"?我还实现了一个准确率99.9%的癌症预测系统呢

前天，一个朋友给我看了一篇文章，题目是《网购有助“脱单”？阿里的大数据证实了这一点》。

文章的一个主要论据是，有近7成的淘宝、天猫用户已经找到伴侣，仅3成单身。所以，网购有助脱单，因为网购用户都7成告别单身狗啦！（当然，原文还有其他数据的逻辑链也有问题，但是这篇文章主要就怼这一条啦！）

![taobao](taobao.png)

嗯，在淘宝天猫上，有伴侣的用户是单身狗的两倍还要多啊！所以单身狗一定要在双11买买买，才更有可能脱单哇！

嘿嘿嘿，是不是看到这个结论，已经觉得哪里不对劲了？

如果你将这样一份报告扔给一个统计学家。哦，其实不用，随便扔给一位博士生，他们会连文章都不看完，就不屑地表示：一本正经地胡说八道！

然后，再无奈地表示：流量怎么都被这些无知的人类赚走了呢？

<br/>

事实上，如果我们仔细分析这个结论的不合理，可以挖掘出一个大家在面对统计数字时非常容易犯的错误。我个人认为，对这个错误的认知，基本决定着你是否有统计学的思维（其实在我心目中，还有另外一点有同样的作用。双剑合璧，方为统计学思维初建立。这篇文章先只说一点。）

是的，统计学绝不仅仅是推导公式，统计学更是一种看待世界的方式。

<br/>

随着机器学习的兴起，统计学越来越受到大众的重视。事实上，在现阶段，短期内，我认为已经没有一门理工类学科可以离开统计学了。嗯，曾经有一位常青藤名校博士生铿(wu)锵(bi)有(xin)力(suan)地对我说：所有的博士其实到头来都是做统计的。是的，我认为统计学已经成功地控制了地球！

同时，这也造成了一个不好的结果，就是对统计学的滥用。或者是商家成心错误地使用统计学，带给大家利好商家的假象。（比如网购有助于脱单。。。）在这些“假象”背后，其中一点，学术一点儿称呼，就是**基本比率谬误（base rate fallacy）**。

要讲清楚这个谬误，通常都用这么一个例子。**有一个人，喜欢看书。你觉得这个人是一名图书管理员捏？还是一名销售员捏？**

大部分人都会不假思索的回答：是图书管理员啊！喜欢看书啊。可惜，如果用这个事情去打赌的话，大部分人都会输得精光。原因很简单，在大部分成熟的商业社会，图书管理员这一职位的总人数，比销售人员少得多。这使得这名爱看书的人是图书管理员的概率，比是销售人员的概率小得多。

可是有的童鞋可能会跳出来喊，不对！我们考虑这个问题不能只简单地看这两个职业的总人数啊。这个问题本质是一个条件概率问题啊！其实，我们是在考虑，在爱看书的条件下，一个人是图书管理员的概率有多大？是销售人员的概率有多大啊？

说得好有道理啊！所以，其实更准确的说，如果我们不知道图书管理员和销售人员的分布的话，是无法估计这个问题的。那我们就简单做一下调查吧。据悉，在美国，图书管理人员和销售人员的人数比是1:1000。（这似乎还是很久以前的数字，现在可能更低。不过我们这个文章的关注点不在这个具体数据，所以大家就先接受它吧！）

嗯。也就是假设在美国社会有10名图书管理员，对应就有10000名销售人员。现在假设图书管理人员100%的爱看书，很符合这个人设吧？而销售人员，只有5%爱看书，嗯，我觉得我严重低估了销售人员对知识的追求和渴望，销售人员会不会组团来打我？但是为了说清楚这个问题，我就牺牲一下吧！（喂喂，明明是销售人员在做牺牲！）

对于这样的数据，意味着我们有10\*100%=10名爱看书的图书管理员；10000\*5%=500名爱看书的销售人员。也就是说，此时，我们考虑了两个职业爱看书的程度的差异，甚至故意夸大了这个差异，可依然得出这个结论：一名爱看书的人，他是销售人员的概率是他是图书管理员的50倍！

那么问题来了，为什么大多数人都会觉得：爱看书的人是图书管理员的可能性大？这就是因为我们忽略了图书管理员和销售员两者在整体人群里的基本分布，或者叫基本比率。这便是**基本比率谬误（base rate fallacy）**。我们习惯用表面的现象代替全部，而忽略现象背后的基本比率。

<br/>

仔细想，这样的错误其实我们经常犯。我们经常不由自主地把爱看书的人想成是图书管理员；开宝马的人想成是富二代；技术大佬想成是六岁就开始编程；等等等等。但当我们了解了基本比率谬误，就可能会反思，正如同图书管理员是少数人；富二代也是少数人；六岁就开始编程的也是少数人。所以那个开宝马的人，或许更有可能是普通人自己奋斗的结果；那个技术大佬也更可能是本科才开始正式编程，多年努力的结果。

嗯，这是一碗鸡汤，有没有觉得世界更美好了？所以大家不要放弃努力，要继续加油啊！

<br/>

是时候回到我们阿里的大数据了：有近7成的淘宝、天猫用户已经找到伴侣，仅3成单身。了解了基本比率谬误，我们就能明白：这个数据显然忽略了单身和非单身的基本比率！

我简单查了一下数据，国内的单身狗大概有2亿人，现中国的总人口大概13.8亿。换句话说，在中国，单身狗占15%左右；而非单身狗占85%。

等等，可是在淘宝平台上，单身狗竟然高达30%。这说明了什么？显然对比基本比率，是有更多的单身狗在淘宝平台上啊！我们是不是可以得出一个完全相反的结论？越“网购”，越单身！而很多不是单身的人，恰恰不在淘宝天猫的魔掌中！

<br/>

嗯，基本比率谬误除了能帮助我们认清商家的本质，还有别的作用吗？当然有了！还可以忽悠别人啊！记得这篇文章的题目吗？我们要实现了一个准确率99.9%的癌症预测系统啊！

我曾经参与过一个医学项目（一本正经的胡说八道），这个项目要写一个算法，通过体检者的数据，预测ta将来是否有可能患有某种癌症。好高端有木有？！绝对是现在大热的机器学习啊！还结合了属于21世纪的魔法黑科技生物医疗工程啊有木有！

我花了整整一个晚上思索，终于想到了完美的解答，很快完成了整个算法。又花了一个小时包装好接口。嗯，你们先测试吧。测试结果，准确率99.9%！哼哼，那是当然，像我这种高手，准确率下95%的识别算法根本就没有写过！你们来调用吧，我按照调用次数计费，调用一次10刀！真心白菜价！

其实，那天晚上，我苦思冥想之后，只是简单在网上调查了一下，发现这种癌症的发病率仅有是0.1%。所以我的算法是这样的：对于任何检查者的数据，我都预测他不会患这种癌症。分分钟便得到了一个准确率高达99.9%的预测算法。

是的，我之后将算法包装成方便调用的接口，再添加上支付功能，用的时间比写这个算法用的时间多多了。

我就是这么机智。

<br/>

现在，你理解基本比率谬误的作用了吗？万一遇到不懂统计学的投资人，当上CEO，迎娶白富美，走上人生巅峰，是很简单的啊！

现在，你学会如何实现了一个准确率99.9%的癌症预测系统了吗？

是不是很酷？

---

P.S. 1：正因为在现实世界中存在着如文中所举的例子一样，基本比率极度偏斜的情况（其实仔细想一想，这样的“比率偏斜”可并不少），所以在机器学习领域，如何判断识别率也是需要专门探讨的。有时间再和大家聊一聊：）

P.S. 2：若采用文中方式成功融资，请主动来缴纳给我15%融资额的创业咨询费。若采用文中方式融资被打，概不负责。
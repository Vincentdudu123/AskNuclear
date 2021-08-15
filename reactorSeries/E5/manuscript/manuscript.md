<!--
Editor Vincent Du
Creation Date: 26.08.2020
Last Update: 26.08.2020
-->


<!--
Markdown 常用语法
# Title
## subtitle 1
### subtitle 2
#### subtitle 3
etc.
--- *** ___分割线
*+- 无序列表
1. 2. 3.有序列表
> 引用的文字
空行 换行
*文字* 斜体
**文字** 粗体
\符号 符号 Latex
$$ 公式 $$
！[标题] (href) 图片
[标题] (href "title") 超链接,目录,文件

表格：
左对齐|居中|右对齐
2|3|5
:--|:--:|--:
2|3|5
10|100|1000

```编程语言（可选）
代码
```
`` 行内代码

~~删除线~~

Tasklist
- [ ] Eat
- [x] Code
  - [x] HTML


@import "xxx.md" 插入文档
-->

# Nuclear energy Episode 5
# A very short introduction to nuclear reactors

## Introduction

嗨大家好，我是doudou。没想到吧哈哈，这一期更新的这么快。其实深层原因是我修了两周的假，外面正好又是阴天，录录歌，浇浇花，骑骑车，写写文案什么的。（小声bb）我网易云现在87个粉丝啦。

## Scene one

言归正传哈，上一期讲了重要参数Keff，它决定了反应堆临界与否，或者通俗一点讲它秒睡了反应堆中中子的数目变化情况。这一期我们来讲讲他的衍生产物，对于反应堆物理同样重要的系数，反应性， $\rho$。从数学公式角度上讲，它表示的是中子数的变化占总中子数的比例。从另外一个角度上讲，它表示的是系统和临界状态的距离。如果他是正数，那么Keff就大于一，中子数就会增加，功率也会增加，反之则减少。那么在一些情况下我们就要时刻保证这个反应性为负值以避免功率一直上升。

反应性这个参数其实我在平常的工作中经常会用到，无论在安全分析，事故分析，反应堆设计还是每次反应堆换料分析，这个参数都是重点分析的一部分。


$\rho=\frac{N_{0} * k_{eff}-N_{0}}{N_{0} * k_{eff}}$


$\rho=\frac{k_{eff}-1}{k_{eff}}$

插一嘴，怎么区分一般的运行事件(transient)和事故(accident)呢，大概就是所有的事故最后都可以写成一个故事而另外一个很快就会被人忘记。

Furthermore，从反应性又能延伸出另外一个概念，叫reactivity feedback coefficient，反应性反馈系数，它描述了某一个参数单位量变化对应的反应性的改变。比如说慢化剂的温度变化了会造成反应性跟着变化，而1K或者1degree celcius慢化剂温度的变化造成的反应性的变化就是这个慢化剂温度的反应性反馈系数。hmm有点儿绕是不是，不过没关系，这个不重要，重要的是你要知道这个系数现在的反应堆设计中扮演的角色。

这就牵扯到另外在反应堆设计中很重要的概念，负反馈系数。什么是负反馈系数呢，简单来讲就是反馈系数是负的，复杂点来讲就是系统一个变量的变化 $\delta x$ 与反应性 $\rho$ 是负相关. 为了理解这个概念我们用两张图来解释一下。

假设我们在地球上，没有风，重力向下，没有磁铁，在一个u形槽底上有一个铁球，u型槽光滑且坚固，坚固到球砸在上面也不会出一个坑，球不会已任何一个理由嵌在或者粘附在槽内壁上，外面也没有讨厌的人把球拿走（鬼知道我怎么这么婆婆妈妈）。有一个不知名的原因让小球沿着内壁产生了位移，由于重力的作用小球无论向哪个方向移动最后总是能够回归原点。然而在另外一种情况，还是因为重力的作用小球无论像哪个地方移动最后都会掉落下去。那在第一种情况下系统就是真稳定，在这种情况重力就是稳定性的负反馈，而第二种情况下系统是假稳定，重力就是稳定性的正反馈。

或者再换句话说，负反馈就是每次你出门远游突然觉得家里的床好舒服，饭好香的那种感觉。

延伸一点儿说啊咱们看看下一张图，在A点上我们大致判断出系统是稳定的，但是当小球的位移大于B点之后系统就变得不稳定。扯的有点远。

当然啦核电站从设计上就要保持各项系数的负反馈，这是很很很重要的，顺便再戳一下切尔诺贝利。

## Scene two

那么在反应堆中会有哪些常用到的反应性反馈系数呢？由于本视频面向非本专业人士，故很多概念简化讲解。

首先是燃料的温度反馈系数。当反应堆功率上升时，核燃料的温度会上升，共振区的中子截面会变的平缓，虽然积分下共振区的面积是不变的，但是由于被捕获的中子是中子截面和中子通量乘积在能量上的积分，虽然中子截面变平缓，但是被捕获的中子变多，因而p（上一节课）变低，反应性也下降，因而燃料温度为负反馈。

另外一个慢化剂的反馈系数则比较复杂。这里以水为例，当反应堆功率上升时，水的温度升高，密度降低，导致中子慢化不足更容易让反应性下降，并且中子泄漏的概率会增加，这里是负反馈，另外一方面，当密度变小后，中子被水分子吸收的概率会变小，如果水中有硼酸，那么中子被硼酸吸收的概率也会变小，这两个因素则为正反馈。这个时候要保证的是它们的综合为负，这也就是为什么反应堆的设计需要的是低饱和的慢化效果，比如在缺失部分慢化剂的情况下能够保证反应性的负反馈，从而达到功率降低的效果。另一边在过饱和的情况下，如果慢化剂和燃料比例下降反而会向系统注入正反馈就会加剧功率的提升，进一步加剧这个比例的下降，显然这不是我们想看到的。至于另外一个硼酸的问题我们之后会在中子毒剂中讲到。

这两个是主要影响反应堆的两个反馈系数，其他的反馈系数还有硼酸浓度的反馈系数，功率的反馈系数，其他中子毒剂的反馈系数，还有控制棒的反馈系数等等。

还有一点要提一下，既然提到硼酸了就要顺嘴说一句，当硼酸含量过高的时候反应堆的慢化剂反馈系数可能为正数，这种情况需要在正常的运行时避免发生，当然有多种手段从设计根本上避免这个现象，比如采用低富集度的核燃料，加入含有中子吸收剂的燃料棒等等。我们之后会在讨论经济性的章节里提到。

## Scene five

突然感觉给自己挖了好多坑。下一期让我们来看看裂变的产物吧，顺便来提一提中子毒剂的事情。peace out。
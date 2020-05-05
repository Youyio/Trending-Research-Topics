# 论文主要内容总结

该文章提出了一种基于广义似然比的序列检测器的方法用于解决智能电网的虚假数据注入攻击问题，该方法的实验结果表明与现有方法相比，该方法对各种攻击数据具有较强的鲁棒性和较高的计算效率。

同时，该文章进一步提出了一种基于自适应采样技术的分布式时序检测器，称为水平触发采样，用于解决智能电网的广域监控问题，而与现有方法相比，分布式的检测器大大减少了系统中的通信开销，同时保持了集中式检测器的鲁棒性和高性能。

# 论文基本信息

> 标题：
>
> *Quickest Detection of False Data Injection Attack in Wide-Area Smart Grids*
>
> 作者：
>
> Shang Li, Yasin Yılmaz, and Xiaodong Wang
>
> 刊物出处：
>
> IEEE Transactions on Smart Grid ( Volume: 6 , Issue: 6 , Nov. 2015 )
>
> 链接：
>
> https://ieeexplore.ieee.org/abstract/document/6982207

# 论文主要创新点

1. 将概率统计方法中的“广义似然比检验”引用到假消息注入攻击的检测中，在本文中使用的是基于广义似然比检验的CUSUM(Cumulative Sum Control Chart:累积和)算法，代表偏离目标值得变差的”累积和“，它把当前和最近的数据看得同等重要。
2. 同时在广域监控问题上，使用ADMM(Alternating Direction Method of Multipliers:交替方向乘子法)，在全局问题的解决上，该方法可以更加有效地提高分布式检测器的效率。

# 论文的缺点

1. 对于文章原理，广义似然比检验是基于极大似然估计数学模型，因此在数学模型的选择上，该方法选择的数学模型不算太新，只是常见的概率统计的数学模型的一种。
2. 该文章在广域监控问题上，仅仅采用了SCADA(Supervisory Control And Data Acquisition)系统，即数据采集与监视控制系统对实验进行验证，并且该系统采用的是IEEE14总线电力系统。然而，这样的实验过程不足以普遍到其它常见的电力系统上，在DCS（Distributed Control System）分布式控制系统中，存在有分布性更强的系统模型，因此该检测方法的普遍性并没有得到很好地测试，不能说能够运用到各类广域监控问题中。

# 改进方法

1. 对于数学模型的选取，可以考虑采用一些概率统计里面的某些现代模型，也就是在系统设计时使用较新的工作框架，以便于提高对相关问题的正确性和适用性，使得检测器的工作更为高效。
2. 针对于系统普遍性的测试，可以在DCS（Distributed Control System）分布式控制系统，其控制站点至少要是两个，主要用在过程控制领路。主要就是将各个分站进行数据交流和整合，完成满足客户需求的控制，核心是网络架构，主要目的是实现控制方式。这个系统同样是分布式的广域监控领域，只不过架构与SCADA架构有区别。
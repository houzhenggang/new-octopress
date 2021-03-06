---
layout: post
title: "家用路由器的选择点滴 "
date: 2012-02-17 14:26
comments: true
categories: 
- 生活
---

因新装光纤宽带后，对老的TP-LINK路由器不满，打算重新购买一台家用路由器，从而对目前的家庭路由器进行了一番了解和实验，于是有了这篇小结。

不满TP的原因是它对bt、emule高并发连接的支持不好，一旦允许的连接数达到几百个以上，那么打开网页等都会受影响。我起初以为这只是硬件能力的问题，毕竟tp的只是低端货，不能指望太多。但到底什么才是家庭路由器中的比较高端的或者能满足这种需求的产品呢？

经过一些了解后，知道路由器的档次区分可以从硬件上来进行。但往往路由器的标的上只会显示ngb这些信息，或者告诉你300M 54M这些，但光知道这些似乎并不足以区分路由器的能力。而真正决定路由器硬件水平的，实质上和电脑很类似。一台电脑硬件的关键标准是cpu和内存，路由器其实也一样，也是cpu、内存、flash的大小决定了路由器的类型。不得不说，这方面的材料是很少的。大部分厂家并不愿意提供切实的路由器数据。我仅仅看到磊科的NR235W提供了自己的芯片和内存信息：
"内存：64MB   
CPU：美国博康BCM5357处理器   "
后来，在一个网站上找到了一批路由器的硬件材料，参见http://www.dd-wrt.com/wiki/index.php/Supported_Devices
比较有价值的例如"TP-LINK WR841N(D) 5.0 AR7240@400 32 4"， 这个意思是芯片是AR7240,内存是32M，flash是4M。

也更进一步了解到，路由器的芯片厂家主要有两大体系，AR系和BCM系，到底哪个好要具体芯片具体比较。ram的大小决定了系统的带机能力，flash的大小决定了所能安装的固件及软件的尺寸。
其实，比较起来，电信的家庭网关在硬件方面反而厚道的多。比如目前配合光猫常用的两款中兴的H218N和贝尔的RG-200，内存和cpu甚至比磊科的NR235W都略胜一筹，而比起100出头的主流路由器就更好出一倍了。
        CPU：Broadcom 5358（BCM5358）内存：64M falsh: 8M
至于电信其他的家庭网关，虽然都打着‘低端路由器’的标签，但实际硬件能力却比市场上200左右的路由器都好许多。

但是，电信提供的网络或路由器的软件均不给力。界面难用，功能受阉，管理员帐号通常也很难获取。这就引发了另外一个问题，光有硬件的路由器是什么都做不了的。决定路由器能力的，除了硬件还有至关重要的软件。某种程度上，可能比硬件还要重要。电信路由器弱就弱在软件。

而提起软件，路由器的开源软件普遍起自linksys。目前比较流行的有dd-wrt, openwrt和tt。tt我没装，从dd和open来说，前者更面向普通用户，主要以web管理为主，简单好用。openwrt则主要通过文本配置进行管理，对开发人员更有好些。总而言之，二者的功能均很强大。甚至可以自己利用这两个操作系统配置vlan。而且运行也会很稳定，tplink 841N用这两个固件就会比原厂的稳定的多。

而安装这两个软件能发挥能力到什么地步，则又和硬件中的cpu型号、flash等有关。由于linksys那款是用Broadcom的芯片，所以一些尖端的功能如vlan等都是b系列的支持要好于A系列。所以对于想自己刷机的人来说，目前还是推荐B系列芯片的路由，这样可以打开的功能更多。而flash大小的限制则决定了能够安装的固件规模及以后加载软件的多少。当然是flash越大，能装的也越多。至于内存，那和pc是一样的，越大自然越稳定。

上面这些固件要刷进去，基本有3类方法。第一类就是直接用web里面的上传按钮，当然这个限制也比较大，不是所有的版本都能直接这样刷。要看当前的软件和要刷的软件分别是什么。第二类就是telnet后，通过write的命令把固件写进去。前面两类只需要网线直接连接路由器即可，而第三类就要打开机顶盒，用一种叫做ttl的串口线连接起来，然后在超级终端里进行控制。除以上三种常规刷机方式外，还有一种用于恢复的jtag方式，这个用起来最复杂，而且众多板子的支持情况也不一样。实际上从ttl开始，就有可能要求你用电烙铁把ttl的针子焊上去。

总而言之，研究路由器是一样很有趣的活，在其中长了不少知识。如路由器的结构，芯片的种类，内存和flash的指标的意义。在厂商方面也了解了许多，毕竟先造厂才能有产品。中兴、贝尔、华为等给电信提供路由器应该普遍外包生产为主，多半是贴牌，当然目前的光猫一体猫可能情况有所变化。他们普遍的特点是装了电信比较弱的软件，但有强大的硬件配置。而tp-link 水星 捷迅其实是一家人家，而tplink东西很喜欢不断缩水，比如flash从8m缩到4m之类的。磊科是一家台湾人的公司。

上面说得都是概念和分类上的东西，具体到实物，可以这么分类：
1. 80-120的类似tplink 841N的产品，使用的A系芯片，需要足以flash有没有缩水，新版的缩的比较厉害，这个要具体去看。
2. 200出头的tplink和磊科路由器。硬件普遍还不错，价格稍贵。
3. H218N之类的家庭网关。普遍配置是内存32/64M，flash 8/16M。
4. 千兆路由器，价格在400-1000，如华硕的N16和tplink 2543等。当然tp还有价位在200的千兆路由器。
性价比自然是第3类最高，但一定需要刷机。第2类属于想用的舒心又不想刷机的人。第4类属于这方面比较愿意花米的人。第1类则肯定是普通大众的首选。

关于家用路由器就先写到这里吧。而对光猫和iptv的接法考虑再用一片文章来记录一下。
---
layout: post
title: "leetcode小结"
description: ""
category: OJ
tags: [OJ]
---

最近每天无事的时候，都会AC几道leetcode OJ的题目，也算为下一阶段做准备吧。看github的Longest Streak，也有11天了，也该写点东西了。

##选择原因
在校期间没怎么好好的刷下OJ，混个ACMER当当啥的，也算是遗憾之一。TopCoder太高，Poj等国内ACM的oj刷过一阵，不想去弄，最主要还是leetcode以简单(本人水平菜鸟或许尚未入门)实用(据说是某些公司面试题)吸引了我。同时也有同学在刷leetcode，同他一起可以被激励被带领，于是，选择之。

##leetcode提交规范
以最简单的[Single Number](http://oj.leetcode.com/problems/single-number/)为例吧，题目描述无需赘述。方法也很简单，用一个变量保存数组所有元素的异或值。提交则让我不知所措：Poj等都是自己写算法，然后来个main，然后还要小心处理输入输出格式，但是这里怎么没说输出格式是啥！竟然连个1000的sample都没有，差评！

犹豫半天，踌躇良久，搜索亦未果，无奈只好提交下面[代码](https://github.com/chrishine/leetcode/blob/master/Single_Number.cpp)试试看：
{% highlight C++ linenos %}
	class Solution {
	public:
	    int singleNumber(int A[], int n) {
	        int tmp = 0;
	        for(int i = 0;i != n; ++i){
	            tmp ^= A[i];
	        }
	        return tmp;
	    }
	};   
{% endhighlight %} 
然后提示已AC，心情大爽。原来leetcode不需要照顾蛋疼无比的输出格式，只需要写主体方法即可，很高端很智能有木有！

##leetcode之路
leetcode在算法要求上比较简单，所以如果全程刷的话，大概一个礼拜就可以刷完。当然有大神可以把这个时间打对折，继续对折等等。
一般可以根据AC rates挑选题目，但AC rates也只是部分的体现了题目的难易度，有时候并不可靠。比如我AC最惨的俩题目：
![1.2.png](/assets/images/leetcode/1.2.png)
![1.1.png](/assets/images/leetcode/1.1.png)

![2.1.png](/assets/images/leetcode/2.1.png)
[3Sum](http://oj.leetcode.com/problems/3sum/)提交8次，[Remove Duplicates from Sorted Array](http://oj.leetcode.com/problems/remove-duplicates-from-sorted-array/)提交7次。这两个题目都不难，如果按照平均AC rates，我这应该算是拖后腿直到根部的那种。不过这俩过程虽然痛苦，也算有收获，拿```++i```来说吧，它是
```i = i + 1```，但是我老当作```i + 1```使用，忘记了i本身的改变。偶尔写出```i = i++```这样行为不确定的玩意(具体请搜索序列点)。

##亮点题目与负分题目
+ 亮点题目  
    1. [LRU Cache](http://oj.leetcode.com/problems/lru-cache/)。现在Cache命中率都在98%以上，添加，命中至少要是常量时间O(1)吧，移除虽然可放宽到O(N)，但是最好也O(1)吧。命中要常量时间，显然```map```了，添加要常量，顺序表排除，按照规则移除要常量，满足这个要求的常见数据结构只有链表了。要三个都实现常量，就要把```map```和```list```结合起来，```map```的```key```(```first```)不能动，只好在```value```(```second```)上面做文章了。具体怎么做，就各人有各人的实现了。此题目亮点在于将两个数据结构思想结合使用了，而不像其他题目，一种结构搞定，就算是几种结构的，也是井水不犯河水的互不相干。
    2. [Evaluate Reverse Polish Notation](http://oj.leetcode.com/problems/evaluate-reverse-polish-notation/)。此题目的亮点主要来自语言的局限。leetcode只能使用C++(包括C++11)/Java提交代码，而不能使用其他语言。Java8才有lambda，C++11刚刚有lambda，加上新的[function](http://en.cppreference.com/w/cpp/utility/functional/function)，写一个函数表来简化太多的if-else，顺便用用lambda啥的，看着代码挺享受的感觉。

+ 负分题目
	1. [Valid Number](http://oj.leetcode.com/problems/valid-number/)。我是看到这个题目直接放弃的，太多的input case，基本无技巧，AC了也没快感，做了但是AC不了那种痛苦是十分让人抓狂的。这样的题目，适合面试的时候和面试官一起讨论啥的，但是在OJ只能和OJ讨论：让我AC嘛！你的程序在这个test case下无法通过哦。这种感觉大概相当于，有个精确的需求，却只告诉你部分，然后慢慢推出来需求，这样的题目真的不适合OJ。
	2. [Unique Paths](http://oj.leetcode.com/problems/unique-paths/)系列，起点和终点为一个，路径为1还是0？你给我定义一下啊，我定义为0，结果提交表示应该定义为1.在2里面，起点还能被block？这个边界情况至少定义一下行为结果吧。题目的确是好题目，但是这种根本不适合OJ啊，适合面谈。比如[Reverse Integer](http://oj.leetcode.com/problems/reverse-integer/)，10和100逆过来都是1如何处理？大于10E数字末尾大于2咋办？只能讨论了。

##例行吐槽
好像没啥要吐槽的，都吐槽在题目中了。还是吐槽自己能力不足吧。最近用sublime写cpp，没了IDE的提示，发现自己写代码速度提升了，突然明白某同学为啥喜欢用Windows的记事本刷各种OJ了。不过用了神器写go，感觉还是IDE好。。各种强大，虽然go插件相对于神器来说很弱了。
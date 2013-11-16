---
layout: post
title: "usaco section1.1"
description: ""
category: "OJ"
tags: [usaco, OJ]
---
题目可以在这里找到[http://www.nocow.cn/index.php/USACO_Training#Section_1.0](http://www.nocow.cn/index.php/USACO_Training#Section_1.0 "USACO Training 中文页面")。ps：发现上面已经有写的很详细的详解，想要更详细的可以直接看那里了，⊙﹏⊙b汗。

1. Your ride is here.

	分析：根据字符串计算余数，很简单。只是要记得所有字母都是大写，因此计算对应的数字，应与‘A’进行比较。

2. Greedy gift givers.

	分析：关键在于如何根据字符串查找，在c++中，使用stl string重载的"=="运算符即可；在c中，使用strcmp()进行比较。

3. Friday the thirteenth.

	分析：该题直接遍历每个月的13号即可，但有几个细节需要注意。1. 如果每个月第一天的编号是b，那么第13天的编号应该是b+12. 2. 下一个月的13号星期几可以根据当前月13号的星期计算出来，即， (x+dayPerMonth)%7.
	所以，为方便计算，可以首先查找第一个13号是星期几，然后直接计算下一个月的13号的星期。

4. Broken Necklace

    给定一个由两三个字符组成的环，确定连在一起最长字符串的长度。

    分析：如果数据量不够大的话，暴力即可。
    但还有一个dp的方法，就是记录对于每个字符，记录其左边和右边连在一起最长字符串的长度。对于下一个字符，只需要比较是否与前一个字符相同，即可知道当前字符的情况，相同则加1，不相同则为0。


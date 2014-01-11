---
layout: post
title: "一次修复bug的经历"
categories:
- 
tags:
- 


---
为了优化代码性能，工作上除了使用vs编译器，部分项目还使用了Intel编译器。
相比开始编程就使用的vs编译器，我对intel编译器就没那么熟悉了。

最近在使用intel compiler的编译代码的时候出现一个错误： error MSB6006: "icl.exe" exited with code 2。
而换到vs2010编译器的时候，却顺利通过了。由于平时一直借助vs编译器输出的错误信息，所以当遇到这个问题就orz了。


仔细查看项目属性的时候发现**C++ -> Diagnosis(intel)**的属性**Emit Diagnosis To File**被设置为Yes，这样intel编译器的提示信息就被输出到一个指定路径下面的后缀为**(.diag)**文件中。将该属性改为No之后，就可以在output窗口中输出错误信息了。

根据错误信息发现，自己代码中使用了nullptr。而根据[Intel官网](http://software.intel.com/en-us/articles/c0x-features-supported-by-intel-c-compiler)的说明，intel编译器(12.0)不支持nullptr，直到12.6之后才支持，orz。

随后又稍微了解了intel编译器的设置。intel编译器不仅可以提供一般编译器的错误信息，还可以提供优化代码的信息。用户可以根据这些信息对代码做相应更改，从而优化代码。

总结：不同编译器对C++不同版本的支持不同，尤其是一些比较新的特性如auto，nullptr。如果在代码上找不到解决方法的时候，就可以考虑编译器了。



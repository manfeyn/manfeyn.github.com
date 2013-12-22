---
layout: post
title: "list technics"
categories:algorithm
- 
tags:list; standford
- 


---
总结stanford library的[list Problem](http://cslibrary.stanford.edu/105/)中的一些技巧如下：

Coding Techniques:

####1. 创建新的链表##
在处理链表的时候，如果需要返回新创建list的head pointer，可以通过Dummy Node来保存首地址。
所有新建的Node可以添加到其他Node的.next，这种方法可以让对第一个节点的处理与对其他节点的处理完全一致，有助于减少代码。
例子:

	List* Process()
	{
     struct node dummy;
     struct node* head = &dummy;
     
     /*
          Process with the head pointer.
          Such as:
               head->next = new node;
     */ 

     return dummy.next;
	}

当然，也可以通过对返回Pointer的引用，但这时就需要对特殊指针（如头指针或为指针）特殊处理。


####2. 改变一个指针

指针p1赋值给指针p2后，两个指针会指向同一块地址。但如果想修改p1指向的地址，就必须获得p1的地址(&p1)。这一点在处理pointer作为函数参数时需要特别注意。如果函数需要改变参数，那就需要传入指针的引用；如果函数只需要使用指针指向的空间，那传入指针即可。
如：
   
	void ChangToNull(struct node** headRef)
	{
	     *headRef = NULL;
	}

	void ChangToNull(struct node*& headRef)
	{
	     headRef = NULL;
	}

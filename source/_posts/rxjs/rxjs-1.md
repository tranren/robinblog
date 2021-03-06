---
title: RxJS 系列-你应该知道的一些知识
date: 2017-10-24 17:29:57
tags: [javascript, rxjs]
categories: [rxjs 系列]
comment: true
origin: 2
author: du1dume
---

**程序的可扩展性，可伸缩性**

一个应用，当处理少量数据时，可以保证用户界面响应迅速，动画流畅；但当面对大量数据涌入的时候，还能做到以上的保证，我们就可以说此应用具备了可扩展性，可伸缩性。

**同步和异步**

同步方式运行的程序最容易理解，语句一条一条执行，下一条要等上一条执行完才能执行。但现实中并不是每条语句都可以迅速完成，比如一个网络请求，一个数据库查询，一个复杂计算等等都会导致一条语句变成耗时操作，阻塞了程序的继续执行，导致了应用程序没有响应，带来了极差的用户体验。众所周知，Javascript 是单线程模式，该如何解决耗时操作问题？没错，就是 callback(回调)函数。

回调函数其实在 Javascript 随处可见，鼠标键盘事情的处理，远程 http 请求以及文件 io 操作等等。我们提供给耗时操作一个函数，当耗时操作返回时，Javascript
runtime 会立刻执行这个函数。与此同时，我们的程序并没有被阻塞，继续一条一条的执行下去。这就是以异步方式运行程序。

**时间和空间**

在同步方式运行的程序中，我们很容易在任意时刻确定某个变量(共享变量)的值，因为同步方式是一条一条执行的指令序列，每条语句都依赖上一条语句的执行。然而在异步方式运行的程序中，每条语句完成的时间是不确定的，也就难以确定某个时刻变量(共享变量)的值是什么；另外，如果我们想让异步程序像同步程序那样，按照一定的顺序执行，该怎么办呢？传统的解决方案是回调函数内嵌异步程序，也就是第一条异步程序的回调函数中调用第二条异步程序，第二条异步程序的回调函数中调用第三条异步程序。然而正是这种内嵌方式形成了众所周知的回调地狱问题，使我们的程序既不美观也难以维护。

**Promises**

ES6 中引入了 Promises 来解决回调地狱问题。promise 代表了异步程序，并在未来某个时刻完成。使用细节请谷歌百度。然而 promise 也有自身的缺点：

- 数据源产生多个值，比如鼠标移动事情或者文件系统的字节流；

- 没有失败重试的机制；

- 没有取消机制；

[转载地址](http://www.jianshu.com/p/0aad25e2e1be)

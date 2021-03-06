# 享元模式

> 定义：运用共享技术来有效支持大量细粒度的对象，是一种用于性能优化的模式

## 特性

1. 享元模式要求将对象属性划为内部状态和外部状态，且尽量减少共享对象的数量；可将内部状态相同的对象指定为一个共享对象，剥离外部对象储存在外部，当需要时将外部状态传入共享对象【以时间换空间】
   1. 内部状态：存储于对象内部、可被一些对象共享、独立于具体场景
   2. 外部状态：取决于具体场景、根据场景变化、不能被共享

## 应用

1. 系统因创建大量类似对象导致的内存占用过高问题【文件上传】
   1. 一个程序中使用大量类似对象
   2. 由于使用大量对象造成了很多开销
   3. 对象的大多数状态可变为外部状态
   4. 外部状态剥离后，可用相对较少的共享对象取代大量对象

## 引申

1. 对象池：将对象放入管理池中，当不需要对象时，对象池不会销毁对象，而是将对象回收到池中，下次需要的时候再从池中拿出，同时若不够，再创建一些新的对象，以补齐剩下的对象【dom操作】

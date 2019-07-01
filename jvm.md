# jvm

*OOM:*

![oom](oom.jpeg)

*方法区:*

> jdk version < 1.8  永久代 jvm堆内存

	1. -XX:PermSize(方法区初始大小)
	2. -XX:MaxPermSize(方法区最大大小,java.lang.OutOfMemoryError: PermGen)


>jdk version >= 1.8	元数据区 本地内存

	1. -XX: MetaspaceSize(元空间初始大小)
	2. -XX: MaxMetaspaceSize(元空间最大大小,java.lang.OutOfMemoryError: Metadata space)

  

1. 程序计数器:

	- 线程正在执行的字节码代码的行号
	- 线程隔离
	- 线程执行native方法时值为null

2. 元空间(metaspace):(1.8以后方法区的实现)
	- 放虚拟机加载的类信息(版本,字段，方法，接口)
	- 静态变量
	- 常量
	- 常量池:编译期生成的各种字面常量和符号引用

3. 堆(存放对象信息)

	![heap](heap.jpeg)

4. 虚拟机栈(方法执行的内存模型)

	![stack](jvm_stack.jpeg)
	
	- 局部变量；
	- 对象的引用；
	- 操作数栈；
	- 动态链接；
	- 方法出口；
	
5. 本地方法栈(虚拟机使用native方法)
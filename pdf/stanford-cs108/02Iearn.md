## Shallowness in Java

java中，= 是浅拷贝，也就是只拷贝指针不拷贝对象

默认的.equals()方法比较的是指针

- `System.arraycopy(source-array, source-index, dest-array, dest-index, lengthto-copy);` 可能比写循环更快

- Arrays.equals(a, b) 对一维数组每个元素调用equals()
- Arrays.deepEquals() 对多维数组每个维度检查
- java的多维数组中，每一维度有一个额外数组存储指向下一维数组位置的指针，故System.arraycopy()对二维数组来说，拷贝的是指向下一维数组的指针



## Package/Import

在编译时，包名在JVM中用的全名

java是动态编译的（与c不同）

‘.*’不会搜索子目录

import语句多少不会是代码变大/变慢



## Java Command Line

使用 javac 进行编译`javac *.java`，生成.class文件

使用java运行.class文件，如`java hello`



## Static

通常变量、方法与类的对象相关联，被static修饰的变量方法直接与类相关联



所有类共享同一个静态变量

通常用Classname.variablename来强调静态变量

静态函数没有接收对象
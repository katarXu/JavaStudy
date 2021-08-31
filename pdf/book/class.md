## 面向对象的好处

易维护、扩展

效率高



## 自定义类

```java
class ClassName{
    constructor
   	...
    method
    ...
    field
}
```



### 构造器

- 与类同名
- 伴随new操作一起调用

### 域和方法

- 数据域最好设置为私有，方便调试

- 可以设置公有的域访问器方法和域更改器方法

- 注意不要编写返回引用可变对象的方法，会破坏封装性，如果需要，应该先对他进行克隆

  ```java
  public int[] getArray(){
      return (int[]) a.clone();
  }
  ```

- 一个方法可以访问所属类的所有对象的私有数据

  ```java
  class ClassName{
  	boolean equals(ClassName other){
      	return element.equals(other.element);
  	}
  }
  
  //可以这样，equals方法能访问ClassB.element
  ClassA.equals(ClassB);
  ```

  

### 静态域和静态方法

- 该类的所有实例共享同一个静态方法和静态域



## 对象构造

- 如果某个域没有被显示赋值则会置零
- 如果给出了构造器，则类不会有隐式的默认构造器
- 在一个构造器方法中可以用`this(arguments, ...)`调用另一个构造器方法
- 可以在类中单独写一个初始化块，这样在构造对象时会默认执行该块的内容（不常用），可以在块前加上static关键字来初始化静态变量



## 对象析构

由于java有GC功能，所以不支持析构器

java中可以在类中添加`finalize`方法，在GC回收对象前调用，但由于不知道什么时候调用，故不鼓励使用



## 包

### import

- 同名时需要加完整的包名

- 静态导入：`import static java.lang.System.*;`，可以使用`System`类的静态方法和静态域

### 将类放入包中

如果没有package语句，源文件中的类会被放入默认包(default package)中

如果有`package com.corejava;`这样的语句，类会放入`com\corejava`目录下

### 包作用域

在包内，有public修饰符的类中的变量可以被所有包中的任意类访问

没有修饰符的变量为default，相当于c++中的friendly，只能被本包下的同种类访问

| 作用域    | 当前类 | 同一package | 子孙类 | 其他package |
| --------- | ------ | ----------- | ------ | ----------- |
| public    | √      | √           | √      | √           |
| protected | √      | √           | √      | ×           |
| friendly  | √      | √           | ×      | ×           |
| private   | √      | ×           | ×      | ×           |


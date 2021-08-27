## 字符串

相当于String类的实例

可以用+拼接，不可修改（便于共享），类似c++中的char * const

- 当用另一字符串替代当前字符串时，会新申请一片空间指向新字符串





## 代码点和代码单元

字符串由char序列组成，采用UTF-16编码，大部分字符一个代码单元就能表示，部分字符需要一对代码单元

`length()`方法返回的是代码单元的数量

实际长度（代码点数量）通过`codePointCount(start,end)`来获得

```java
char charAt(int index);
//返回给定位置的代码单元
int codePointAt(int index);
//返回对应位置开始或结束的代码点
int offsetByCodePoints(int startIndex, int cpCout);
//返回从startIndex代码点开始，位移cpCount个代码点后的代码单元索引
int length();
int codePointCount(int startIndex, int endIndex);
//返回[startIndex, endIndex)间的代码点数量

String substring(int beginIndex);
String substring(int beginIndex, int endIndex);
String toLowerCase();
String toUpperCase();
String trim();
//去掉头部和尾部的空格

int compareTo(String other);
//如果字符串相等返回0，否则返回this-other的差值（第一个字母）
boolean startWith(String prefix);
boolean endWith(String suffix);
boolean equals(String other);

int indexOf(String str);
int indexOf(String str, int fromIndex);
int indexOf(int cp);
int indexOf(int cp, int fromIndex);
int lastIndexOf(String str);
int lastIndexOf(String str, int fromIndex);
int lastIndexOf(int cp);
int lastIndexOf(int cp, int fromIndex);
//返回字符串中与str或cp第一个/最后匹配的开始位置，不存在则返回0
```



## 字符串构造

字符串连接的方式需要构造新的String对象，耗费时间空间。

使用StringBuilder类来避免这些问题（相当于一个字符数组）

```java
StringBuilder();

int length();
String toString();

void setCharAt(int i, char c);
StringBuilder append(String str);
StringBuilder append(char c);
StringBuilder appendCodePoint(int cp);
StringBuilder insert(int offset, String str);
StringBuilder insert(int offset, char c);
StringBuilder delete(int startIndex, int endIndex);
```




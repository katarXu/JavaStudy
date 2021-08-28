## 输入

System.in 标准输入

`File(String fileName)`

### Scanner类

```java
Scanner(InputStream in);
Scanner(File f);
String nextLine();
String next();
int nextInt();
double nextDouble();

boolean hasNext();
boolean hasNextInt();
boolean hasNextDouble();
```

### Console类

```java

```

## 输出

```java
PrintWriter(File fileName);
System.out.print();
```



## 抽象类InputStream/OutputStream

```java
abstract int read();	
//读入一个字节，返回该字节，碰到结尾返回-1
int read(byte[] b);		
//读入字节至数组b，返回实际读入的字节数，碰到结尾返回-1，最多读入b.length个字节
int read(byte[] b, int off, int len);
//off: 偏移量，len: 最大数量
long skip(long n);
//在输入流中跳过n个字节，返回实际跳过的字节数（可能碰到流的末尾）
int available();
//返回在不阻塞的情况下可用的字节数
void close();
//关闭输入流
void mark(int readlimit);
//在输入流当前位置打标记（不是所有流都支持），如果已读入字节多于readlimit，则忽略此标记
void reset();
//返回到最后的标记，若无标记则不返回
boolean markSupported();
//返回是否支持打标记
```

```java
abstract int write();
void write(byte[] b);
void write(byte[] b, int off, int len);
void close();
void flush();
//清空输出流，也就是将缓冲区的数据发送到目的地
```

- FileInputStream、InputStreamReader

  ```java
  public static void main(String[] args) throws IOException {
  	InputStreamReader in = new InputStreamReader(System.in);
  	byte b = (byte) in.read();
  	do {
  		System.out.print(b);
  		b = (byte) in.read();
  	}while(b != '\r');
  }
  ```

  

  


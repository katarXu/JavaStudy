## 大数值

没有重载运算符，使用add、multiply等方法进行运算



```java
BigInteger add(BigInteger other);
BigInterger subtract(BigInteger other);
BigInteger multiply(BigInteger other);
BigInteger divide(BigInteger other);
BigInteger mod(BigInteger other);

bool compareTo(BigInteger other);

static BigInteger valueOf(long x);
//返回值等于x的大整数
```



```java
BigDecimal add(BigDecimal other);
BigDecimal substract(BigDecimal other);
BigDecimal multiply(BigDecimal other);
BigDecimal divide(BigDecimal other);
BigDecimal mod(BigDecimal other);

bool compareTo(BigDecimal other);

static BigDecimal valueOf(long x);
static BigDecimal valueOf(long x, int scale);
//返回值为x或x/10^scale的一个大实数
```


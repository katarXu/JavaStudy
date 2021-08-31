## 声明和初始化

```java
int[] a = new int[100];
int[] b = {1, 2, 3};
int[] c = new int[]{1, 2, 3};
```

- 数组创建后不能改变数组大小

- 数组长度可以为0



## 数组拷贝

'=' : 可以将一个数组变量拷贝给另一个（拷贝指针，两个变量指向同一个数组）

`Arrays.copyOf(type[] a, int length)`方法 : 拷贝到新数组中，多余元素置零，超出则截断

`System.arraycopy(type[] from, int fromIndex, type[] b, int toIndex, int count)`方法 : 需要足够的空间



## 数组排序

`Arrays.sort` : 使用优化的快速排序





```java
static String toString(type[] a);

static type copyOf(type[] a, int length);
static type copyOf(type[] a, int start, int end);	//eclipse好像不支持
//length或end大于a.length时多余元素置零
static type sort(type[] a);
static int binarySearch(type[] a, type v);
static int binarySearch(type[] a, int start, int end, type v);
//二分查找，成功返回下标值，失败返回负数r，-r-1对应v的插入值
static void fill(type[] a, type v);
//初始化所有元素为v
static boolean equals(type[] a, type[] b);
```



## 多维数组

```java
int[][] arr1 = new int[n][m];
int[][] arr2 = { {1,2},{3,4}};
```

- 可以是不规则数组
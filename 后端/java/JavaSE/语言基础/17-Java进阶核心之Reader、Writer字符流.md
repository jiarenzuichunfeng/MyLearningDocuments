# 15-Java进阶核心之Reader、Writer字符流

## Java进阶核心之Reader

* Reader是输入字符流的父类，他是一个抽象类，部分库不推荐使用Reader/Writer

* ```java
  int read()
  //一个字符一个字符的读，只能用来操作文本（不能写图片、音频、视频）
  int read(char cbuf[])
  // 从输入字符流中读取一定数量的字符，并将其存储再缓冲区数组cbuf中，返回实际读取的字符数，如果已经到达流末尾没有可用的字节，则返回-1
  int close() throws IOException
  // 关闭输入流
  ```

* 常见子类

  * FileReader 用来读取字符文件的实现类

    ```java
    public FileReader(String fileName) throws FileNotFoundException {
        super(new FileInputStream(fileName));
    }
    
    public FileReader(File file) throws FileNotFoundException {
        super(new FileInputStream(file));
    }
    ```


## Java进阶核心之Writer

* Writer是输出字符流的父类，他是一个抽象类
* ```java
  public void write(int c) throws IOException
  // 直接将int型数据作为参数的话，是不会写入数字的，而是先将数字按照ascll码转换为相应的字符，然后写入
    public void write(String str) throws IOException
    // 要想实现数字和中文的写入，必须要用Striong为参数的Writer
    public abstract void write(char cbuf[],int off,int len) throws IOException
    // 将cbuf字符数组的一部分写入到流中，但不能写len个字符取决于cbuf中是否有那么多
    void flush() throws IOException
    //writer是写到缓冲区中，可以认为是内存中，当缓冲区满时系统会自动将缓冲区的内容写入文件，但是一般还有一部分有可能会留在内存这个缓冲区中，所以需要调用flush清空缓冲区数据
    void close() throws IOEXception
    //关闭流
  ```
* 常见子类

  * FileWriter 用来写出字符文件的实现类

    ```java
    public Filewriter(String fileName) throws IOExcepion
      // 如果文件不存在，这会自动创建。如果文件存在，则会覆盖
      public Filewriter(File file) throws IOExceptiong
      // 如果文件不存在，会自动创建，如果文件存在，则会覆盖
      public FileWriter(String FileName,boolean append) throws IOException
      // 加入true，会实现对文件的续写，false则会覆盖
      public FileWriter(File file,boolenan append) throws IOException
      // 加入true，会实现对文件的续写，false则会覆盖
    ```


## Buffered Reader 字符输入缓冲流

* 为了提高单个字符读写的效率，进行字符批量的读写；为了提高字符流读写的效率，引入了缓冲机制
* 采用包装设计模式
* BufferedReader
  * 当BufferdeReader在读取文本文件时，会先尽量从文件中读入字符数据并放满缓冲区，而之后若使用read（）方法，会先从缓冲区中进行读取，如果缓冲区数据不足，才会再从文件中读取
  
  * 构造函数
  
    ```java
    BufferedReader(Reader in)
    BufferedReader(Reader in,int sz)
      // 创建一个使用指定大小输入缓冲区的缓冲子u发输入流
    ```

* 常用API

  ```java
  	boolean ready()
      //判断此流师傅已准备好被读取，依赖其他流，所以一般需要做判断
  	int read()
      //读取单个字符
    intread(char[] cbuf,int off, int len)
      // 读取一部分字符到数组里面，从数组下标off处放置length长度的字符
    String readLine()
      //读取一整行文本行，返回一整行字符串，如果读到行尾了就返回null，注意返回的一行字符中不包含换行符
    void close()
      // 关闭
  ```


## Buffered Writer字符输出缓冲流

* 构造函数

```java
BufferedWriter(Writer in)
BufferedWriter(Writer in,int sz)
```

* 常用API

  ```java
    void writer（int c）
    // 写入一个字符
     void writer（char[] cbuf,int off,int len）
      //写入字符数组的一部分，通过off和len控制
      void writer(String s,int off,int len)
      //写入字符数组的一部分，通过off和len控制
      void newLine()
      //写入一个换行符号
      void close()
      //关闭流
      void flush（）
      //清除缓冲区
  ```

## InputStreamReader

* 背景

  * 计算机存储的单位是字节，从持久化设备读取到程序中是解码，从程序写到持久化设备中是编码不管是编码还是解码，不同字符集解码成字符需要不同的个数，因此字节流读取容易出错，因此需要一个流，把字节流的字节进行缓冲后，在通过字符集解码成字符返回

* InputStreamReader（继承Reader）

  * 将字符流转换为字符流。字节流通向字符流的桥梁，如果不指定字符集编码，则解码工程中将使用平台默认的字符编码
  * 文件存储和读取编码要一致

* 构造函数

  ```java
  //使用系统默认编码
  public InputStreamReader(InputStream in)
  //指定编码集创建对象
  public InputStreamReader(InputStream in,String charsetName)
  ```

* 常用API

  ```java
  	boolean ready()
      //判断此流师傅已准备好被读取，依赖其他流，所以一般需要做判断
  	int read()
      //读取单个字符
    intread(char[] cbuf,int off, int len)
      // 读取一部分字符到数组里面，从数组下标off处放置length长度的字符
    String readLine()
      //读取一整行文本行，返回一整行字符串，如果读到行尾了就返回null，注意返回的一行字符中不包含换行符
    void close()
      // 关闭
  ```

## outputStreamWriter

* outputStreamWriter（继承Writer）
  * 将字符流转换为字节流，字符流通向字符流的桥梁，如果不指定字符集编码，则解码过程中将使用平台默认的字符编码。

* 构造函数

  ```java
  //使用系统默认编码
  public outputStreamWriter(outputStream in)
  //指定编码集创建对象
  public outputStreamWriter(outputStream in,String charsetName)
  ```

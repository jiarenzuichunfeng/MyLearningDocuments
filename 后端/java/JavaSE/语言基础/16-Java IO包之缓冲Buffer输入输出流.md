# 16-Java IO包至缓冲Buffer输入输出流

* 什么是缓冲 Buffer
  * 他是内存空间的一部分，在内存空间中预留了一定的存储空间，这些存储空间用来缓冲输入或输出的数据，这部分空间就叫做缓冲区，缓冲区是具有一定大小的。
* 为啥要用缓冲
  * 缓冲，缓和冲击，例如操作磁盘比内存慢很多，所以不用缓冲区效率很低
  * 数据传输速度和数据处理的速度存在不平衡

* Java IO包里面有两个缓冲类（高级类）

  * BufferInputStream 和 BufferOutputStream
  * 采用包装设计模式
  * 画图

* BufferInputStream 缓冲字节输入流

  * BufferedlnputStream 通过预先读入一整段原始输入流数据至缓冲区中，而外界对BufferedInputStream的读取操作实际上是在缓冲区上进行，如果读取的数据超过了缓冲区的范围，那么Bufferedlnputstream负责重新从原始输入流中载入下一截数据填充缓冲区，然后外界继续通过缓冲区进行数据读取。

  * 好处:避免了大量的磁盘IO，原始的InputStream类现的read是即时读取的，每一次读取都会是一次磁盘IO操作(哪怕只读取了1个字节的数据）如果数据量巨大，这样的磁盘消耗非常可怕。

  * 缓冲区的实现：读取可以读取缓冲区的内容，当读取超过缓冲区的内容后在进行一次磁盘IO，载入一段数据填充缓冲，下一次读取一般情况就直接可以从缓冲区读取， 减少了磁盘IO。

  * 默认缓冲区大小是8k

  * 常见的构造函数

    ``` java
    // 对输入流进行包装，里边默认的缓冲区是8k
    	public BufferenInputStream(InputStream in)
    // 对输入流进行包装，创建具有指定缓冲区大小
      public BufferenInputStream(InputStream in,int size)
    ```

  * 常用的两个方法

    ```java
    // 从输入流中读取一个字节
    	public int read（）
    // 从字节输入流中给定偏移量处开始将各字节读取到指定的byte数组中。
    	public int read（byte[] buf,int off,int len）
    // 关闭释放资源，关闭的时候这个流即可，InputStream会在里面被关闭
    	void close（）
    ```

* BufferOutputStream 缓冲字节输出流

  * 常见的构造函数

    ``` java
    // 对输入流进行包装，里边默认的缓冲区是8k
    	public BufferenOutputStream(InputStream in)
    // 对输入流进行包装，创建具有指定缓冲区大小
      public BufferenOutputStream(InputStream in,int size)
    ```

  * 常用的三个方法

    ```java
    // 向输出流中输出一个字节
    	public void write（）
    // 将制定byte数组中从偏移量off开始的len个字节写入缓冲的输出流
    	public void write（byte[] buf,int off,int len）
    // 刷新此缓冲的输出流，强制使所有缓冲的输出字节被写出到底层输出流中
       public void flush()
    // 关闭释放资源，关闭的时候这个流即可，OutputStream会在里面被关闭，jdk7新特性try（在这里声明的会自动关闭）
    	void close（）
    ```




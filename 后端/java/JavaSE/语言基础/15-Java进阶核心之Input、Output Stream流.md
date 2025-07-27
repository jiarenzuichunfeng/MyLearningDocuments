# 15-Java进阶核心之Input、Output Stream流

* IO：Input/Puput 即输入输出
  * 输出流：程序（内存）---》外界设备
  * 输入流：外界设备 --》 程序（内存）
* 处理数据类型分类
  * 字符流：处理字符相关，如处理文本数据。Reader/Writer
  * 字节流：处理字节相关，如声音或者图片等二进制.InputStream/OutputStream
  * 两者区别
    * 字节流以字节（8bit）为单位，字节流以字符为单位，根据码表映射字符，一次可能读多个字节
    * 字节流可以处理几乎所有文件，字符流只能处理字符类型的数据
    * 功能不同，但是具有共性内容，通过不断抽象形成4个抽象类，抽象类下面有很多子类是具体的实现
      * 字符流 Reader/Writer
      * 字节流 InputStream/OutputStream
* IO流相关类体系概览
  * ![image-20250519172014169](D:\study\lianxi\MyLearningDocuments\images\image-20250519172014169.png)

## Java输入流InputStream讲解

* InputStream是输入字节流的父类，他是一个抽象类（一般用他的子类）

  ``` java
  int read（）
   // 从输入流中读取单个字节，返回0到255范围内的int字节值，字节数据可直接转为int类型，如果已经到达流末尾而没有可用的字节，则返回-1
    int read（byte[] buf）
    // 从输入流中读取一定数量的字节，并将其存储在缓冲去数组buf中，返回实际读取的字节数
    long skip(long n)
    //从输入流中跳过并丢弃n个字节的数据
    int available()
    //返回这个流中有多少字节数，可以把buf数组长度定位这个
    void close() throws IOException
    //关闭输入流并释放与该流相关联的系统资源
  ```

* 常见的子类

  * FileInputStream

    * 抽象类InputStream用来具体实现类的创建对象，文件字节输入流，对文件数据以字节的形式进行读取操作

    * 常用构造函数

      ```java 
      //传入文件所在地址
      public FileInputStream（String name）throws FileNotFoundException
      //传入文件对象
      public FileInputStream（File file）throwsFileNotFoundException
      ```


## Java输出流OutPutStream讲解

* OutputStream是输出字节流的父类，他是一个抽象类（一般用他的子类）

  ``` java
  void write(int b)
  // 将制定的字节写入输出流
   void write(byte[] b) rhrows IOException
    //将b.length个字节的byte数组写入当前输出流
    void flush() throws IOException
    //write是写入到缓冲区中，可以认为是内存中，当缓冲区满时系统会自动将缓冲区的内容写入文件，但是一般还有一部分可能会留在内存这个缓冲区中，所以需要调用flush清空缓冲区数据
    void close() throws IOException
    //关闭输入流并释放与该流相关联的系统资源
  ```

* 常见的子类

  * FileOutputStream

    * 抽象类OutputStream用来具体实现类的创建对象，文件字节输出流，对文件数据以字节的形式进行输出操作

    * 常用构造函数

      ```java 
      //传入文件所在地址
      public FileOutputStream（String name）
      //传入目标输出文件对象
      public FileOutputStream（File file）
       //传入目标输出文件对象，是否可以追加内容
        public FileOutputStream(File file,boolenan append)
      ```

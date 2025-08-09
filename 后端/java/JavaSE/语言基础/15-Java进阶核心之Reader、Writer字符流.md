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


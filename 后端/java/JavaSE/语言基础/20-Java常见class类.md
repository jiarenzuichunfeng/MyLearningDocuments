# 20-Java常见class类

* Java顶级对象之Object对象
  * Object 类位于java.lang包中，Java.lang包包含着Java最基础和核心的类，在编译时会自动导入
  
  * Object类是所有Java类的祖先每个类都是用Object作为超类
  
  * 常见方法
  
    ```java
    public final native Class<?> getClass()
    // 获取对象的运行时class对象，Class对象就是描述对象所属类的对象，类的对象可以获取这个类的基本信息
    public native hashCode()
    // 获取对象的散列值，集合框架中应用
    public boolean equals(Object obj)
    // 比较两个对象，如果这两个对象指向的时同一个对象返回true，否则返回false
    public String toString()
    //用于返回一个可代表对象的字符串
    ```
    
    * native 方法，本地方法，具体是用C（C++）在DLL中实现的，然后通过JNI调用
    * 什么是JNI：Java平台和本地C（C++）代码进行互操作的API
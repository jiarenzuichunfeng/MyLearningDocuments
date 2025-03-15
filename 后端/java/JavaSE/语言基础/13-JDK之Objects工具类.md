# 新版JDK之Objects工具类

* Objects工具类讲解
  * jdk1.7引进的工具类，都是静态调用的方法，jdk1.8新增了部分方法
  * 重点方法
    * equals
      * 用于字符串和包装对象的比较，先比较内存地址，再比较值
    * deepEquals
      * 数组的比较，先比较内存地址，再比较值，如String/char/byte/int数组，或者包装类型Integer等数组
    * hashCode
      * 返回对象的hashCode，若传入的为null，返回0
    * hash
      * 传入可变参数的所有值的hashCode的总和，底层调用Arrays.hashCode

# 新版JDK之重写HashCode和equals

* HashCode方法

  * 顶级类Object里面的方法，所有类都是继承于Object的，返回值int类型
  * 根据一定的hash规则（存储地址、字段、或者长度等），映射成一个数值，即散列值

* Equals方法

  * 顶级类Object里面的方法，所有类都是继承于Object的，返回值boolean类型

  * 根据自定义的匹配规则，用于匹配两个对象是否一样，一般逻辑是如下

  * ```java
    //判断地址是否一样
    //非空判断和class类型判断
    //强转
    //对象里面的字段一一匹配
    ```

* 重写规则

  ```java
  ```


* 问题：当向集合中插入对象时，如何判断在集合中是否已经存在该对象，比如Set确保存储对象的唯一，并判断是不是同个对象呢？
  * 依据hashCode和equals进行判断，所以Set存储的对象必须重写这两个方法
  * 判断两个对象是否一样，首先判断插入obj的hashCode值是否存在，hashcode值不存在则直接插入集合，值存在则还需判断equals方法判断对象是否相等

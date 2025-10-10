# System类

* 他是系统类，在java.long包中，提供了一些系统属性信息和系统操作

* final类型，构造函数被私有化

* 常用API

  * ```
           //输入输出包含的三个成员变量，分别是in，out，err
           System.out  //常用于调试
            System.in // 用于数据读取
             System.err//用于错误输出
           // 打印毫秒数（时间戳）
            System.out.println(System.currentTimeMillis());
    //        打印系统信息
            System.out.println(System.getProperties());
            // 根据指定key获取系统属性
            System.out.println(System.getProperties(key));
    ```

# Scanner类

* 常用api
  * 获取输入的字符串，以回车换行符为结束表示
    * public String nextLine()
  * 获取输入的整数
    * public int nextInt（）
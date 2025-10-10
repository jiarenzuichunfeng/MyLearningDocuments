# String类

* 字符串对象String
  * 字符串时对象，不是简单的数据类型
  * 封装在java.lang包，自动导入
* 创建字符串对象
  * String str = new String（"值"）
  * String str = "值"
* 字符串比较内容是否相等
  * == 是比较地址
  * equals（）方法是比较内容
* 常用的API

  ```java
         String str1 = new  String("abc");
          String str2 = "ABc";
  //        System.out.println(str1 == str2); // 地址比较
  //        System.out.println(str1.equals(str2)); // 值比较
          String str = "小弟课堂xdclass.net";
  //      获取字符串长度
          System.out.println(str.length());
  //      通过下标获取字符
          char ch = str.charAt(5);
          System.out.println(ch);
  //      字符串比较
          boolean result = str1.equals(str2);
          System.out.println(result);
  //        字符串比较忽略大小写
          boolean result1 = str1.equalsIgnoreCase(str2);
          System.out.println(result1);
  //        查找字符串出现的位置
          int index = str.indexOf('.');
          System.out.println(index);
  //        字符串截取
          String result2 = str.substring(index);
          System.out.println(result2);
          String result3 = str.substring(1,3); // 左闭右开
          System.out.println(result3);
  //      字符串拆分
          String [] arr = str.split("\\."); // 特殊字符需要转义
          System.out.println(arr.length);
  //        字符串替换
          String tempDir = str.replace("x","a");
          System.out.println(tempDir);
  //        字符串大小写转换
         String a = str.toUpperCase();
         String b = str.toLowerCase();
          System.out.println(a);
          System.out.println(b);
  //        字符串去空格
          str.trim();
          System.out.println(str);
  ```

* 其他类型和字符串互相转换

  * ```
    boolean bool = Boolean.parseBoolean("false"); //字符串类型转换为布尔类型 
    int integer = Integer.parseInt("0");// 字符串类型转换为整形
    long longInt =  Long.parseLong("0");// 字符串类型装换位长整形
    float floatFloat = Float.parseFloat("0.01");// 字符串类型转换为单精度浮点型
    double doubleDouble = Double.parseDouble("0.01");// 字符串类型转换为双精度浮点型
    ```


# 19-Java时间日期

* 时间基础知识

  ```
  时区：整个地球分为二十四时区，每个时区都有自己的本地时间。
  为了统一起见，使用一个统一的时间，称为全球标准时间（UTC）
  UTC与格林尼治平均时（GMT） 差不多一样
  CST（北京使劲按）UTC+8
  
  时间戳：自1970年1月1日（09：00：00 GMT）至当前时间的总秒数，它 也被称为unix时间戳，广泛的运用在知识产权保护、合同签字、金融账户、电子报价投标、股权交易等方面
  格式多种：2050-10-31、2050：10：31、2050/10/31
  
  ```

* java.util包提供了Date类来封装当前的日期和时间

* 构造函数

  ``` java
  // 当前时间
  Date（）
  // 从1970年1月1日起的毫秒数作为参数
  Date（long millisec）
  ```

* 常见方法

  ```java
  //返回自1970年1月1日00：00：00 GMT 以来此Date对象来表示的毫秒数
  long getTime（）
  //调用此方法的Date对象在指定日期之后返回true，否则返回false
  boolean after（Date date）
  //调用此方法的Date对象在指定日期之后返回true，或者返回false
  boolean before（Date date）
  ```

## JDK8之时间日期处理类

* 核心类

  ``` java
  LocalDate:不包含具体时间的日期
  LocalTime:不含日期的时间
  LocalDateTime:包含时间和日期
  ```

## 时间日期格式化

* 常用的占位符

  ```java
  Y 四位数年份
  M 月
  d 日
  h 时 在上午或下午（1~12）
  H 时 在一天中（1~24）
  m 分
  s 秒
  S 毫秒
  ```

* JDK8引入了线程安全的日期与时间DateTimeFormatter

* 计算时间差 java.time.Duration
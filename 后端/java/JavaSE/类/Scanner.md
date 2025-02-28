# 用户交互Scanner

java.util.Scanner是java5的新特征

基本语法：Scanner 名字 = new Scanner（System.in）

通过Scanner类的next（）与nextLine（）方法获取输入的字符串，在读取前我们一般需要使用hasNext（）与hasNextLine（）判断是否还有输入的数据	

凡是输入IO流的类如果不关闭会一直占用资源

名字.close()

next()

  		1. 一定要读取到有效字符后才可以结束输入
  		2. 对输入有效字符之前遇到的空白，next（）方法会自动将其去掉
  		3. 只有输入有效字符后才将其后面的输入的空白作为分隔符或者结束符
  		4. next（）不能得到带空格的字符串

nextLine（）

 	1. 以Enter为结束符，也就是说nextLine（）方法返回的是输入回车之前的所有字符
 	2. 可以获得空白


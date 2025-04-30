# Java进阶核心之File文件和目录

## 计算机文件和路径介绍

* 什么是计算机文件（File）
  * 以计算机硬盘为载体存储在计算机上的信息集合，可以是文本、图片、视频、程序等，文件一般有扩展名，表示文件的类型
* 文件目录（Directory）
  * 就是我们一般称呼的文件夹，为了便于对文件进行存取和管理
  * 文件目录由文件目录相组成的。文件目录分为一级目录、二级目录和多级目录。多级目录结构也称为树形结构，在多级目录结构中，没一个磁盘有一个根目录，在根目录中可以包含若干个子目录和文件，在子目录中不但可以包含文件，而且还可以包含下一级子目录
* 区分两个斜杠
  1. 斜杠：“/” 与 反斜杠：“\”
  2. 反斜杠（\）是一个特殊的字符，被称为转义字符，用来转移后面一个字符。转义后的字符通常用于表示一个不可见的字符或具有特殊含义的字符。
  3. 在Java中的字母前面加上反斜杠来表示常见的那些不能显示的ASCII字符，我们称之为转义字符
* 相对路径
  * 相对某个基准目录或者文件的路径，./ 表示当前路径；../ 表示上级目录
* 绝度路径
  * 存储在硬盘上的真正路径
* Windows路径分割符
  * \表示Windows系统文件目录分隔符
* Linux和Mac路径分隔符
  * /表示Linux和Mac路径分隔符

## Java核心知识之File类讲解

* 程序代码和文件目录的关系：主要就是对文件和目录进行增删改查，俗称CRUD

* 简单了解IO。即Input / Output
  * 把内存中的数据存储到持久化设备上的动作称为输出，Output操作
  * 把持久化设备的数据读取到内存中的动作称为输入，Input操作
  * 一般把输入和输出的动作称为IO操作，IO也分网络IO，文件IO

* Java文件类File
  * 主要是计算机文件和目录的操作，即对文件和目录的增删改查

  * File类表示磁盘中存在的文件和目录

  * File类的包名是Java.io,也实现了Serializable，Comparable两大接口以便于其对象可序列化和比较

  * File.separator目录分隔符，在不同的系统下不一样

    ``` java
     String dir = "D:\\study\\lianxi\\";
            String name = "a.txt";
    //        File file = new File(dir,name);
            File file = new File(dir);
            System.out.println(file.getPath());
    
    //      文件的查询和判断
            System.out.println(file.separator);
            System.out.println("基本路径 getPath（）" + file.getPath());
            System.out.println("文件名 getName（）" + file.getName());
            System.out.println("绝对路径 getAbsolutePath（）" + file.getAbsolutePath());
            System.out.println("父路径名 getParent（）" + file.getParent());
            System.out.println("是否是绝对路径 isAbsolute（）" + file.isAbsolute());
            System.out.println("是否是一个目录 isDirectory（）" + file.isDirectory());
            System.out.println("是否是一个文件 isFile（）" + file.isFile());
            System.out.println("文件或目录是否存在 exists（）" + file.exists());
    
            System.out.println("目录中的文件和目录的名称所组成的字符串数组 list（)");
            String[] arr = file.list();
            for (String temp : arr) {
                System.out.println(temp);
            }
    
            // 创建指定目录
            File mkdirFile = new File(dir+"\\xd");
            mkdirFile.mkdir();
    
            // 创建多级目录
            File mikedirsFile = new File(dir+"\\xd\\aa\\bb\\cc");
            mikedirsFile.mkdirs();
    
            // 创建一个文件
            File newFile = new File(dir+"\\xxxx.txt");
    
            try {
                newFile.createNewFile();
            }catch (IOException e){
                e.printStackTrace();
            }
    
            // 删除文件
            // 注意：当前文件必须是最终文件才可以删除，如果是文件夹，里面含有文件，应该先删除里面的文件
            newFile.delete();
    ```

    注意：FIle的构造函数只是创建一个File实例，即使目录错误也不出报错，因为没对文件进行操作

### 作业

* 封装一个方法，传入一个路径，则在此路径下创建test文件夹

* 然后再test目录下创建10个文件夹，名称是1~10,然后再各个文件夹里面创建一个txt文本，名称也是1~10，重复调用此方法的话结果一样。

  ```java
  public static void main(String[] args) throws IOException {
          String dir = "D:\\study\\lianxi";
          wenjian(dir);
  //        wenjian(dir);
  
  //        createDir(dir);
      }
  
      public static void wenjian(String filename){
          String root = filename+File.separator+"test";
          // 声明file实例
          File file = new File(root);
          // 创建test目录
          if(!file.exists()){
              file.mkdir();
          }
          System.out.println(file);
          // 声明下一级目录
          String dir = root+File.separator;
          //
          for (int i = 0; i <= 10; i++ ){
              File file1 = new File(dir+File.separator+i);
              if(!file1.exists()){
                  file1.mkdirs();
              }
              System.out.println(file1);
              // 声明下一级的下一级目录
              String dir2 = dir+File.separator+i;
              File file2 = new File(dir2+File.separator+i+".txt");
              try {
                  if(!file2.exists()){
                      file2.createNewFile();
                  }
              } catch (IOException e) {
                  throw new RuntimeException(e);
              }
          }
      }
  
      public static void createDir(String path) throws IOException {
  
          String root = path+File.separator+"test";
          File rootDir = new File(root);
          if (!rootDir.exists()){
              rootDir.mkdirs();
          }
  
          for (int i=0; i<10;i++){
              String dirPath = root+File.separator+(i+1);
              File dirFile = new File(dirPath);
              if (!dirFile.exists()){
                  dirFile.mkdir();
                  String testPath = dirPath+File.separator+(i+1)+".txt";
                  File txtFile = new File(testPath);
                  if (!txtFile.exists()){
                      txtFile.createNewFile();
                  }
              }
          }
      }
  ```
  
  

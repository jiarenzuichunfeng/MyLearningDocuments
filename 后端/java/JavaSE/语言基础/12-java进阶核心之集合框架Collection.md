# Java进阶核心之集合框架Collection

## 计算机核心基础之大话数据结构

* 什么是数据结构

  ```
  数据结构是带有结构特性的数据元素的集合，他研究的是数据的逻辑结构和数据的物理结构以及他们之间的相互关系，并对这种结构定义相适应运算，设计出相应的算法，并确保经过这些运算以后所得到的新结构仍保持原来的结构类型
  
  简述：数据结构是相互之间存在一种或多种特定关系的数据元素的集合，即带“结构”的数据元素的集合。“结构”就是指数据元素之间存在的关系
  ```

* 数据结构有很多种，一般来说，按照数据的逻辑结构对其进行简单的分类，包括线性结构和非线性结构两类
  * 线性结构：各节点具有线性关系，有且仅有一个开始节点和一个终端节点
    * 栈、队列和串
  * 非线性结构：各节点之间具有多个对应关系，一个节点可能有多个直接前趋结点和多个直接后继结点
    * 数据、广义表、树结构和图结构

* 常用的数据结构入门
  * 栈Stack
    * 限制在表的一端进行插入和删除运算的线性表，通常称插入、删除的这一端为栈顶（Top），另一端为栈底（Bottom）
  * 队列Queue
    * 限制在表的一端进行插入，而在另一端进行删除。允许删除的一端称为队头（front），允许插入的一端称为队尾（rear）
  * 数组Array
    * 最基本的数据结构，他是将具有相同类型的若干变量有序的组织在一起的集合
    * 根据下标进行操作
  * 链表Linked List
    * 数据元素按照链式存储结构进行存储的数据结构，这种存储结构具有在物理上存在非连续的特点，每个数据节点包括数据域和指针域两个部分。其中指针域保存了数据借工中下一个元素存放的地址

## 计算机核心基础之散列表 Hash Table

* 什么是散列表

  * 散列表（Hash Table，也叫哈希表），是根据关键码值（Key Value）而直接进行访问的数据结构。也就是说，它通过把关键码值映射到表中的一个位置来访问记录，以加快查找速度。这个映射函数叫做散列函数，存放记录的数组叫散列表。

    给定表M，存在函数f（key），对任意给定的关键字值key，滴入函数后若能得到包含关键字的记录在表中的地址，则称表M为哈希（Hash）表，函数f（key）为哈希函数

  * 散列函数 能使对一个数据序列的访问过程更加迅速有效，通过散列函数，数据元素将被更快地定位

* 链式哈希表

  * 是由一组链表构成，每个链表都可以看做是一个“桶”，我们将所有的元素通过散列的方式放到具体的不同的桶中。
  * 插入元素时，首先将其建传入一个哈希函数，函数通过散列的方式告知元素属于哪个“桶”，然后在相应的链表插入元素。
  * 查找或删除元素时，用相同的方式先找到元素的“桶”，然后遍历相应的链表，知道发现我们想要的元素。

* 注意：

  * 应为每个“桶”都是一个链表，如果表变得太大，他的性能将会降低。
  * 哈希扩容：Bucket桶不够的话需要重新扩容，历史的数据需要重新Hash
  * 哈希冲突碰撞：不同的元素经过hash后命中相同的桶的位置
    * 更多资料 http://www.jianshu.com/p/a407ee0ce404

## Java进阶核心之Collection集合框架概要

* 集合容器主要用于保存对象，主要分类有三种List、Set、Map
  * List有序、重复的集合
    * 常见的List有Array List、Vector、Linked List
  * Set无序、不可重复
    * 常见的Set接口的实现类有Hash Set、Lined Hash Set和Tree Set这几类
  * Map键值对存储
    * 常见的Map接口实现类有Hash Map和Tree Map
* Collection接口有两个主要的子类List和Set，Nap不是Collection的子类，应为其本身就是一个顶层接口

## Java进阶核心之集合框架List介绍

* 什么是List数据结构

  ``` 
  List接口是一个有序的Collection，线性列表接口，能够精确的控制每个元素插入位置，能够通过索引（类似于数组的下标）来访问List中的元素，第一个元素的索引为0，而却允许有相同的元素，接口存储一组不唯一，有序（插入顺序）的对象。
  ```

* 常见的实现类

  * Array List

    * 基于数组实现，是一个动态的数组队列，但它和Java中的数组又不一样，它的容量可以自动增长
    * 可以存储任意多的对象，但是只能是存储对象，不能存储原生数据类型

  * Linked List

    * 基于的数据结构是链表，一个双向链表，链表的数据结构的特点是每个元素分配的空间不必连续
    * 插入和删除元素时的速度非常快，但是访问元素的速度较慢

  * 常见的List API语法

    ``` java
    // 创建对象，LinkedList和ArrayList api一样
    List<> list = new ArrayList<>();
    // 往容器里面添加对象
     数组名.add();
    //根据索引获取元素
     数组名.get(index)
    // 更新一个元素
    数组名.set(index,要输入的内容)
    // 返回大小
     数组名.size()
    // 根据索引删除一个元素
     数组名.remove(index)
    // 根据对象删除元素
    数组名.remove(内容)
    // 清空元素
     数组名.clear()
    // 是否为空
     数组名.isEmpty()
    ```
    
    ``` java
    // LinkedList 特有的api
    // 获取第一个元素
     数组名.getFinst();
    // 获取最后一个元素
     数组名.getLast();
    ```

* 两者常见的区别（面试题）

  * 两个都是List的接口，两个都是非线程安全的
  * Array List是基于动态数组的数据结构，Linked List是基于链表的数据结构
  * 对于随机访问get和set（查询操作），Array List要优于Linked List，应为Linked List要移动指针
  * 对于增删操作（add，remove）Linked List优于Array List

## Java进阶核心之集合框架Map

* 什么是Map数据结构
  * 底层就是一个数据结构，数组中的每一项又是一个链表，即数组和链表的结合体
  * Table是数组，数组的元素时Entry
  * Entry元素时一个key-value键值对，它持有一个指向下一个Entry元素的引用，Table数组的每个Entry元素同时也作为当前Entry链表的首节点，也指向了该链表的下一个Entry元素
* 常见的实现类
  * Hash Map
    * 一个散列桶（数组和链表），它存储的内容是键值对（key-value）映射
    * 是基于hashing的原理，使用put（key，value）存储对象到Hash Map中，使用get（key）从Hash Map中获取对象。当put（）方法传递建和值时，会先对建调用hash Code（）方法，计算并返回的hash Code是用于找到Map数组的bucket位置来存储Entry对象的，是非线程安全的，所以Hash Map操作的速度很快
  * Tree Map
    * 在数据的存储过程中，能够自动对数据进行排序，实现了Sotred Map接口，他是有序的集合
    * Tree Map使用的存储结构是平衡二叉树，也称为红黑树
    * 默认排序规则：按照key的字典顺序来排序（升序），也可以自定义排序规则，要实现Comparator接口
* 常用的 api语法

  ```java
  //往map里添加key-value
  数组名.put（key，value）
  // 根据key获取value
  数组名.get(key)
  // 判断是否包含某个key
    数组名.containskey（key）
    //返回map的元素数量
    数组名.size()
    //清空容器
    数组名.clear()
    //获取所有value集合
    数组名.value()
    //获取所有key集合
    数组名.keySet()
    //返回一个set集合，集合类型为Map.Entry，是Map声明的一个内部接口，接口为泛型，定义为Entry<k,v>
    // 它表示Map中的一个实体（一个key-value），主要有getkey（），getvalue（）方法
    Set<Map.Entry<String,String>> 名字 = map.entrySet()
    //判断map是否为空
    数组名.isEmpty()
  ```

* Map面试题

  * Hash Map和Tree Map应该怎么选择
    * Hash Map可以实现快速存储和检索，但缺点是包含的元素时无序的，适用于在Map中插入、删除和定位元素
    * Tree Map能便捷的视线对其内部元素的各种排序，但其一般性能比Hash Map差，适用于按自然顺序或自定义顺序遍历键
  * JDK1.7和JDK1.8中Hash Map的主要区别
    * 底层实现由之前的“数组+链表”改为“数组+链表+红黑树”
  * 什么时候开始转变
    * 当链表节点较少时仍然是以链表存在，当链表节点较多时，默认是大于8时会转为红黑树

## Java进阶核心之集合框架Set

* 什么是Set数据结构
  * Set相当于List是简单的一种集合，具有和Collection完全一样的接口，只是实现上不同，Set不保存重复的元素，存储一组唯一，无序的对象
  * Set中的元素是不能重复的，实现细节可以参考Map，因为这些Set的视线都是对应的Map的一种封装。比如Hash Set是对Hash Map的封装
  * Set底层是一个Hash Map，由于Hash Map的put（）方法时一个键值对，当新放入Hash Map的Entry中key与集合中原有的Entry的key相同（hash Code（）返回值相等，通过equals比较返回true），新添加的Entry的value会将覆盖原来Entry的value，但key不会有任何改变
  * 允许包含值为null的元素，但最多只能有一个null元素
* 常见的实现类
  * Hash Set
    * Hash Set类按照哈希算法来存取集合中的对象，存取速度比较快
    * 对应的Map是Hash Map，是基于Hash的快速元素插入，元素无顺序
  * Tree Set
    * Tree Set类实现了Sorted Set接口，能够对集合中的对象进行排序
* 两种常见区别
  * Hash Set不能保证元素的排列顺序，Tree Set是Sorted Set接口的唯一实现类，可以确保集合元素处于排序状态
  * Hash Set底层用的是哈希表，Tree Set用的是红黑树
  * Hash Set中的元素可以是null，但只能有一个，Tree Set不允许放入null
  * 一般使用Hash Set，如果需要排序的功能时，才使用Tree Set

## Java进阶核心之三大集合框架扩展

### Java集合框架遍历之迭代器（Iterator）

* 什么是迭代器Iterator
  * Iterator是Java中的一个接口，核心作用就是用来遍历容器的元素，当容器实现类Iterator接口后，可以通过调用Iterator（）方法获取一个Iterator对象
  * 为什么是调用容器里面的Iterator方法呢？
    * 因为容器的实现有多种，不同的容器遍历规则不一样，比如Array List、Linked List、Hash Set、Tree Set等，所以设计了Iterator接口，让容器本身去实现这个接口，实现里面的方法，从而让开发人员不用关心容器的遍历机制，直接使用对应的方法即可
  * 三个核心的方法
    * boolean hashNext（）
      * 用于判断Iterator内是否有下个元素，如果有则返回true，没有返回false
    * Object next（）
      * 返回Iterator的下一个元素，同时指针也会向后移动1位
    * void remove（）
      * 删除指针的上一个元素（容易出问题，删除元素建议不使用容器自己的方法）
      * 只有当next执行完后，才能调用remove函数
      * 如要删除第一个元素，不能直接调用remove（），要先next（）一下否则调用remove方法是会抛出异常的

### Java迭代器进阶和注意事项

* 迭代器遍历元素时不能通过Collection接口中的remove方法删除元素，只能用Iterator的remove方法删除元素；原因：某个线程在Collection上进行迭代时，不允许另一个线程修改Collection
* 迭代出的对象是引用的拷贝，如果修改迭代中的元素，那么就是修改容器对象本身
* 和for循环对比
  * for循环适合顺序访问，或者通过下标进行访问
  * 迭代器适合链式结构
  * 最终看使用场景，性能会有轻微的差别，但是可以忽略

## Java集合框架之Collections工具类

* Java里关于集合的工具类，包含有各种有关集合操作的静态多种方法，不能实例化（把构造函数私有化）

* 和Collection的区别

  * Collection是接口，提供了对集合对象进行基本操作的通用接口方法，List、Set等多种具体的实现类
  * Collections是工具类，专门操作Collection接口实现类里面的元素

* 常见方法

  * 排序 sort（List 数组名）

    * 按自然语言排序升序排序

      ``` java
       List<String> list = new ArrayList<>();
              list.add("bbb");
              list.add("aaa");
              list.add("ccc");
              System.out.println(list);
      
              //默认是升序
              Collections.sort(list, Comparator.naturalOrder());
              System.out.println(list);
             
      ```

    * sort(List 数组名，Comparator c)自定义排序规则，由Comparator控制排序逻辑

      ```java
       List<String> list = new ArrayList<>();
              list.add("bbb");
              list.add("aaa");
              list.add("ccc");
              System.out.println(list);
      // 降序
              Collections.sort(list, Comparator.reverseOrder());
              System.out.println(list);
      ```

  * 随机排序shuffle（List 数组名）

    ```java
     List<String> list = new ArrayList<>();
            list.add("1");
            list.add("2");
            list.add("3");
            list.add("4");
            list.add("5");
            list.add("6");
            list.add("7");
            list.add("8");
            list.add("9");
            list.add("10");
            list.add("J");
            list.add("Q");
            list.add("K");
           Collections.shuffle(list);
    
           System.out.println(list);
    ```

  * 获取最大元素max（Collection coll）默认比较，不适合对象比较

  * 获取最大元素max（Collection coll，Comparator comparator）

    ```java
     List<Student> list = new ArrayList<>();
            list.add(new Student("jack",26));
            list.add(new Student("tom",29));
            list.add(new Student("marry",32));
            list.add(new Student("tony",19));
            list.add(new Student("smith",41));
    
            System.out.println(list.toString());
    
            Student maxstudent = Collections.max(list, new Comparator<Student>() {
                @Override
                public int compare(Student o1, Student o2) {
                    return o1.getAge()-o2.getAge();
                }
            });
    
            System.out.println(maxstudent);
    
            Student minstudent = Collections.min(list,new Comparator<Student>() {
    
                @Override
                public int compare(Student o1, Student o2) {
                    return o1.getAge()-o2.getAge();
                }
            });
    
            System.out.println(minstudent);
    
    class Student{
        private String name;
        private int age;
        public Student(String name, int age) {
            this.name = name;
            this.age = age;
        }
    
        public void setAge(int age) {
            this.age = age;
        }
    
        public int getAge() {
            return age;
        }
    
        public String getName() {
            return name;
        }
    
        public void setName(String name) {
            this.name = name;
        }
    
        @Override
        public String toString() {
            return "Student{" +
                    "name='" + name + '\'' +
                    ", age=" + age +
                    '}';
        }
    }
    ```

  * 获取最小元素min（Collection coll）

  * 创建不可变集合unmodiflabllexxx()

    ```java
    List<String> list = new ArrayList<>();
            list.add("SpringBoot课程");
            list.add("架构课程");
            list.add("微服务SpringCloud");
            // 设置为只读集合
            list = Collections.unmodifiableList(list);
    
            list.add("html");
    
            Set<String> set = new HashSet<>();
            set.add("Mysql教程");
            set.add("Linux服务器教程");
            set.add("Git教程");
            
            set = Collections.unmodifiableSet(set);
    
            set.add("html");
    
            Map<String, String> map = new HashMap<>();
            map.put("key1", "value1");
            map.put("key2", "value2");
    
            map = Collections.unmodifiableMap(map);
    
            map.put("html","css");
    ```

## Java集合框架之Comparable排序接口

* 什么是Comparable
  * 是一个接口，定制排序规则
  * 对实现他的每个类的对象进行整体排序，里面compareTo方法是实现排序的具体方法
  * 比如Tree Set、SortedSet、Collections.sort()方法调用进行排序
  * String、Integer等类默认实现了这个接口
* 详解compareTo方法
  * 用于比较次对象和指定对象的顺序，o为要比较的对象
  * 返回int类型
    * 大于0，表示this大于传进来的对象o，则往后排，即升序
    * 等于0，表示this等于传进来的对象o
    * 小于0，表示this小于传进来的对象o

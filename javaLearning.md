Java is quite similar to c++.

Here  I will record some characters that java possesses while c++ not.

- changeable parameters.  For example, String ... names means you can import String(s)

  ```java
  Group g = new Group();
  g.setNames("Xiao Ming", "Xiao Hong", "Xiao Jun"); // 传入3个String
  g.setNames("Xiao Ming", "Xiao Hong"); // 传入2个String
  g.setNames("Xiao Ming"); // 传入1个String
  g.setNames(); // 传入0个String,means empty string, not null
  ```

- 以及->尚未看到，即使是类定义中，也使用this.name

- 在构造函数中，可以在一个构造函数中调用另一个构造函数的内容，例如this(name)，对于父类则是this变super。有一个很有意思的是子类的构造函数必然会先调用父类的构造函数，没有写则是super()。那么在c++中是不是一样的情况呢，因为c++中也不会继承父类的构造函数（当然不会继承，毕竟你肯定用不到，名字是父类的），所以往往要重写狗杂函数，而且c++里一般用参数列表的方法解决，那么我觉得确实可以就如java一般理解，反正java和c++也太相似了。

- Instanceof判断是不是指向某个类（或者某个类的子类）的实例，父类指针指向子类实例，那么该指针可以认为指向父类或者子类实例（因为upcasting永远是安全的），但父类指向父类，则只能是父类。

- 对于重载则是相同的，函数如果只有返回值不同在c++和java中都是不能重载的，我想这个编译器的机制有关。

- java中的hashcode处理冲突的方法就是哈希链，相同的不断地往外拖。如果改动equals方法就会改动hashcode，要保证equal的前提下hashcode必定一致

- 用abstract修饰抽象类，更为简洁明了，我很喜欢

- 引入了implement interface 的方法，不得不时候令我眼前一亮

- 回忆静态字段属于类

- 还有一个包作用域 c++中如果不加修饰符说明就是private但是java中是表示包访问  可以被同一个包中的访问 public别的包也可以访问 

- 作用域是一个比较复杂的问题 

  - Public（类和接口）:可以被其他任何类访问，只需要import一下
  - private：method或者field（即函数或者变量）不能被其他类访问，嵌套类（nested class）自然可以访问private，说起来也是类内的。
  - protected：同c++
  - 包作用域：即没有public或者private修饰的类名（可见修饰类名只有这三种），或者没有public protected private修饰的字段或方法（即 field或者method）。是在同一个包内可以由别的类访问的。
  - 局部变量，比如方法参数就是变量。相比于c++我觉得java是更面向对象编程的语言。
  - final：非常奇怪而独特的部分；修饰class可以防止被继承；修饰method可以防止被子类覆写（override）；修饰field可以表示是常量。
  - 一个.java文件只能包含一个public类，别的可有多个；若有public类，文件名必须和public类名字相同。而把方法定义为package权限有助于测试。

- 非常有意思，我很喜欢这句话：最好的做法是不要设置classpath，默认当前目录一般够用，如果用IDE，会是当前工程的bin目录和引入的jar包

- module和JRE部分暂且用不到，没看

- java核心类：String 内部是char[] 有意思的是String有很多内部的方法 这样当然就比C++之类更加容易写了

  - toUpperCase or toLowerCase
  - equals  equalsIgnoreCase
  - contains ：是否包含某个子串
  - indexof某个字符第一次出现的index      lastIndexOf
  - startsWith endsWith return bool
  - substring: 提取子串 参数为开始下标或者开始下标以及结束下标
  - String.trim() 返回新的字符串，而且移除首尾空白字符（包括\t \r \n）更强的.strip()\u3000中文空格也会被去除
  - isEmpty :长度为0 isBlank：全是空白字符
  - String.replace(A,(with)B) A B 可以是字符也可以是字符串（或可以用正则表达式替换）
  - split：割开字符串
  - java中均按照unicode编码：unicode统一了主要语言 可以自行改为GBK（国标）或者UTF-8编码 UTF-8的话就是可变长度，对包含很多英文的可以节省存储空间 并且由于高位确定字符长度 可以 避免单个字符出错污染后续字符

- 和c++非常大的区别是 java中是不去刻意区分指针的 在new的时候体现很明显 
- 
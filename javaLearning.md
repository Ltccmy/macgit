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
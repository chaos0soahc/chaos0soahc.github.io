UML统一建模语言

在大部分的UML中，都是用类图的方式来表现相关关系

类图：主要出现在系统的分析和设计阶段，描述系统中包含的类以及他们之间的关系，也是系统编码和测试的重要模型依据

类：封装了数据和行为，是面向对象的重要组成部分，是具有相同属性，操作，关系的对象集合的总称（实体类，控制类，边界类）

类和类之间的关系

关联关系

在UML图中，使用**实线**连接有关联关系的对象所对应的类，在面向对象语言中，通常采用将一个类当做另外一个类的成员变量

```java
public class Tire{
	......
}
public class Car{
	private Tire tires;
}
```

<img src="D:\ProjectThings\chaos0soahc.github.io\png\关联关系图.png" alt="关联关系图" align='left' style="zoom:100%;" />

双向关联

默认情况下，关联是双向的采用**实线**。像代码中为列，一个老师要交很多个学生，每个学生都学习很多门老师的课

```java
public class Teacher{
	private Student[] students;
	......
}
public class Student{
	private Teacher[] teachers;
	......
}
```

<img src="D:\ProjectThings\chaos0soahc.github.io\png\双向关联关系图.png" alt="双向关联关系图" align='left' style="zoom:100%;" />

单向关联

关联关系也有可能是单向的，采用**箭头的实线**表示。

```java
public class Tire{
	......
}
public class Car{
	private Tire tires;
}
```

<img src="D:\ProjectThings\chaos0soahc.github.io\png\单向关联图.png" align='left' alt="单向关联图" style="zoom:100%;" />



自关联

```java
public class Node{
	private Node subNode;
	......
}
```

<img src="D:\ProjectThings\chaos0soahc.github.io\png\自关联图.png" align='left' alt="自关联图" style="zoom:100%;" />



多重关联

表示两个关联对象的数量上的对应关系,**主要表示另一个类与该类的关联关系**

| 表示方式 | 1..1 | 0..* | 1..* | 0..1 | m..n |
| :------: | ---- | ---- | ---- | ---- | ---- |
|          |      |      |      |      |      |



聚合关系

表示部分与整体的关系：成员对象是整体的一部分，当时成员对象可以脱离整体对象独立存在

```java
pulic class Car{
	private Engine engine;
	
	public Car(Engine engine){
		this.engine = engine;
	}
	
	public void setEngine(Engine engine){
		this.engine = engine;
	}
	......
}

public class Engine{
	......
}
```

<img src="D:\ProjectThings\chaos0soahc.github.io\png\聚合关系关联图.png" align='left' style="zoom:100%;" />

组合关系

表示整体和部分的关系，整体的对象可以控制成员对象生命周期，整体对象不存在了，成员对象也不存在

```java
public class Head{
	private Mouth mouth;
	public Head(){
		mouth = new Mouth;
	}
	......
}

public class Mouth{
	.....
}
```

<img src="D:\ProjectThings\chaos0soahc.github.io\png\组合关联关系图.png" align='left' style="zoom:80%;" />



依赖关系

是一种使用关系，表示一个事物使用另一个事物，大多数情况下主要体现在某个类的方法使用另一个类的对象作为参数（形式参数）;

主要通过三种方式来实现：

- 将一个类对象作为另一个类中的方法参数
- 在一个类的方法中将另一个类作为局部变量
- 在一个类的方法中使用另一个类的静态方法

```java
public class Driver{
	public void drive(Car car){
		car.move();
	}
}

public class Car{
	public void move();
}
```

![](D:\ProjectThings\chaos0soahc.github.io\png\依赖关系图.png)

泛化关系

也是继承关系，描述父类与子类之间的关系，父类作为基类或超类，子类成为派生类

```java
public class Person{
	protected String name;
	protected int age;
	
	public void say(){
		......
	}
	
	public void move(){
		......
	}
}

public class Teacher extends Person{
	private String teacherNo;
	
	public void teach(){
		......
	}
}
```

<img src="D:\ProjectThings\chaos0soahc.github.io\png\泛化关系.png" style="zoom:100%;" />

接口与实现关系

在接口中通常是没有属性的，所有的关系都是抽象的。接口之间也可以有类之间类似的依赖关系和泛化关系

```java
public interface Vehicle{
	public void move();
}

public Car implements Vehicle{
	public void move(){
		......
	}
}
```

![](D:\ProjectThings\chaos0soahc.github.io\png\接口与实现关系图.png)
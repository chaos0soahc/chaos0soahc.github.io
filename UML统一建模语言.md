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
### 对象是什么？

- 在计算机科学中，对象（英语：object），台湾译作物件，是一个存储器地址，其中拥有值，这个地址可能有标识符指向此处。对象可以是一个变量，一个数据结构，或是一个函数。是面向对象（Object Oriented）中的术语，既表示客观世界问题空间（Namespace）中的某个具体的事物，又表示软件系统解空间中的基本元素。

- 在软件系统中，对象具有唯一的标识符，对象包括属性（Properties）和方法（Methods），属性就是需要记忆的信息，方法就是对象能够提供的服务。在面向对象（Object Oriented）的软件中，对象（Object）是某一个类（Class）的实例（Instance）。

- 在ECMAScript 2019规范中，An object is a collection of properties and has a single prototype object. The prototype may be the null value.（一个对象是一组属性，还拥有单一的原型对象，而且原型对象可以为null）。

### 面向对象到底指的是什么？
**面向对象**可以指：
  - 面向对象的程序设计，一种设计程序的思想。
  - 面向对象的系统分析，一种对问题环境的模拟分析方法。
  
#### 面向对象程序设计
两种各有千秋的面向对象编程方式。

- 基于类编程（英语：class-based programming），又称基于类的编程、面向类（class-orientation），是面向对象编程（OOP）的一种风格，在程序设计时，强调对象（object）的类别（class）。

- 基于原型的编程（英语：prototype-based programming）或称为原型程序设计、原型编程，是面向对象编程的子系统和一种方式。在原型编程中，类不是实时的，而且行为重用（通常认为继承自基于类的语言）是通过复制已经存在的原型对象的过程实现的。这个模型一般被认为是 classless、面向原型、或者是基于实例的编程。

在基于类的编程当中，对象总共有两种类型。类（class）定义了对象的基本布局和函数特性，而接口（interface）是“可以使用的”对象，它基于特定类的样式。在此模型中，类表现为行为和结构的集合，就接口持有对象的数据而言，对所有接口来说是相同的。区分规则因而首先是基于结构和行为，而后是状态。

原型编程的主张者经常争论说基于类的语言提倡使用一个关注分类和类之间关系开发模型。与此相对，原型编程看起来提倡程序员关注一系列对象实例的行为，而之后才关心如何将这些对象划分到最近的使用方式相似的原型对象，而不是分成类。因为如此，很多基于原型的系统提倡运行时原型的修改，而只有极少数基于类的面向对象系统（比如第一个动态面向对象的系统 Smalltalk）允许类在程序运行时被修改。

### 面向对象编程的三大特性

#### 封装
- 从类型角度
> 类型处理是语义分析时的重要工作。现代计算机语言可以用自定义的类来声明变量，这是一个巨大的进步。早期的计算机语言只支持一些基础的数据类型，有非常大的局限性，所以需要扩展语言的类型机制，让程序员可以创建自己的类型。这是基于概念层面的封装。

- 从作用域角度
> 首先是类的可见性。作为一种类型，它通常在整个程序的范围内都是可见的，可以用它声明变量。当然，也能限制某些类型的使用范围。对象的属性可以在整个对象内部访问，无论在哪个位置声明。这是基于逻辑层面的封装。

- 从生存期的角度
> 对象的属性的生存期，一般跟对象的生存期是一样的。在创建对象的时候，就对所有属性做初始化，在销毁对象的时候，所有属性也随着一起销毁。当然，如果某个属性引用了从堆中申请的内存，这些内存需要手动释放，或者由垃圾收集机制释放。这是基于状态层面的封装。

继承和多态对类型系统提出的新概念，就是**子类型**。我们之前接触的类型往往是并列关系，你是整型，我是字符串型，都是平等的。而现在，一个类型可以是另一个类型的子类型。没有子类型，就没有继承和多态。

#### 继承
继承是指一个类的子类，自动具备了父类的属性和方法。

#### 多态
多态是指同一个类的不同子类，在调用同一个方法时会执行不同的动作。

### 面向对象的到底是语言还是程序？

#### 基于类的程序
```js
class Person {
  constructor(name) {
    this.name = name;
  }
  sayHello() {
    console.log("Hi, I am " + this.name);
  }
}
var p = new Person('moling');
console.log(p.name); // "moling"
p.sayHello(); // "Hi, I am moling"
```

#### 基于原型的程序
```js
function Person(name) {
  this.name = name
}
Person.prototype.sayHello = function() {
  console.log("Hi, I am " + this.name);
}
var p = new Person('moling');
console.log(p.name); // "moling"
p.sayHello(); // "Hi, I am moling"
```

### 为什么只有JavaScipt会在面向对象和基于对象之间有争议？
准确来说，并没有什么基于对象，面向对象有两种编程范式，基于类或者是基于原型，JavaScript恰好是两种模式都可以写，又或者说，JavaScript用原型模拟了类。由于JavaScript极致的灵活性，所以才难有定论。

### 小结
结论是，ECMAScript说它是一个OOP的语言，基于类OR基于原型，或者哪种编程范式更优，没有定论。

> ECMAScript is an object-oriented programming language for performing computations and manipulating computational
objects within a host environment. 

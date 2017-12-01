## Design Patterns: Elements of Reusable Object-Oriented Software<br>
该本书是介绍设计模式的书籍，在OOP，设计模式是个重要且核心的内容。记得在知乎上有个网友说"设计模式是终点，而不是起点"觉得颇有意思。<br>
设计模式确实是前辈多次实践和经验总结形成“经验”，故在闲暇之时，记录一下自己读书笔记。供自己复习和总结。<br>

该本书包含了一些供学习的设计案例，案例中包含了一些设计模式使用的过程。并将设计模式总结成三种大类型：**创建型，结构型，行为型**。<br>
每种类型用于不同的场景，也不必要强制使用，在合适场景使用合适的模式是理想目标。书籍中分别介绍不同设计模式，以及设计模式如何组合操作。<br>

通过设计模式也可以更好的理解OOP，这个面向对象是个很大的领域，思想这二字，亦是抽象。某个概念，某种技术，在脑子中抽丝剥茧的不断理解过程中，<br>会结合自己的学识，经历经验，思维模式来不断重构。什么是设计模式？有那些设计模式？如何运用设计模式解决实际软件设计问题?设计模式有什么特性，有什么弊端，在其他非OOP领域中模式是否有用？<br>

设计模式主要目的就是解决软件系统代码的可重用性，灵活性问题的。在软件工程中，从概要设计，详细设计，编码实现，测试等等一系列过程中，**设计**二字是重中之重，初期软件架构设计亦是项目后期`存活`影响最大的地方。架构设计先不说，自己的能力也相差甚远。但是`代码级别`设计，就是我们程序员可以控制的。<br>

在软件开发过程中，使用的技术框架本身底层就包含许多设计模式的思想和实践(ps:都是针对OOP编程)，`框架级别`代码设计我们可以参考，学习。动手实践部分还是`编码实现`这一过程。面对多变的需求，系统是否能符合`开闭原则`,在对本身软件系统风险控制最低情况下，对软件系统进行拓展，重构。<br>
使用设计模式不外乎有两种主要情况：<br>
	* 在编码熟悉代码框架，业务后，预料到后期可能的改动而使用设计模式。
	* 依据前辈经验，使用设计模式对后期拓展改动会有作用，可拓展，灵活性高目的来使用设计模式。
当然，设计模式是对问题类型的总结抽象出来的，也不是一定能解决全部问题。学习设计模式目的是什么呢？改怎么学设计模式？学习设计模式有什么必要前提基础呢？<br>

我认为设计模式是属于`实践应用型`。在了解它是什么?包含那些内容?还需要有实际编程的代码量。在依靠书籍学习过程中，还要多思考，多看看优秀框架如何应用设计模式，或者拿jdk来说，底层的源代码设计中也有模式的应用，具体是如何实现的？再在实际项目中，在自己有能力设计项目基础代码条件下来实际应用，不过，说实话，多数在刚工作几年的我们，都是没有这个机会的。最多就是`编程规范，代码重构`这个范畴。若是以后要深入OOP编程和设计，那设计模式当然要学习的。<br>

设计模式是设计人员依据自身之前的经验重新设计软件系统的原则，思想。因为无论各行各业，都是**有某某经验者优先**。因为之前遇到问题，有对应的解决方法了，无论方法是不是最好。这就成了经验，也避免因为踩坑而花费的时间。在多行业的很多使用OOP开发的软件，设计师或者架构师自身也会在不断多场景使用多种设计模式中汲取经验，拿捏平衡。久而久之，也就知道，某种软件系统后面会如何拓展，在该软件设计初期改使用什么模式进行设计?<br>

总之，深入OOP设计和编码学习，设计模式都是不可绕过的高山。因为要提升，所以学习设计模式。对以后软件开发，设计都会有用处。<br>

### 什么是设计模式<br>
该书中原文:<br>
>Each pattern describes a problem which occurs over 
and over again in our environment, and then describes the core of the solution 
to that problem, in such a way that you can use this solution a million times 
over, without ever doing it the same way twice.

简而言之，就是把之前出现的多种重复问题解决方法抽取出来的一种**形式**。目的为了防止再次遇到同样的问题而再次使用同样的解决方法，直接`防微杜渐，未雨绸缪`。例如在应用场景A1中遇到问题P1，最后可以用Z1方法解决;场景A2中遇到问题P2,最后用方法Z2解决，多次反复，可以对场景A软件开发，提取z1,z2....抽象出的思想进行定义，得到设计模式Z。那么，我们在设计时候，就能参考和使用该种模式Z了，可以避免很多类似场景会出现的问题。<br>

* 一种设计模式需要的必要元素：<br>
	* **模式名字**：
设计模式的名字还是挺重要的，因为从该名字就能高度抽象出该种模式应用的领域和场景。更可以在行业内快速交流，传播。
	* **问题描述**
描述什么情况下可以使用该种设计模式来解决，同时也会说明问题一些共性特征。让设计者在遇到这种有这种特性问题的时候，能知道该种设计模式适合解决。
	* **解决方法**
描述了模式组成部分。组建之间的关系，职责，以及如何协作。但是不会做出更详细的描述，不会具体到XXX类。从抽象描述成模版，具有那些组件，这些组建的职责作用，组建之间的依赖协作关系。(在我们实际设计也按照职责模版进行细化)
	* **应用结果**
使用设计模式后对系统时间空间的影响，更多包括：系统的灵活性，拓展性，可移植性等等，使用设计模式了可以明显对这些特征进行评估和理解。
* 设计模式元素
因为是OOP领域的，离不开类和对象。总结包括： 场景  形式  关系依赖  顺序  对象  类(接口) <br>

该本书的设计模式表示的是：<br>
**如何解决特定环境下的设计问题，以及在这过程中类和对象之间是如何联系和协作的。**

### 设计模式如何表示？
封装，类的属性字段和操作属性的代码方法都被封装到类中。不能直接访问`类实例化对象的内部`数据，对于外部对象来说，其内部数据是不可见的。<br>
就像我们使用三方或者框架代码，若是获取某个对象的属性,都是只能通过暴露的方法代码来操作的或者对对象内部数据进行设置的。<br>

面向对象系统设计难点在于将系统分解成对象，如何适当的分解是个难点，要考虑到很多问题：`如何封装？细分到什么程度？如何依赖？灵活性，性能，可重用性等等....`。 一些优秀框架如**spring**,其内部设计是由很多优秀程序员协作设计开发的。就那一个spring对bean的前置后置处理来说，灵活性和拓展性都设计得不错，能让我们使用这自定义需求，来对spring容器获取bean时刻进行拓展。其内部框架代码设计就很不错，可以研究源代码来看看如何应用设计模式的。<br>

**抽象**特性增强将面向对象模式设计的灵活性的关键。<br>

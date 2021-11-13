> 类图关系  

    在UML类图中，常见的有以下四种关系: 
                           泛化（Generalization）  
                           实现（Realization）  
                           关联（Association)  
                                - 聚合（Aggregation）  
                                - 组合(Composition)  
                           依赖(Dependency)

**1. 泛化（Generalization）**

    【泛化关系】：是一种继承关系, 表示一般与特殊的关系, 它指定了子类如何特化父类的所有特征和行为。  
    例如：老虎是动物的一种, 即有老虎的特性也有动物的共性  

    【箭头指向】：带三角箭头的实线，箭头指向父类  

![image](https://user-images.githubusercontent.com/42632290/141610009-f6d8beff-b003-4160-91c9-1ee21d4ac0a1.png)  

**2. 实现（Realization）**

【实现关系】：是一种类与接口的关系, 表示类是接口所有特征和行为的实现  

【箭头指向】：带三角箭头的虚线，箭头指向接口

![image](https://user-images.githubusercontent.com/42632290/141610030-bfb65c77-ebe3-4e81-bd08-703e1f2f50d4.png)  

**3. 关联（Association)**

【关联关系】：是一种拥有的关系,它使一个类知道另一个类的属性和方法；如：老师与学生，丈夫与妻子  

  - 关联方向：

    关联的两个类互相之间都会去向对方发送消息的情况下，称为双向关联。关联端两端都要用箭头明示。

![image](https://user-images.githubusercontent.com/42632290/141610152-73b22714-b0b2-4671-8608-ff4a5c2a1fbd.png)  

    关联的两个类之间，只能由一端向另外一端的类发消息，而反过来不行时，称为单向关联。接受消息一方的关联端用箭头表示，不能接受消息一方的关联端用“X”进行表示。

![image](https://user-images.githubusercontent.com/42632290/141610175-058f53d1-6660-4ffe-b781-1e9c0986a441.png)  

    关联的某一端的关联方向尚未明确的情况下，可不标明方向性。

![image](https://user-images.githubusercontent.com/42632290/141610183-29038876-2220-4115-919d-86ea65d2a581.png)  


  【代码体现】：拥有者含有一个成员变量，指向被拥有者。

  【箭头及指向】：带普通箭头的实心线，指向被拥有者

![image](https://user-images.githubusercontent.com/42632290/141610207-669f8675-b2de-4649-9d25-e34218abf890.png)  

  上图中，老师与学生是双向关联，老师有多名学生，学生也可能有多名老师。但学生与某课程间的关系为单向关联，一名学生可能要上多门课程，课程是个抽象的东西他不拥有学生  

**4. 依赖(Dependency)**

  【依赖关系】：是一种使用的关系, 即一个类的实现需要另一个类的协助, 所以要尽量不使用双向的互相依赖.  

  【关系分类】：

    - 一个类的对象作为另外一个类的参数被调用。  

![image](https://user-images.githubusercontent.com/42632290/141610257-d89d40b8-2fec-43c9-a9c8-37ee89c468df.png)  

    - 一个类的对象作为局部变量被调用。  

![image](https://user-images.githubusercontent.com/42632290/141610276-34845eb7-7336-4835-8f35-6c34e98298a6.png)  

    - 一个类的对象作为全局变量被调用  

![image](https://user-images.githubusercontent.com/42632290/141610283-dd0cad9f-d15f-41d0-a768-fb7623580ff0.png)  

  【代码表现】：作为全局/局部变量、方法的参数或作为返回值  
```cpp
class ZhangSan
{
 public:
     //依赖关系  
     void GoWork(Car * p)
     {}
     //依赖关系
     car * fix()
     {}
}

calss Car
{
 public:
 private:
}
```

  【箭头及指向】：带箭头的虚线，指向被使用者

![image](https://user-images.githubusercontent.com/42632290/141610307-a5ff9f8b-b7ba-4e51-bf1e-db11c9a741e3.png)  

**5. 聚合（Aggregation）**

  【聚合关系】：是整体与部分的关系, 且部分可以离开整体而单独存在.如车和轮胎是整体和部分的关系, 轮胎离开车仍然可以存在.聚合关系是关联关系的一种，是强的关联关系；关联和聚合在语法上无法区分，必须考察具体的逻辑关系。  

  【代码体现】：成员变量  

  【箭头及指向】：带空心菱形的实心线，菱形指向整体  

![image](https://user-images.githubusercontent.com/42632290/141610338-33d32ddc-0e10-42b6-b771-3aefacfcba2e.png)  

**6. 组合(Composition)**

  【组合关系】：是整体与部分的关系, 但部分不能离开整体而单独存在. 如公司和部门是整体和部分的关系, 没有公司就不存在部门.组合关系是关联关系的一种，是比聚合关系还要强的关系，它要求普通的聚合关系中代表整体的对象负责代表部分的对象的生命周期  

  【代码体现】：成员变量  

  【箭头及指向】：带实心菱形的实线，菱形指向整体

![image](https://user-images.githubusercontent.com/42632290/141610385-a2a3652f-0978-4235-9aa6-cb76b9efe6f7.png)  


> 类图  

  **组成要素**
  
    类（类名，属性，操作）、关系（泛化，实现，关联，依赖等）

  **类的表示法**  

    类用矩形表示，顶部放类的名称；中间放类的属性，属性类型及值；底部存放类的方法，方法参数和返回类型  
    
    公有类型（public）：允许在类的外面使用或查看该属性(+)

    受保护类型（protected）：允许子类访问父类中受保护类型的属性(#) 

    私有类型（private）：只有类本身能够访问，外部一概不能(-)

![image](https://user-images.githubusercontent.com/42632290/141610789-e0f66288-a455-4ea5-b71b-4789692b1170.png)  

  示例：  

![image](https://user-images.githubusercontent.com/42632290/141610846-0b5adcd8-6a22-41dd-a02b-7b25a1012b02.png)  




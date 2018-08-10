**call 和 apply：**`call()和apply()` 方法在使用一个指定的 this 值和若干个指定的参数值的前提下调用某个函数或方法。根本上是改变了this的指向。<br>
**区别 :** 传参列表不同，call之后将实参依照形参顺序依次传入，apply之后将实参以数组的形式传入。<br>
**这是Call的用法**
```javaScript
 var son = new Son();
        function Person(name,age,sex){
            this.name = name;
            this.age = age;
            this.sex = sex;
        }
        var person1 = new Person("bao",100,"male");
        var person2 ={
        }
        Person.call(person2,"bao",100,"male");
        //两个式子功能等价，person1.__proto__.__proto__===person2.__proto__
```
**call也可以用来简化代码**

```javascript
  function Person(name,age,sex){
            this.name = name;
            this.age = age;
            this.sex = sex;
        }
  function Student(name,age,sex,tel,grade){
            // this.name = name;
            // this.age = age;
            // this.sex = sex;
            Person.call(this, name, age, sex);
            //与前三行的功能相同
            this.tel = tel;
            this.grade = grade; 
        }
        var student1 ={

        }
         Student.call(student1,"bao", 100 , "male" , 15829691128 , 17);
         var student2 = new Student("bao", 100 , "male" , 15829691128 , 17);
```
**apply的用法**

```javacript
		function foo(){bar.apply(null,arguments)}
        function bar(x){console.log(arguments)}
        foo(1,2,3,4,5)//1,2,3,4,5
```

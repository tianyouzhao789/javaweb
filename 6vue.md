---

title: 6 vue

author: glls

date: '2023-3-29'

---



# 前端开发

## 1.前端开发

前端工程师“Front-End-Developer”源自于美国。大约从2005年开始正式的前端工程师角色被行业所认可，到了2010年，互联网开始全面进入移动时代，前端开发的工作越来越重要。

最初所有的开发工作都是由后端工程师完成的，随着业务越来越繁杂，工作量变大，于是我们将项目中的可视化部分和一部分交互功能的开发工作剥离出来，形成了前端开发。

![image-20210516145804375](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20210516145804375.png)



## 2.环境准备：
nodejs安装   



vscode 安装  



vscode 常用插件安装

Chinese  ，   Live Server ， Vetur    ,  Vue-helper ,  Auto close tag  ,Auto Rename Tag  ,HTML CSS Support ,JavaScript(ES6)  .....



## 3.创建项目

vscode本身没有新建项目的选项，所以要先创建一个空的文件夹，如project_xxxx。

然后打开vscode，再在vscode里面选择 File -> Open Folder 打开文件夹，这样才可以创建项目。

## 4.保存工作区

打开文件夹后，选择     “文件 -> 将工作区另存为...”，为工作区文件起一个名字，存储在刚才的文件夹下即可

![image-20210516153834546](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20210516153834546.png)



然后  可以在工作区下 创建前端工程的文件

# ES6 基本语法

## 1、ECMAScript 6

### 1.1什么是 ECMAScript 6

ECMAScript 6.0（简称 ES6）是 JavaScript 语言的下一代标准， 2015 年 6 月正式发布。它的目标，是使得 JavaScript 语言可以用来编写复杂的大型应用程序，成为企业级开发语言。

### 1.2 ECMAScript 和 JavaScript 的关系

一个常见的问题是，ECMAScript 和 JavaScript 到底是什么关系？

要讲清楚这个问题，需要回顾历史。1996 年 11 月，JavaScript 的创造者 Netscape 公司，决定将 JavaScript 提交给标准化组织 ECMA，希望这种语言能够成为国际标准。次年，ECMA 发布 262 号标准文件（ECMA-262）的第一版，规定了浏览器脚本语言的标准，并将这种语言称为 ECMAScript，这个版本就是 1.0 版。

因此，ECMAScript 和 JavaScript 的关系是，前者是后者的规格，后者是前者的一种实现（另外的 ECMAScript 方言还有 Jscript 和 ActionScript）

## 2 基本语法

ES6相对之前的版本语法更严格，新增了面向对象的很多特性以及一些高级特性。本部分只学习项目开发中涉及到ES6的最少必要知识，方便项目开发中对代码的理解。

### 2.1 let声明变量

~~~javascript
// var 声明的变量没有局部作用域
// let 声明的变量  有局部作用域
{
 var a = 1;
let b = 2;
}
console.log(a)
console.log(b)  //b is not defined

~~~

~~~javascript
// var 可以声明多次
// let 只能声明一次
var m = 1;
var m = 2;
let n = 10;
let n = 20;  //'n' has already been declared
console.log(m)
console.log(n)

~~~

### 2.2 const声明常量（只读变量）

~~~javascript
// 1、声明之后不允许改变    
const PI = "3.1415926"
PI = 3     // TypeError: Assignment to constant variable.
// 2、一但声明必须初始化，否则会报错
const MY_AGE  // Missing initializer in const declaration

~~~

### 2.3 解构赋值

创建 03-解构赋值-数组解构.js

解构赋值是对赋值运算符的扩展。

他是一种针对数组或者对象进行模式匹配，然后对其中的变量进行赋值。

在代码书写上简洁且易读，语义更加清晰明了；也方便了复杂对象中数据字段获取。

~~~javascript
//1、数组解构
let a = 1, b = 2, c = 3
//console.log(a, b, c)
// ES6
let [x, y, z] = [1, 2, 3]
//console.log(x, y, z)

~~~

~~~javascript
//2、对象解构
let user = {name: 'Helen', age: 18}
// 传统
let name1 = user.name
let age1 = user.age
console.log(name1, age1)
// ES6
let { name, age } =  user  //注意：结构的变量必须是user中的属性
console.log(name, age)

~~~

### 2.4 模板字符串

模板字符串相当于加强版的字符串，用反引号 `，除了作为普通字符串，还可以用来定义多行字符串，还可以在字符串中加入变量和表达式。

~~~javascript
 <script>
            // 1、模板字符串的语法

            // 没用模板字符串之前   想要在字符串中加入变量可以这样写：
            let name ="zs";

            let age = 18;

            let str = "My name is "+name+
                    ",I am "+age+" years old";

            console.log(str);

            // 使用模板字符串之后   想要在字符串中加入变量可以这样写：

            let str1 = `My name is ${name}
            ,I am ${age}`;

            console.log(str1);

            // 模板字符串中 使用函数
            function getName(){
                return "张三";
            }



            let str2 = `My name is ${getName()}`

            console.log(str2);


        </script>

~~~

### 2.5声明对象简写

~~~javascript
//传统方式定义对象
const name = "lucy"
const age = 20
const user1 = {name:name,age:age}
//console.log(user1)
//es6
const user2 = {name,age}
console.log(user2)


~~~

### 2.6对象拓展运算符

拓展运算符（...）用于取出参数对象所有可遍历属性然后拷贝到当前对象。

~~~javascript
//对象复制
let person1 = {name: "Amy", age: 15}
let someone1 = { ...person1}
//console.log(someone1)

//对象合并
let age = {age: 15}
let name = {name: "Amy"}
let person2 = {...age, ...name}
console.log(person2)

~~~

### 2.7箭头函数

箭头函数提供了一种更加简洁的函数书写方式。基本语法是：

参数 => 函数体

箭头函数多用于匿名函数的定义

~~~javascript
//传统方式定义函数
var f1 = function(a) {
    return a
}
//console.log(f1(3))

//es6使用箭头函数定义
//参数 => 函数体
var f2 = a => a
//console.log(f2(4))

~~~

使用箭头函数

~~~javascript
// 当箭头函数没有参数或者有多个参数，要用 () 括起来。
// 当箭头函数函数体有多行语句，用 {} 包裹起来，表示代码块，
// 当只有一行语句，并且需要返回结果时，可以省略 {} , 结果会自动返回。
var f3 = function(m,n) {
    return m+n
}

//es6 
var f4 = (m,n) => m+n
console.log(f4(4,5))

~~~



### 2.8  函数的优化

~~~js
    <script>
        //不定参数
        function fun(name,...hobby){
            console.log(`${name}的兴趣爱好是${hobby}`);
        }

        fun("张三","打球","跳舞","唱歌");

        //给函数的参数设置默认值
        //之前的写法
        function add1(a,b){
            // 判断b是否有值
            b = b || 1;   // 如果b没有值，那么就设置b的值为1
            return a+b;
        }


        //es6的写法

        function add2(a,b = 1){
            return a+b;
        }


        console.log(add2(1,10));
    </script>

~~~

### 2.9 数组中新增的方法

map 和  reduce

~~~js
<p>
        数组中新增的map和reduce方法
    </p>

    <script>
        //map方法   接受一个函数参数  ，对数组中的所有元素 使用这个函数加工处理，然后返回一个新的数组
    
        let arr = [1,2,3,4,5,6,7,8,9,10];

        let newarr = arr.map((x)=>{return x*2});
        
        console.log(newarr);
        

        // reduce 方法   语法：
        // arr.reduce(callback,[initialValue])
        // reduce 为数组中的每一个元素 依次执行回调函数，不包括数组中未被赋值的元素
        // callback 回调函数 有四个参数：
        // 1. previousValue  上一次执行回调函数的返回值 或者 提供的初始值
        // 2. currentValue  数组中当前被处理的元素
        // 3. currentIndex  当前元素在数组中的索引
        // 4. array  当前处理的数组   也就是调用 reduce 的数组

        // initialValue  初始值  (作为 第一次调用callback 的第一个参数)

        let arr2 = [1,2,3,4,5,6,7,8,9,10];

        let result = arr2.reduce((a,b)=>a+b,10);

        let result2 = arr2.reduce((a,b)=>a*b,0);
        console.log(result2);
    </script>
~~~

### 2.10 promise

~~~js
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="/js/jquery-3.4.1.min.js"></script>
</head>

<body>

    <script>
        //1.查询用户的信息
        //2.根据用户的id查询他得课程
        //3.根据课程id查询他得分数

        // $.ajax({
        //     url:"/mock/user.json",
        //     success:function(res){
        //         console.log("用户信息"+res);
        //         //根据用户信息查询课程信息
        //         $.ajax({
        //             url:`/mock/course_${res.id}.json`,
        //             success:function(res){
        //                 console.log("课程信息"+res);
        //                 //根据课程信息查询分数

        //                 $.ajax({
        //                     url:`/mock/score_${res.id}.json`,

        //                     success:function(res){
        //                         console.log("分数信息"+res.score);
        //                     },
        //                     error(error){
        //                         console.log("查询分数信息"+error);
        //                     }
        //                 })     

        //             },

        //             error(error){
        //                 console.log("查询课程信息"+error);
        //             }
        //         })


        //     },

        //     error(error){
        //         console.log("查询用户错误"+error);
        //     }
        // })    


        //上面的写法 很繁琐  ，下面的写法更简洁 
        // 借助 Promise 实现   Promise 可以封装异步操作

        // let p = new Promise((resolve, reject) => {
        //     $.ajax({
        //         url: "/mock/user.json",
        //         success: function (res) {
        //             console.log("用户信息" + res);
        //             resolve(res);  // 表式 把结果向下传递
        //         },
        //         error(error) {
        //             reject(error);
        //         }
        //     })
        // });

        // 下面这个 res 是上面查询的 用户信息
        // p.then(res => {
        //     return new Promise((resolve, reject) => {
        //         $.ajax({
        //             url: `/mock/course_${res.id}.json`,
        //             success: function (res) {
        //                 console.log("课程信息" + res);
        //                 resolve(res);  // 表式把结果向下传递
        //             }
        //         })
        //             .then(res => {
        //                 console.log("上一步查询的课程信息" + res);
        //                 $.ajax({
        //                     url: `/mock/score_${res.id}.json`,
        //                     success: function (res) {
        //                         console.log("查询到的成绩" + res.score)
        //                     }
        //                 })

        //             })
        //     })
        // }
        // )


        // 实际开发中的写法：  会把promise 封装成 通用的方法

        function getMsg(url,data){
            return new Promise((resolve,reject)=>{
                $.ajax({
                    url,
                    data,
                    success(res){
                        resolve(res);
                    },
                    error(error){
                        reject(error);
                    }
                })
            })
        }    



        getMsg("/mock/user.json")
        .then(res=>{
            console.log("用户信息"+res);
            //根据用户的id查询课程
            return getMsg(`/mock/course_${res.id}.json`);
        }
        )
        .then(res=>{
            console.log("课程信息"+res);
            //根据课程id查询分数
            return getMsg(`/mock/score_${res.id}.json`);
        }
        )
        .then(res=>{
            console.log("分数信息"+res.score);
        }
        )
    </script>


</body>

</html>
~~~

# Vue基础

## 1.vue.js 介绍

Vue (读音 /vjuː/，类似于 **view**) 是一套用于构建用户界面的**渐进式框架**。与其它大型框架不同的是，Vue 被设计为可以自底向上逐层应用。Vue 的核心库只关注视图层，不仅易于上手，还便于与第三方库或既有项目整合。另一方面，当与[现代化的工具链](https://vuejs.bootcss.com/guide/single-file-components.html)以及各种[支持类库](https://github.com/vuejs/awesome-vue#libraries--plugins)结合使用时，Vue 也完全能够为复杂的单页应用提供驱动。

## 2.环境准备

>使用idea 创建web 工程      安装vue.js 插件  ，   创建html 页面 引入 vue.js   查看有没有提示

~~~html
<script src="https://cdn.jsdelivr.net/npm/vue@2.6.12/dist/vue.js"></script>
~~~

## 3.基本语法
### 3.1 helloworld实现

~~~html
  <div id="app">    //  mvvm 中的 第一个 v
        {{message}}
        <input type="text" v-model="message" >

    </div>
~~~

~~~js
   var app = new Vue({    // 创建 vue 实例    即  mvvm 中的   vm
        el: '#app',    //  接管 app 这个 dom
        data: {         //  mvvm 中的   第一个  m
            message: 'Hello Vue!'
        }
    })
~~~

>说明：
>
>这里有几点重要说明：
>
>new Vue 我们创建了Vue对象；
>
>el 指定了绑定DOM，接管DOM操作；
>
>data：初始化数据，页面可以直接访问；
>
>v-model 重点 可以实现数据双向绑定，改变了这里的值，其他地方也根据改变；
>
>{{xxxxx}} 显示数据；

核心原理：mvvm

![image-20201231154558720](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20201231154558720.png)

>这里 核心就是 ViewModel 里面有DOM监听以及数据绑定，View是页面数据展示 Model也就是前面data里定义的，通过Vue来实现各种快捷功能，我们用普通js写的话 得写一大串Js代码；
>
>mvvm设计模式 这里的 
>
>第一m是 model 也就是vm的data属性  
>
>第二个v是 view 视图 网页模版
>
>最后vm就是中间vue的 viewmodel 代码体现就是vm对象或者vm实例；

### 3.2 常用指令


~~~html
<html>
<head>
    <meta charset="UTF-8">
    <meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
    <title>Title</title>
    <script src="https://cdn.jsdelivr.net/npm/vue@2.6.12/dist/vue.js"></script>
</head>
<body>

<div id="app">
    <h2>插值</h2>
    <input type="text" v-model="msg">
    <span v-once>Message: {{ msg }}</span>

    <p>{{message}}</p>
    <p><span v-html="message"></span></p>

    <h2>数据绑定-- 双大括号语法不能作用在 html 的属性上面  遇到这种情况应该使用 v-bind 指令</h2>

    <div class="c">div1</div>
    <div v-bind:class="c">div2</div> <%--v-bind 把 vue 实例的 c 属性值 赋值给 这个div 标签的class 属性--%>


    <div v-bind:id="dynamicId">1</div>
    <div :class="c">1</div>   <%--简写  v-bind:  --%>


    <button :disabled="isDisabled">Button</button>
    <a v-bind:href="url">百度</a>
    <a :href="url">百度2</a>


    <h2>js表达式</h2>
    <p>{{number+1}}</p>
    <p>{{ ok ? 'YES' : 'NO' }}</p>
    <p>{{ message2.split(' ').reverse().join(',') }}</p>

    <p v-if="see">看得到吗？</p>
    <h2>事件绑定</h2>

    <button v-on:click="doSomething">按钮</button>
    <button @click="doSomething">按钮2</button>


    <h2>总结</h2>
    <pre>
        指令： 指令 (Directives) 是带有 v- 前缀的特殊 attribute。
        指令 attribute 的值预期是单个 JavaScript 表达式 (v-for 是例外情况，稍后我们再讨论)。
        指令的职责是，当表达式的值改变时，将其产生的连带影响，响应式地作用于 DOM。
        指令：
        v-model="vuedata"     数据双向绑定
        v-bind:htmlattr="vuedata"    属性动态赋值
        v-bind的简写       :htmlattr="vuedata"
        v-on:htmlevent="vuemethods"    事件动态绑定
        v-on的简写       @htmlevent = "vuemethods"
        v-html : 可以解析 html 标签
        v-once : 一次性的插值
        v-if="vuedata"  v-if 指令将根据表达式 vuedata 的值的真假来插入/移除 x 元素。
    </pre>
</div>

<script type="text/javascript">
    var app = new Vue({
        el: '#app',    //  接管 app 这个 dom
        data: {
            msg: 'Hello Vue!',
            message:'<font color="red">hello</font>',
            c:'c',
            dynamicId:'5',
            isDisabled:false,
            url:"https://www.baidu.com",
            number:2,
            ok:true,
            message2:"ni hao ma",
            see:false

        },
        methods:{
            doSomething(){
                alert("点我干嘛");
            }
        }
    })
    //app.ok = false;
</script>

<style type="text/css">
    .c{
        border: 1px solid black;
    }
    .c2{
        border: 1px solid red;
    }
</style>
</body>
</html>

~~~

~~~html
<html>
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <script src="https://cdn.jsdelivr.net/npm/vue@2.6.12/dist/vue.js"></script>
</head>
<body>
    <div id="app">
        <a  v-bind:[attributename]="msg"> 超链接 </a>
        <a href="#" v-on:[eventName]="doSomething"> 超链接2 </a>
    </div>
<script type="text/javascript">
    new Vue({
        el:'#app',
        data:{
            attributename:'href',
            msg:'1mubanyufa.html',
            eventname:'click'

        },
        methods:{
            doSomething(){
                alert("点我干嘛")
            }
        }
    })
</script>
</body>
</html>

~~~

### 3.3 条件渲染v-if


~~~javascript
<html>
<head>
    <meta charset="UTF-8">
    <title>Title</title>
   <!-- <script src="https://cdn.jsdelivr.net/npm/vue@2.6.12/dist/vue.js"></script>-->
    <script src="js/vue.js" type="text/javascript"></script>
</head>
<body>
    <div id="app">
        <h2>v-if</h2>
        <h1 v-if="awesome">Vue is awesome!</h1>
        <h1 v-else>Oh no </h1>
        <h2>v-if in template</h2>
        <template v-if="ok">
            <h1>Title</h1>
            <p>Paragraph 1</p>
            <p>Paragraph 2</p>
        </template>

        <h2>v-else</h2>
        <div v-if="Math.random() > 0.5">
            Now you see me
        </div>
        <div v-else>
            Now you don't
        </div>

        <h2>v-else-if</h2>
        <div v-if="type === 'A'">
            A
        </div>
        <div v-else-if="type === 'B'">
            B
        </div>
        <div v-else-if="type === 'C'">
            C
        </div>
        <div v-else>
            Not A/B/C
        </div>

        <H2>用 key 管理可复用的元素</H2>
        <template v-if="loginType === 'username'">
            <label>Username</label>
            <input placeholder="Enter your username" key="username-input">
        </template>
        <template v-else>
            <label>Email</label>
            <input placeholder="Enter your email address" key="email-input">
        </template>

        <BUTTON @click="toggle">toggle</BUTTON>

        <h2>v-show</h2>
        <h1 v-show="ok">Hello! v-show</h1>

        <h2>不推荐同时使用 v-if 和 v-for。请查阅风格指南以获取更多信息。</h2>
    </div>
    <h2>总结</h2>
    <pre>
       v-if 用于条件性的渲染一块内容
       在template 上使用 v-if  条件渲染分组   最终的渲染结果是不包含template
        v-else   表示   v-if 的else 块
        v-else-f     表示    v-if 的 else -if   可以连续使用  多分枝
        用key 管理 服用的元素
        v-show 只是简单的切换元素的  display
    </pre>
<script type="text/javascript">
    new Vue({
        el:"#app",
        data:{
            awesome:false,
            ok:false,
            type:'B',
            loginType:'username'
        },
        methods:{
            toggle(){
                this.loginType= this.loginType=='username'?'email':'username'
            }
        }
    });
</script>
</body>
</html>

~~~

### 
### 3.4 列表渲染v-for



~~~html
<html>
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <script src="https://cdn.jsdelivr.net/npm/vue@2.6.12/dist/vue.js"></script>
</head>
<body>
    <div id="app">
        <h2>用 v-for 把一个数组对应为一组元素</h2>
        <p>我们可以用 v-for 指令基于一个数组来渲染一个列表。v-for 指令需要使用 item in items 形式的特殊语法，
            其中 items 是源数据数组，而 item 则是被迭代的数组元素的别名</p>

        <ul>
            <!--<li>星期一</li>
            <li>星期二</li>
            <li>星期三</li>-->
            <li v-for="item in items">{{item.date}}</li>
        </ul>

        <h2> 在 v-for 块中，我们可以访问所有父作用域的属性。v-for 还支持一个可选的第二个参数，即当前项的索引。 可以不看</h2>
        <ul>
            <li v-for="(item,index) in items" v-bind:key="index" v-bind:title="item.id">
                {{parentMessage}}--{{item.date}}--{{index}}
            </li>
        </ul>
        <ul>
            <li v-for="(item,index) in myitems2.items2" v-bind:key="item.id" >
                {{parentMessage}}--{{item.date}}--{{index}}
            </li>
        </ul>

        <h2>在 v-for 里使用对象</h2>
        <ul>
            <li v-for="(value,name,index) in student">
               {{name}}--{{value}}--{{index}}
            </li>
        </ul>

        <pre>
            注意
            为了给 Vue 一个提示，以便它能跟踪每个节点的身份，从而重用和重新排序现有元素，你需要为每项提供一个唯一 key 属性：
            &lt;div v-for="item in items" v-bind:key="item.id"&gt;
            <!-- 内容 -->
            &lt;/div&gt;
            建议尽可能在使用 v-for 时提供 key attribute，除非遍历输出的 DOM 内容非常简单，或者是刻意依赖默认行为以获取性能上的提升。
            不要使用对象或数组之类的非基本类型值作为 v-for 的 key。请用字符串或数值类型的值。
        </pre>

        <hr>
        <table style="border: 1px solid black">
            <tr>
                <th>姓名</th>
                <th>年龄</th>
                <th>联系方式</th>
            </tr>
            <tr v-for="(stu,index) in students" v-bind:key="index">
                <td>{{stu.name}}</td>
                <td>{{stu.age}}</td>
                <td>{{stu.phone}}</td>
            </tr>
        </table>


    </div>
<script type="text/javascript">
    var vue = new Vue({
        el:"#app",
        data:{
            parentMessage: 'Parent',

            items:[
                {
                    date:"星期1",
                    id:1
                },
                {
                    date:"星期2",
                    id:2
                },
                {
                    date:"星期3",
                    id:3
                }
            ],
            myitems2:{
                parentMessage2:'Parent2',
                items2:[
                    {
                        date:"星期1111"
                    },
                    {
                        date:"星期2222"
                    },
                    {
                        date:"星期3333"
                    }
                ]
            },
            student:{
                name:'zs',
                age:18,
                phone:'136'
            },
            students:[
                {
                    name:'zs',
                    age:18,
                    phone:'111'
                },
                {
                    name:'ls',
                    age:18,
                    phone:'222'
                },{
                    name:'ww',
                    age:18,
                    phone:'333'
                }
            ]
        }
    });

    vue.students.push({name:'zl',age:19,phone:'444'})
</script>
</body>
</html>

~~~

### 3.5计算属性 computed

~~~html
<html>
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <script src="https://cdn.jsdelivr.net/npm/vue@2.6.12/dist/vue.js"></script>
</head>
<body>
<div id="app">
    <h2>
       计算属性
    </h2>
    <pre>
         模板内的表达式非常便利，但是设计它们的初衷是用于简单运算的。在模板中放入太多的逻辑会让模板过重且难以维护。例如：
        &lt;div id="example"&gt;
            {{ message.split('').reverse().join('') }}
        &lt;/div&gt;
        在这个地方，模板不再是简单的声明式逻辑。你必须看一段时间才能意识到，这里是想要显示变量 message 的翻转字符串。
        当你想要在模板中多次引用此处的翻转字符串时，就会更加难以处理。
        所以，对于任何复杂逻辑，你都应当使用计算属性。
        vue  computed 属性  用于计算复杂业务逻辑    把复杂业务逻辑抽取 实现维护方便
    </pre>

</div>
<hr>
<p>例子</p>
<div id="example">
    <p>Original message: "{{ message }}"</p>
    <p>Computed reversed message: "{{ reversedMessage }}"</p>
    <button @click="change()">change</button>

    <h2>计算属性 setter</h2>
    <p>Computed reversed info: "{{ reversedInfo }}"</p>
    <button @click="change2()">change2</button>

    <h2>计算属性缓存 vs 方法</h2>
    <p>Original message: "{{ message }}"</p>
    <p>Computed reversed message: "{{ reversedMessage }}"</p>
    <p>Computed reversed message: "{{ reversedMessage }}"</p>
    <p>Computed reversed message: "{{ reversedMessage2() }}"</p>
    <p>Computed reversed message: "{{ reversedMessage2() }}"</p>
</div>
<script type="text/javascript">
    var count = 1;
    new Vue({
        el: '#example',
        data:{
            message:'Hello',
            info:'Hello2'
        },
        computed:{
            // 计算属性的 getter
            reversedMessage() {
                // `this` 指向 vm 实例
                count++;
                console.log('---调用了message get');
                console.log(count);
                return this.message.split('').reverse().join('')
            },
            reversedInfo:{
                get(){
                    console.log('调用了info  get')
                    return this.info.split('').reverse().join('')
                },
                set(newValue){
                    console.log('调用了info  set');
                    console.log(newValue);
                    this.info = newValue;
                }
            }
        },
        methods:{
            change(){
                this.message="springcloud"
            },
            change2(){
                this.reversedInfo="springboot"
            },
            reversedMessage2 () {
                count++;
                console.log('---222');
                console.log(count);
                return this.message.split('').reverse().join('')
            }
        }
    });

</script>
</body>
</html>

~~~

### 3.6侦听属性 watch

>Vue 提供了一种更通用的方式来观察和响应 Vue 实例上的数据变动：**侦听属性**。当你有一些数据需要随着其它数据变动而变动时，你很容易滥用 `watch`——特别是如果你之前使用过 AngularJS。然而，通常更好的做法是使用计算属性而不是命令式的 `watch` 回调

~~~html
<html>
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <script src="https://cdn.jsdelivr.net/npm/vue@2.6.12/dist/vue.js"></script>
</head>
<body>
    <div id="app">
        <input type="text" v-model="n"> 的平方是：{{result}}    {{result2()}}
    </div>

    <div id="app2">
        <input type="text" v-model="n2"> 的平方是：{{result2}}
    </div>
<script type="text/javascript">
    new Vue({
        el:"#app",
        data:{
            n:1,
           // result:1
        },
        computed:{   //  计算属性
            result(){
                return this.n * this.n;
            }
        },
        methods:{
            result2(){
                return this.n*this.n;
            }
        }
    });

    let vm = new Vue({
        el:"#app2",
        data:{
            n2:1,
            result2:1
        },
        watch:{
            n2(newN,oldN){
                console.log(newN,oldN);
                this.result2= newN*newN;
            }
        }
    });
    //也会有下面的写法
    //vm.$watch('n2',function(newN,oldN){
    //     console.log(newN,oldN);
    //     this.result2= newN*newN;
    //})
</script>
</body>
</html>

~~~

3.7class与style绑定

~~~html
<html>
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <script src="https://cdn.jsdelivr.net/npm/vue@2.6.12/dist/vue.js"></script>
</head>
<body>
    <pre>
        操作元素的 class 列表和内联样式是数据绑定的一个常见需求。因为它们都是属性，
        所以我们可以用 v-bind 处理它们：只需要通过表达式计算出字符串结果即可。
        不过，字符串拼接麻烦且易错。因此，在将 v-bind 用于 class 和 style 时，Vue.js 做了专门的增强。
        表达式结果的类型除了字符串之外，还可以是对象或数组。
    </pre>
    <h2>绑定 HTML Class</h2>
    <div id="app">
        <h3>对象语法</h3>
        <div :class="{ active: isActive }"></div>
        <hr>
        <div class="static"
                :class="{ active: isActive, 'text-danger': hasError }"
        >123</div>

        <hr>
        <div :class="classObject"
        >123</div>

        <hr>
        <h2>数组语法</h2>

        <div v-bind:class="[activeClass, errorClass]"></div>


        <h2>绑定内联样式  v-bind:style</h2>
        <div v-bind:style="{ color: activeColor, fontSize: fontSize + 'px' }">123</div>
        <div v-bind:style="styleObject">222</div>
    </div>
<script type="text/javascript">
    new Vue({
        el:"#app",
        data:{
            isActive:true,
            hasError: true,
            classObject:{
                active: true,
                'text-danger': false
            },
            activeClass: 'active',
            errorClass: 'text-danger',
            activeColor: 'red',
            fontSize: 30,
            styleObject: {
                color: 'red',
                fontSize: '13px'
            }
        }
    });
</script>

    <style type="text/css">
        .active{
            border: 1px solid black;
            width: 100px;
            height: 100px;
        }
        .static{
            background-color: aquamarine;
        }
        .text-danger{
            color: red;
        }
    </style>
</body>
</html>

~~~

### 3.7事件处理

~~~html
<html>
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <script src="https://cdn.jsdelivr.net/npm/vue@2.6.12/dist/vue.js"></script>
</head>
<body>
    <h2>可以用 v-on 指令监听 DOM 事件，并在触发时运行一些 JavaScript 代码。</h2>
    <div id="app">
        <button @click="counter+=1">Add 1</button>
        <p>The button above has been clicked {{ counter }} times.</p>
    </div>
    <hr>
    <h2>事件处理方法</h2>
    <div id="example-2">
        <!-- `greet` 是在下面定义的方法名 -->
        <button @click="greet">Greet</button>
    </div>
    <h2>内联处理器中的方法</h2>
    <div id="example-3">
        <button @click="say('hi')">Say hi</button>

        <p>有时也需要在内联语句处理器中访问原始的 DOM 事件。可以用特殊变量 $event 把它传入方法：</p>
        <a  @click="warn('Form cannot be submitted yet.', $event)" href="https://www.baidu.com">
            Submit
        </a>
    </div>

    <h2>事件修饰符</h2>
    <pre>在事件处理程序中调用 event.preventDefault() 或 event.stopPropagation() 是非常常见的需求。
        尽管我们可以在方法中轻松实现这点，但更好的方式是：方法只有纯粹的数据逻辑，而不是去处理 DOM 事件细节。
    为了解决这个问题，Vue.js 为 v-on 提供了事件修饰符。之前提过，修饰符是由点开头的指令后缀来表示的。
        .stop
        .prevent
        .capture
        .self
        .once
        .passive
    </pre>
    <div id="example-4">
        <a @click.prevent="doThis" href="https://www.baidu.com">
            百度
        </a>
        <hr>
        <div @click = "doDivClick" style="width: 100px;height: 100px;border: 1px solid black">
            <a @click.stop="doThis" href="https://www.baidu.com">
                百度
            </a>
        </div>

    </div>

    <h2>按键修饰符</h2>
    <div id="example-5">
        <input type="text" v-model="name" @keyup.enter="submit">
    </div>
<script type="text/javascript">
    new Vue({
        el:"#app",
        data:{
            counter:0
        }
    });
   var vue2 = new Vue({
        el:"#example-2",
        data:{
            name:'zs'
        },
        methods:{
            greet(event){

                // `event` 是原生 DOM 事件
                //alert(event.target.tagName);
            }
        }
    });
    new Vue({
        el:"#example-3",
        data:{
            name:'zs'
        },
        methods:{
            say(mess){
                alert(mess);
                // `event` 是原生 DOM 事件
                //alert(event.target.tagName);
            },
            warn(mess,event){

                // 现在我们可以访问原生事件对象
                if (event) {
                    event.preventDefault()
                }
                alert(mess);
            }
        }
    });

    new Vue({
        el:"#example-4",
        methods:{
            doThis(){
                alert("执行到了a的click");
            },
            doDivClick(){
                alert("执行到了div的click");
            }
        }
    });
    new Vue({
        el:"#example-5",
        data:{
            name:'zs'
        },
        methods:{
            submit(){
                alert(this.name);
            }
        }
    });
    //alert(vue2.name);

    //vue2.greet();

</script>
</body>
</html>

~~~

### 3.8表单处理

~~~html
<html>
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <script src="https://cdn.jsdelivr.net/npm/vue@2.6.12/dist/vue.js"></script>
</head>
<body>
    <div id="app">
        <h2>文本</h2>
        <input v-model="message" placeholder="edit me">
        <p>Message is: {{ message }}</p>
        <p style="white-space: pre-line;">{{ message }}</p>
        <br>
        <h2>文本域</h2>
        <textarea v-model="message" placeholder="add multiple lines"></textarea>
        <h2>复选框</h2>
        <input type="checkbox" id="checkbox"  v-model="checked">
        <label for="checkbox">{{ checked }}</label>
        <h2>多个复选框，绑定到同一个数组：</h2>
        <div >
            <input type="checkbox" id="jack" value="Jack" v-model="checkedNames">
            <label for="jack">Jack</label>
            <input type="checkbox" id="john" value="John" v-model="checkedNames">
            <label for="john">John</label>
            <input type="checkbox" id="mike" value="Mike" v-model="checkedNames">
            <label for="mike">Mike</label>
            <br>
            <span>Checked names: {{ checkedNames }}</span>
        </div>
        <h2>单选按钮</h2>
        <div >
            <input type="radio" id="one" value="One" v-model="picked">
            <label for="one">One</label>
            <br>
            <input type="radio" id="two" value="Two" v-model="picked">
            <label for="two">Two</label>
            <br>
            <span>Picked: {{ picked }}</span>
        </div>

        <h2>选择框</h2>
        <div >
            <select v-model="selected">
                <option disabled value="">请选择</option>
                <option>A</option>
                <option>B</option>
                <option>C</option>
            </select>
            <span>Selected: {{ selected }}</span>
        </div>
        <H2>多选选择框</H2>
        <div >
            <select v-model="selecteds" multiple style="width: 50px;">
                <option>A</option>
                <option>B</option>
                <option>C</option>
            </select>
            <br>
            <span>Selected: {{ selecteds }}</span>
        </div>

        <h2>用 v-for 渲染的动态选项：</h2>
        <select v-model="selected">
            <option v-for="option in options" :value="option.value">
                {{ option.text }}
            </option>
        </select>
        <span>Selected: {{ selected }}</span>

        <h2>值绑定</h2>
        <pre>对于单选按钮，复选框及选择框的选项，v-model 绑定的值通常是静态字符串 (对于复选框也可以是布尔值)：</pre>
        <!-- 当选中时，`picked` 为字符串 "a" -->
        <input type="radio" v-model="picked" value="a">  {{picked}}

        <!-- `toggle` 为 true 或 false -->
        <input type="checkbox" v-model="toggle" true-value="yes">   {{toggle}}

        <!-- 当选中第一个选项时，`selected` 为字符串 "abc" -->
        <select v-model="selected">
            <option value="abc">ABC</option>
        </select>
        {{selected}}

        <h2>单选按钮</h2>
        <input type="radio" v-model="pick" v-bind:value="a">  {{pick}}

        <h2>选择框的选项</h2>
        <select v-model="selectedobj">
            <!-- 内联对象字面量 -->
            <option v-bind:value="{ number: 123 }">123</option>
        </select>
        {{selectedobj.number}}

        <h2>修饰符</h2>
        <!-- 在“change”时而非“input”时更新 -->
        <input v-model.lazy="msg" >  {{msg}}
        <!--如果想自动将用户的输入值转为数值类型，可以给 v-model 添加 number 修饰符：-->
        <input v-model.number="age" type="number">

        <%--如果要自动过滤用户输入的首尾空白字符，可以给 v-model 添加 trim 修饰符：--%>
        <input v-model.trim="msg">
    </div>

<script type="text/javascript">
    new Vue({
        el:"#app",
        data:{
            message:"",
            checked:'',
            checkedNames: [],
            picked:'',
            selected: 'B',
            selecteds:[],
            options:[
                { text: 'One', value: 'A' },
                { text: 'Two', value: 'B' },
                { text: 'Three', value: 'C' }
            ],
            toggle:'',
            a:'xxx',
            pick:'ooo',
            selectedobj:{},
            msg:''

        }
    });

</script>
</body>
</html>

~~~

### 3.9组件基础

~~~html
<html>
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <script src="https://cdn.jsdelivr.net/npm/vue@2.6.12/dist/vue.js"></script>
</head>
<body>
    <div id="app">
        <button-counter :title="msg" @event="fun1">
            <p>这是一个p</p>
        </button-counter>
       <button-counter :title2="msg2"></button-counter>
        <button-counter></button-counter>

    </div>

<script type="text/javascript">
    Vue.component('button-counter',{   //  创建一个全局组件  组件的名字是  button-counter
        //props:['title'],      /*父组件向子组件传值*/

        props:{
          title:{
              type:String,
              default:'默认值'
          },
            title2:{
                type:String,
                default:''
            },
        },
        data:function () {
            return {
                count:0
            }
        },
        methods:{
            clickFun(){
                this.count++;
                this.$emit('event',this.count);  // 触发   父组件的事件
            }
        },
        template:'<div><h1>h1...</h1><slot></slot><button @click="clickFun">{{title}}You clicked me {{ count }} times.{{title2}}</button><slot></slot></div>'
    });
    new Vue({
        el:"#app",
        data:{
            msg:'标题1',
            msg2:'标题2'
        },
        methods:{
            fun1(count){
                console.log('子组件向父组件传参'+count);
            }
        }
    });

    /*
    * 组件的概念
    * 如何创建全局组件
    * 组件的模板只能有一个根元素
    * props   取值   赋值（父组件向子组件赋值）
    * */
</script>
</body>
</html>

~~~

~~~html
<html>
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <script src="https://cdn.jsdelivr.net/npm/vue@2.6.12/dist/vue.js"></script>
</head>
<body>
    <div id="blog-post-demo">
        <!--<blog-post title="My journey with Vue" content="content..."></blog-post>
        <blog-post title="Blogging with Vue"></blog-post>
        <blog-post title="Why Vue is so fun"></blog-post>-->
        <hr>
           <div :style="{ fontSize: postFontSize + 'em' }">
        <blog-post @enlarge-text="onEnlargeText"
                v-for="post in posts"
                v-bind:key="post.id"
                v-bind:post="post"
        ></blog-post>
           </div>

           <hr>
           <custom-input
                   v-bind:value="searchText"
                   v-on:input="searchText = $event"
                   v-model="searchText"
           ></custom-input>


           <hr>
           <component-a title="这是局部组件"></component-a>

    </div>

<script type="text/javascript">
    Vue.component('blog-post', {
        //props: ['title','content'],
        props: ['post'],
        template: '<div class="blog-post"><h3>{{ post.title }}</h3>' +
            '<button @click="clickFun">Enlarge text</button><div v-html="post.content"></div><div v-html="post.comments"></div></div>'
        ,methods:{
            clickFun(){
                this.$emit('enlarge-text',0.1);
            }
        }
    })

    Vue.component('custom-input', {
        props: ['value'],
        template: `<input v-bind:value="value" v-on:input="$emit('input', $event.target.value)">`
    })

    new Vue({
        el: '#blog-post-demo',
        data: {
            posts: [
                { id: 1, title: 'My journey with Vue' ,content:'content1',comments:'评论1'},
                { id: 2, title: 'Blogging with Vue' ,content:'content2',comments:'评论2'},
                { id: 3, title: 'Why Vue is so fun' ,content:'content3',comments:'评论3'}
            ],
            postFontSize: 1,
            searchText:''
        },
        methods:{
            onEnlargeText(enlargeAmount) {
                this.postFontSize += enlargeAmount;
            }
        },
        components:{
            'component-a':{
                props: ['title'],
                template: '<div ><h2>{{title}}</h2></div>'
            }
        }
    })

</script>

<style type="text/css">
    .blog-post{
        border: 1px solid black;
    }
</style>
</body>
</html>

~~~



### 3.10 vue生命周期 

>每个 Vue 实例在被创建时都要经过一系列的初始化过程——例如，需要设置数据监听、编译模板、将实例挂载到 DOM 并在数据变化时更新 DOM 等。同时在这个过程中也会运行一些叫做生命周期钩子的函数，这给了用户在不同阶段添加自己的代码的机会。

<img src="https://gllspictures.oss-cn-beijing.aliyuncs.com/img/lifecycle.png" style="zoom: 50%;" />



生命周期主要有三个阶段：

一，初始化显示；（重要勾子 mounted 网页加载完毕触发）

二，更新显示；(重要勾子beforeUpdate 数据属性更新前)

三，死亡；（重要勾子beforeDestroy vm死亡前）



每个生命周期都会有对应的生命周期的函数，或者叫做勾子函数；

~~~html
<html>
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <script src="https://cdn.jsdelivr.net/npm/vue@2.6.12/dist/vue.js"></script>
</head>
<body>
    <pre>每个 Vue 实例在被创建时都要经过一系列的初始化过程——例如，需要设置数据监听、编译模板、
        将实例挂载到 DOM 并在数据变化时更新 DOM 等。同时在这个过程中也会运行一些叫做生命周期钩子的函数，
        这给了用户在不同阶段添加自己的代码的机会。</pre>
    <div id="app">
        <p>{{name}}</p>
        <button @click="update">update</button>
        <button @click="destroy">destroy</button>
    </div>
<script type="text/javascript">
    new Vue({
        el:"#app",
        data:{
            a:1,
            name:"zs"
        },
        methods:{
            update(){
                this.name = Math.random() +"---";
            },
            destroy(){
                this.$destroy();
            }
        },
        beforeCreate(){
          console.log("创建vue实例之前");
        },
        created(){
            //
            console.log("vue实例创建成功");
            console.log(this.a);
        }
       /* created: () => console.log(this.a)*/
        ,
        beforeMount(){
            console.log("vue对象挂载之前");
        },
        mounted(){
            // 只执行一次    页面加载完之后执行       比如 咱们在 页面加载完毕 发送ajax请求 获取数据
            console.log(" mounted   挂载完毕")
        },
        beforeUpdate(){
            // 可执行多次
            console.log("data更新之前执行");
        },
        updated(){
            // 可执行多次
            console.log("data更新之后执行");
        },
        beforeDestroy(){
            // 只执行一次
            console.log("vue实例销毁之前执行");
        },
        destroyed(){
            // 只执行一次
            console.log("vue实例销毁之后执行");
        }

    });
</script>
</body>
</html>

~~~



### 3.11 axios 

~~~js
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="../js/vue.js"></script>
    <script src="../js/axios.min.js"></script>
</head>

<body>


    <div id="app">
        <p>
            vue中使用ajax请求 <br>
            -- axios <br>
            -- vue-resource 用得不多
        </p>
        <table>
            <tr>
                <td>编号</td>
                <td>名字</td>
                <td>年龄</td>
                <td>邮箱</td>
            </tr>
            <tr v-for="user in users">
                <td>{{user.id}}</td>
                <td>{{user.name}}</td>
                <td>{{user.age}}</td>
                <td>{{user.email}}</td>
            </tr>
        </table>
    </div>


</body>
<script type="text/javascript">
    new Vue({
        el: "#app",
        data: {
            users: [
                {
                    id: 1,
                    name: "张三",
                    age: 18,
                    email: "123@qq.com"
                }
            ]
        },
        methods: {
            getUsers() {

                //let _this = this;   //  这里的this代表当气前 vue 实例 
                // 发送ajax请求  获取数据
                // 为给定 ID 的 user 创建请求
                // axios.get('http://localhost:8080/user/users?token=123')
                //     .then(function (response) {
                //         console.log(response);
                //         console.log(response.data.data);
                //         _this.users = response.data.data;    

                //     })
                //     .catch(function (error) {
                //         console.log(error);
                //     });

                // axios.get("http://localhost:8080/user/users?token=123")
                //     .then((response) => {
                //         console.log(response);
                //         console.log(response.data.data);
                //         this.users = response.data.data;
                //     })
                //     .catch((error) => {
                //         console.log(error);
                //     })


                axios.post('http://localhost:8080/user/users?token=123', {
                    firstName: 'Fred',
                    lastName: 'Flintstone'
                })
                    .then((response)=>{
                        this.users = response.data.data;
                    })
                    .catch(function (error) {
                        console.log(error);
                    });

            }
        },
        mounted() {
            this.getUsers();

        }
    })
</script>

</html>
~~~





## 4.vue-cli 脚手架创建vue工程



	准备工作：安装好 nodejs  安装好vscode      安装过程中可能出现的问题 百度可解决

![image-20230518174402346](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20230518174402346.png)

有版本号就正常，安装Node的时候，npm包管理工具也是一并安装的

> 查看 npm 的 版本         ：  npm -v

![image-20200831195651206](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20200831195651206.png)

可以再安装   cnpm  这个工具 ，使用它 下载东西较快, 这里 咱们安装的版本是    8.3.0 ，安装最新版 可能会出问题

>  npm  install  -g  cnpm@8.3.0  --registry=https://registry.npm.taobao.org



> 安装vue-cli   安装一次即可    安装时间很漫长

~~~java
cnpm install  -g   @vue/cli         //安装的是新版本   新版本  支持  vue ui 
~~~

>注意  这里的安装可能需要管理员权限
>
>安装完了之后 可能被windows的安全策略限制  参考
>
>[VSCode报错：vue : 无法加载文件 D:\nodejs\node_global\vue.ps1，因为在此系统上禁止运行脚本。_没有咸鱼的梦想的博客-CSDN博客](https://blog.csdn.net/nineteenthdog/article/details/106415113)



1.使用vue脚手架创建vue 项目,创建的方式  可以通过指令  也可以通过 vue ui

这里 咱们通过 vue ui 来创建，建议大家使用 管理员 来进行操作

![image-20230518174940875](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20230518174940875.png)

![image-20230518175107110](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/20230518175110.png)



![image-20210516154350266](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20210516154350266.png)

![image-20210516154402178](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20210516154402178.png)

![image-20210516154733414](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20210516154733414.png)

![image-20210516154921027](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20210516154921027.png)

![image-20210516155002913](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20210516155002913.png)

![image-20210516155200978](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20210516155200978.png)

![image-20210516155250009](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20210516155250009.png)

![image-20210516155410683](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20210516155410683.png)

创建项目  不保存预设    然后 后台就开始下载文件

![image-20210516155607012](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20210516155607012.png)

创建好之后  页面跳转到仪表盘

![image-20210516155638214](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20210516155638214.png)

可以在这里 安装一些插件   比如   **axios   element-ui**  等等 

![image-20210516155833290](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20210516155833290.png)

这是已经安装的插件

点 添加插件   搜索  element-ui

![image-20210516160045692](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20210516160045692.png)

![image-20210516160133753](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20210516160133753.png)

搜索  axios   点安装

![image-20210516160232766](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20210516160232766.png)

安装 ajax 插件  axios，



然后  可以关掉仪表盘，使用vscode 打开 刚才创建的工程  使用  vue run serve  启动工程，

![image-20210516201803181](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20210516201803181.png)







下图是 低版本的 工程结构

![image-20200831202202035](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20200831202202035.png)



这个是咱们 所创建的工程结构

![image-20230518175524292](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/20230518175528.png)

### 4.0  vue 文件结构

![image-20230518175750828](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/20230518175752.png)

一般 咱们会使用 用户代码片段   去写这个页面 

文件-》首选项-》配置用户代码片段-》新建全局代码片段文件-》把下面的代码粘贴进去

~~~java
{
    "生成vue模板": {
        "prefix": "vue",
        "body": [
            "<template>",
            "<div></div>",
            "</template>",
            "",
            "<script>",
            "//这里可以导入其他文件（比如：组件，工具js,第三方插件js,json文件，图片文件等等）",
            "//例如： import <<组件名称>> from '<<组件路径>>' ; ",
            "",
            "export default {",
            "//import 引入的组件需要注入到对象中才能使用",
            "components: {},",
            "props: {},",
            "data() {",
            "//这里存放数据",
            "return {",
            "",
            "};",
            "},",
            "//计算属性 类似于data概念",
            "computed: {},",
            "//监控data 中的数据变化",
            "watch: {},",
            "//方法集合",
            "methods: {",
            "",
            "},",
            "//生命周期 -创建完成 （可以访问当前this 实例）",
            "created() {",
            "",
            "},",
            "//生命周期-挂载完成（可以访问DOM 元素）",
            "mounted() {",
            "",
            "},",
            "beforeCreate() {}, //生命周期 -创建之前",
            "beforeMount() {}, //生命周期 - 挂载之前",
            "beforeUpdate() {}, // 生命周期 - 更新之前",
            "updated() {}, // 生命周期 -更新之后",
            "beforeDestroy() {}, //声明周期 - 销毁之前",
            "destroyed() {}, // 生命周期 - 销毁完成",
            "activated() {}, // 如果页面有keep-alive 缓存功能 这个函数会触发 ",
            "}",
            "</script>",
            "<style scoped>",
            "/* //@import url($3);引入公共css类 */",
            "$4",
            "</style>"
        ],
        "description": "生成vue模板"
    }
}
~~~



在vscode 中 启动 vue 工程，

![image-20230518180123825](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/20230518180127.png)

停止  ctrl + c





### 4.1 vue工程的组件使用

> 引入

![image-20210101184217439](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20210101184217439.png)

### 4.2 父组件向子组件传递数据---父子组件之间

>GllsDemo1.vue

~~~vue
<template>
    <div>
         <!-- {{msg}} -->
         {{title}}
         <button @click="clickFun">You clicked me {{ count }} times.</button>
         <slot></slot>
          <a :href="webSite.url" target="_blank">百度</a>
    </div> 
   
</template>

<script>
export default {
  name: 'GllsDemo1',
  data () {
    return {
      msg: 'Welcome to GllsDemo1',
      count: 0
    }
  },
  props:['title','webSite']
  ,
  methods:{
      clickFun(){
                this.count++;
                this.$emit('event',this.count);  // 触发   父组件的事件
    }
  }
}
</script>

<style>

</style>

~~~

>GllsDemo2.vue

~~~vue

<template>
    <div class="blog-post">
        <h3>{{ post.title }}</h3>
        <button @click="clickFun">Enlarge text</button>
        <div v-html="post.content"></div>
        <button @click="testParentMethod">testMethod</button>
    </div>
</template>

<script>
export default {
    name:"GllsDemo2",
    data(){
        return {
            msg:'childMsg'    
        }
    },
    props:['post','parentMethod'],   // 这里 不但能接属性 还能接方法
    methods:{
        clickFun(){
                this.$emit('enlarge-text',0.1);   // emit 的方式 调用父组件的方法
            },
        testParentMethod(){
            this.parentMethod('子调父方法');    // 接了父组件传过来的方法
        }
    }
}
</script>

<style>
	
</style>
~~~

>App.vue

~~~vue
<template>
  <div id="app">
    <!-- <img src="./assets/logo.png">
    <router-view/> -->
   <glls-demo-1 :title="msg" :webSite="webSite" @event="fun1">
       <p>这是一个p，通过插槽传递过去 </p>
   </glls-demo-1>
   <glls-demo-1 :title="msg2" :webSite="webSite"></glls-demo-1>


    <div :style="{ fontSize: postFontSize + 'em' }">
        <glls-demo-2 @enlarge-text="onEnlargeText" :parentMethod="mymethod" v-for="(post,index) in posts" v-bind:key="index" v-bind:content="post.content" :post="post"></glls-demo-2>
    </div>
   
  </div>
</template>

<script>
import GllsDemo1 from './components/GllsDemo1.vue'
import GllsDemo2 from './components/GllsDemo2.vue';


export default {
  components: { GllsDemo1, GllsDemo2 },
 
  name: 'App',
  data () {
    return {
      msg: '传递给子组件',
      msg2: '传递给子组件2',
      postFontSize: 1,
      webSite:{
        url:'http://www.baidu.com',
        title:'测试xxxx'
      },
      posts: [
                { id: 1, title: 'My journey with Vue' ,content:'content1',comments:'评论1'},
                { id: 2, title: 'Blogging with Vue' ,content:'content2',comments:'评论2'},
                { id: 3, title: 'Why Vue is so fun' ,content:'content3',comments:'评论3'}
            ]
    }
  },
  methods:{
    fun1(count){
                console.log('子组件向父组件传参'+count);
    },
    onEnlargeText(enlargeAmount) {
                this.postFontSize += enlargeAmount;
    },
    mymethod(msg){
       this.msg=msg; 
    }
  }
}


</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

~~~

总结： 父组件 向 子组件 传递  数据  ，这个数据 可以是  属性 也可以是  方法  好好体会下



> **props 方式 传递数据** 
>
> 子组件

![image-20210101184617456](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20210101184617456.png)

>父组件

![image-20210101184720656](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20210101184720656.png)

>emit 方式 调用父组件方法
>
>参考上文代码

### 4.3 消息订阅与发布组件PubSub

>我们前面讲了父子组件之间通过prop来实现消息传递；但是再其他情况，比如兄弟组件，爷孙组件消息传递时候，就要用到高级的消息订阅与发布；

>1.首先我们安装下消息订阅与发布pubsub组件；

~~~shell
cnpm install --save pubsub-js
~~~

>2.把 pubsub 配置成全局组件  在 main.js 中配置

![image-20210101195650862](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20210101195650862.png)

>3. 在 父组件中 订阅消息  可以在  mounted 钩子函数中   监听消息
>
>

![image-20210101200902824](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20210101200902824.png)



在这里  使用了 箭头函数  =>   ,在箭头函数中 的 this 代表 当前 vue 对象，如果 使用一般函数 ，那么在这个函数内 this 就代表PubSub对象，所以 在这里 咱们使用 =>箭头函数

>在别的组件中     发布消息  

![image-20210101201008987](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20210101201008987.png)

注意： 执行上面的案例  会发现 订阅消息的回调函数 执行了两次  ，  我们需要在我们每次接受数据pubsub.subscribe的时候，先执行pubsub.unsubscribe操作就好了，就完美解决了，这样你接收以后的callback只执行一次

~~~js
PubSub.unsubscribe();
PubSub.subscribe(eventName, callback);   //这样  回调就只执行一次
~~~







### 4.4 插槽 slot

父组件向子组件传递标签，通过slot 插槽实现

主要作用：

某一个区块，先占位，然后可以动态的搞个标签进去，方便切换该位置的内容，无需再搞多个页面；

>父组件   直接定义标签p  注意  slot 属性

![image-20210101204238546](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20210101204238546.png)

>子组件  使用 slot 标签 占位置    注意  slot 标签的name 属性，当父组件没有传对应的插槽（属性值对应）内容时，会显示插槽默认内容

![image-20210101204346453](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20210101204346453.png)

## 5.  ajax框架  

vue的ajax框架有vue-resource和axios；vue-resource插件非官方库，axios是ajax通用请求库，vue官方推荐；

在这里，咱们先只研究axios

>axios 的用法

`https://github.com/axios/axios`

>安装    咱们    已经在 vue  ui 中 安装过了

>创建GllsDemo4.vue     

~~~html
<template>
  <div>
         <input type="text" v-model="name">   <button @click="getUsers()">查询</button>
        <table>
            <tr>
                <td>编号</td>
                <td>名字</td>
                <td>年龄</td>
                <td>邮箱</td>
            </tr>
            <tr v-for="user in users" :key="user.id">
                <td>{{user.id}}</td>
                <td>{{user.name}}</td>
                <td>{{user.age}}</td>
                <td>{{user.email}}</td>
            </tr>
        </table>
  </div>
</template>
<script>
export default {
     name:"GllsDemo4",
      data(){
        return {
            name:'',
    users: [
                    {
                        id: 1,
                        name: "zs",
                        age: 18,
                        email: "xxx@qq.com"
                    }
                ]
        }
    },
    methods:{
        getUsers() {
        axios.post("http://localhost:8088/user/users",{name:this.name})
                        .then((res) => {
                            this.users = res.data.data.users;
                        })
                        .catch(function (error) {
                            console.log(error);
                        })
    }
        
    },
    mounted(){
      	 this.getUsers();
    }
}
</script>

<style>

</style>
~~~

>准备 后台 接口   需要 注意  前后端交互 问题
>
>请求 方式   ？   
>
> 携带参数的方式？    
>
>跨域问题？   
>
>后端怎么接参数   ？ 、
>
> 后端响应的数据结构是什么？ 
>
>前端怎么接后端响应的数据





## 6.Vue Router

vue Router路由组件是vue的核心组件； 平时我们通过路由组件来实现导航菜单以及各种页面切换；我们在安装vue-cli 的时候  安装了这个组件，如果一开始没有安装  也可以通过   npm install vue-router --save  来安装。

这里 咱们已经安装好了vue router,并且vue-cli 已经自动帮助咱们配置好了 ，咱们直接使用即可

### 6.1 基本用法

>在main.js 中的 router 配置，  咱们 用 vue ui 安装的时候 已经自动配置到  main.js 了 

~~~js
import router from './router'

new Vue({
  el: '#app',
  router,
  components: { App },
  template: '<App/>'
})
~~~

>在 router文件夹下  的index.js 是 路由的配置文件
>
>创建views 文件夹  其下面创建Index.vue 和 Menu1.vue

~~~js
import Vue from 'vue'
import Router from 'vue-router'
import HelloWorld from '@/components/HelloWorld'
import Index from '@/views/Index'
import Menu1 from '@/views/Menu1'
Vue.use(Router)

export default new Router({
  routes: [
    {
      path: '/',
      name: 'HelloWorld',
      component: HelloWorld
    },
    {
      path: '/index',
      name: 'Index',
      component: Index
    },
    {
      path: '/menu1',
      name: 'Menu1',
      component: Menu1
    }
  ]
})

~~~

  >在App.vue 中的路由写法

~~~html
 <div class="menu">
      <ul>
        <li>
          <!--<a href="">首页</a>-->
          <router-link to="/index">首页</router-link>
        </li>
        <li>
          <!--<a href="">菜单1</a>-->
          <router-link to="/menu1">菜单1</router-link>
        </li>
      </ul>
    </div>
    <div class="content">
      <router-view></router-view>
    </div>

<style scoped>
/* 这里的scoped 是 设置 样式作用范围  如果加上 scoped 就 只作用于当前页面   
  如果不加 scoped 就会影响 他的 路由视口页面
*/


ul li{

  float: left;
  list-style: none;
  padding-left: 30px;

}

.content{
  clear: both;
}

</style>
~~~

通过 router-link 向路由配置发送请求 ，结果会在 router-view 显示

### 6.2嵌套路由

>Menu1.vue 继续嵌套 下级页面   配置嵌套路由

Menu1.vue

~~~html
<div>
      {{msg}}
      <ul>
          <li>
            <router-link to="/menu1/submenu1">子菜单1</router-link>
          </li>
          <li>
            <router-link to="/menu1/submenu2">子菜单2</router-link>
          </li>
        </ul>

        <div class="content">
                <router-view></router-view>
      </div>

  </div>
~~~

在路由配置文件中

~~~js
 {
      path: '/menu1',
      name: 'Menu1',
      component: Menu1,
      children:[   // 子路由
        {
          path:'/menu1/submenu1',    // 当然  对应的 子组件 得创建好
          component: () => import('@/views/SubMenu1.vue')   // 这样就不用在文件上面配置了
        },
        {
          path:'/menu1/submenu2',
          component: () => import('@/views/SubMenu2.vue')
        },
        {
          path:'',
          redirect:'/menu1/submenu1'     // 默认显示submenu1
        }
      ]
    },
~~~

SubMenu1.vue

~~~html
<template>
  <div>子菜单1
      <input type="text" name="sub1input">
  </div>
</template>
~~~

SubMenu2.vue

~~~html
<template>
  <div>子菜单2
      <input type="text" name="sub2input">
  </div>
</template>
~~~

### 6.3路由缓存

当我们 在 子菜单1 和 子菜单2 的 文本输入框输入内容时，发现 跳转之后内容没有了，这种情况也经常遇到

![image-20210102083806817](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20210102083806817.png)

我们切换不同的组件时，希望 组件内输入的内容不要丢失  ，怎么解决？只需要 使用keep-alive 标签

![image-20210102083912214](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20210102083912214.png)

### 6.4 路由组件传参

![image-20210102100459807](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20210102100459807.png)

在App.vue  添加 用户信息 路由菜单 ， 配置 路由配置文件  

~~~java
  {
    path: '/user',
    name: 'user',
    component: () => import('../views/User.vue'),
   
  },
~~~



用户信息组件  User.vue

~~~html
    <table>
          <tr>
              <th>编号</th>
               <th>用户名</th>
                <th>密码</th>
          </tr>
          <tr v-for="(user,index) in users" v-bind:key="index">
              <td>{{user.id}}</td>
               <router-link :to="`/user/subUser/${user.id}`"><td>{{user.userName}}</td></router-link>
                <td>{{user.password}}</td>
          </tr>
      </table>
~~~

路由配置

~~~js
{
    path: '/user',
    name: 'user',
    component: () => import('../views/User.vue'),
    children:[
      {
        path:'/user/subUser/:id',    // 当然  对应的 子组件 得创建好
        component: () => import('@/views/SubUser.vue')   // 这样就不用在文件上面配置了
      },
    ]
  },
~~~

SubUser.vue

~~~html
<template>
  <div>
       Id:{{$route.params.id}}<br/>

      {{user.userName}}<br/>

      {{user.password}}<br/>
  </div>
</template>

<script>
export default {
    name:"SubMenu",
    data(){
        return {
            user:{}
        }
    },
    methods: {
    getUserById(id){
            axios.get(`http://localhost:8088/user/user/${id}`)
                        .then((res) => {
                            console.log(res);
                            this.user = res.data.data.user;
                        })
                        .catch(function (error) {
                            console.log(error);
                        })
    }
},
    
    mounted(){
       let id=this.$route.params.id;
    console.log(id);
    this.getUserById(id);
    },
   watch: {
    $route(value){
             let id=value.params.id;
             this.getUserById(id);   
         }
	},
}
</script>

<style>

</style>
~~~

### 6.5 编程式路由导航

![image-20210102102407383](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20210102102407383.png)

~~~html
<template>
  <div>
    用户信息 <br />
    <input type="text" v-model="name" />
    <button @click="getUsers()">查询</button>
    <table>
      <tr>
        <td>编号</td>
        <td>名字</td>
        <td>年龄</td>
        <td>邮箱</td>
        <th>测试编程式路由</th>
      </tr>
      <tr v-for="user in users" :key="user.id">
        <td>{{ user.id }}</td>
        <router-link :to="`/user/subUser/${user.id}`">
          <td>{{ user.name }}</td>
        </router-link>
        <td>{{ user.age }}</td>
        <td>{{ user.email }}</td>
        <td>
          <button @click="pushShow(user.id)">push显示</button>
          <button @click="replaceShow(user.id)">replace显示</button>
        </td>
      </tr>
    </table>
    
    <button @click="$router.back()">回退</button>
    <hr />
    <div class="content">
      <router-view></router-view>
    </div>
  </div>
</template>

<script>
//这里可以导入其他文件（比如：组件，工具js,第三方插件js,json文件，图片文件等等）
//例如： import <<组件名称>> from '<<组件路径>>' ;

export default {
  //import 引入的组件需要注入到对象中才能使用
  components: {},
  props: {},
  data() {
    //这里存放数据
    return {
      name: "",
      users: [
        {
          id: 1,
          name: "zs",
          age: 18,
          email: "xxx@qq.com",
        },
      ],
    };
  },
  //计算属性 类似于data概念
  computed: {},
  //监控data 中的数据变化
  watch: {},
  //方法集合
  methods: {
    pushShow(id) {
      console.log(id);
      this.$router.push(`/user/subUser/${id}`);
    },

    replaceShow(id) {
      this.$router.replace(`/user/subUser/${id}`);
    },
    getUsers() {
      axios
        .post("http://localhost:8088/user/users", { name: this.name })
        .then((res) => {
          this.users = res.data.data.users;
        })
        .catch(function (error) {
          console.log(error);
        });
    },
  },
  //生命周期 -创建完成 （可以访问当前this 实例）
  created() {},
  //生命周期-挂载完成（可以访问DOM 元素）
  mounted() {
    this.getUsers();
  },
  beforeCreate() {}, //生命周期 -创建之前
  beforeMount() {}, //生命周期 - 挂载之前
  beforeUpdate() {}, // 生命周期 - 更新之前
  updated() {}, // 生命周期 -更新之后
  beforeDestroy() {}, //声明周期 - 销毁之前
  destroyed() {}, // 生命周期 - 销毁完成
  activated() {}, // 如果页面有keep-alive 缓存功能 这个函数会触发
};
</script>
<style scoped>
/* //@import url();引入公共css类 */
</style>
~~~

## 7.Vue x 状态集中式管理

>Vuex 是一个专为Vue.js 应用程序开发的状态管理模式。https://vuex.vuejs.org/zh/
>
>简单地说 在复杂应用中 Vuex 对vue 应用中的多个组件的共享状态进行集中式管理。

步骤

1.先创建一个没有使用  vuex的组件    MyVuex.vue  

~~~html
<p>当前数字： {{number}} is {{evenOrOdd}}</p>
    <button v-on:click="jia()">加</button>
    <button @click="jian()">减</button>
~~~

~~~js
data() {
//这里存放数据
return {
    number:0
};
},
~~~

~~~js
methods: {
   jia(){
       this.number++
   },
   jian(){
       this.number--
   }    
},
~~~

~~~js
computed: {
	evenOrOdd(){
        return this.number%2==0?'偶数':'奇数'
    }

},
~~~

就有了计数器的效果

![image-20210516185447774](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20210516185447774.png)

但是  如果项目里 需要多个组件 共享这个 number 的值 ，也就是 number 的变化  很多组件都能感知到 怎么实现，vuex 状态集中式管理 就是解决这个问题的

> 首先  安装    咱们是在  vue  ui   创建工程的时候 已经勾选了 vuex ，所以 无需再安装



~~~js
import Vue from 'vue'
import Vuex from 'vuex'
Vue.use(Vuex);

// 全局 state 对象，用于保存所有组件的公共数据
const state = {
    // 在组件中是通过 this.$store.state.number 来获取
   number:0
  };
  
  // 实时监听 state 值的最新状态，注意这里的 getters 可以理解为计算属性
  const getters = {
	// 在组件中是通过 this.$store.getters.evenOrOdd 来获取
    evenOrOdd(state){
        return state.number%2==0 ? '偶数' : '奇数'
    }

  };
  
  // 定义改变 state 初始值的方法，这里是唯一可以改变 state 的地方，缺点是只能同步执行
  const mutations = {
      // 在组件中是通过 this.$store.commit('jia'); 方法来调用 mutations
    jia(state){
       state.number++     
    },
    jian(state){
        state.number--
    }
  };
  
  // 定义触发 mutations 里函数的方法，可以异步执行 mutations 里的函数
  const actions = {
      
       // 在组件中是通过 this.$store.dispatch('jia'); 来调用 actions
      
    jia(context){
        
        context.commit('jia')
    },
       // 在组件中是通过 this.$store.dispatch('jian'); 来调用 actions
    jian({commit,state}){    //解构 context 对象  可以拿到对象属性  commit  和  state
        if(state.number>0){

            commit('jian')
        }
    }
  };
  
  export default new Vuex.Store({
    state,
    getters,
    mutations,
    actions
  });
~~~



>修改 main.js 增加刚才配置的 store/index.js，关键代码如下：

~~~js
import Vue from 'vue'
import Vuex from 'vuex'
import store from './store'

Vue.use(Vuex);

new Vue({
  el: '#app',
  store
});
~~~



>修改MyVuex.vue

~~~html
 <p>当前数字： {{$store.state.number}} is {{$store.getters.evenOrOdd}}</p>
    <button v-on:click="jia()">加</button>
    <button @click="jian()">减</button>
~~~

~~~js
methods: {

    jia(){
        this.$store.dispatch('jia')     // 调用   actions 中的方法
     },
    jian(){
          this.$store.dispatch('jian')
     }

},
~~~

依然 可以实现之前的效果

但是感觉  每次 都写 $.store.xxx.xxx 太长了  ，怎么办？

~~~js
// 不想每次都写 $store.state.xxx    就导入组件  然后 计算属性    
//  第一步
import {mapState,mapGetters,mapActions} from 'vuex'
~~~

~~~js
//计算属性 类似于data概念
computed: {
    // evenOrOdd(){
    //     return this.number%2==0?'偶数':'奇数'
    // }

    // 第二步
    ...mapState(['number']),
    ...mapGetters(['evenOrOdd'])  // 如果 名字不一致

    //...mapGetters({'evenOrOdd':'evenOrOdd222'})    // 如果 名字不一致  vuex 中的 getters 内部的方法名 为 evenOrOdd222   不建议这样写
},
~~~

~~~js
methods: {

    // jia(){
    //     this.number++
    // },
    // jian(){
    //     this.number--
    // }



    //jia(){
    //    this.$store.dispatch('jia')
    //},
    //jian(){
    //     this.$store.dispatch('jian')
    //}

    ...mapActions(['jia','jian'])
},
~~~

~~~html
<div>
     <!-- <p>当前数字 {{$store.state.number}} is {{$store.getters.evenOrOdd}}</p>      -->

    <!-- // 第三步  -->
    <p>当前数字： {{number}} is {{evenOrOdd}}</p>
    <button v-on:click="jia()">加</button>
    <button @click="jian()">减</button>
</div>
~~~

##### 解决浏览器刷新后 Vuex 数据消失问题

- 问题描述

> Vuex 的状态存储是响应式的，当 Vue 组件从 store 中读取状态的时候，若 store 中的状态发生变化，那么相应的组件也会相应地得到高效更新。但是有一个问题就是：vuex 的存储的数据只是在页面的中，相当于我们定义的全局变量，刷新之后，里边的数据就会恢复到初始化状态。但是这个情况有时候并不是我们所希望的。

- 解决方案

> 监听页面是否刷新，如果页面刷新了，将 state 对象存入到 sessionStorage 中。页面打开之后，判断 sessionStorage 中是否存在 state 对象，如果存在，则说明页面是被刷新过的，将 sessionStorage 中存的数据取出来给 vuex 中的 state 赋值。如果不存在，说明是第一次打开，则取 vuex 中定义的 state 初始值。

- 修改代码

> 在 App.vue 中增加监听刷新事件

```javascript
  export default {
    name: 'App',
    mounted() {
      window.addEventListener('unload', this.saveState);
    },
    methods: {
      saveState() {
        sessionStorage.setItem('state', JSON.stringify(this.$store.state));
      }
    }
  }
```

> 修改 store/index.js 中的 state

```javascript
const state = sessionStorage.getItem('state') ? JSON.parse(sessionStorage.getItem('state')) : {
  user: {
    name: ''
  }
};
```



思考： 此时 复制 MyVuex.vue 组件 复制出来一个新的 MyVuex2.vue  ， 访问 这两个 页面  为什么 number 的值 却没有共享？

![image-20210516195912881](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20210516195912881.png)

![image-20210516195921076](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20210516195921076.png)

vuex 和 vuex 2 中 number 的值怎么不一致？  注意 这是两个窗口  相当于是两个人，所以不一致， 再试试在一个窗口 进行页面跳转 就会发现一致了





## 个人学习：

### 1.webpack介绍

Webpack是一个前端资源的打包工具，它可以将js、image、css等资源当成一个模块进行打包。

![image-20210103091834000](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20210103091834000.png)

从图中我们可以看出，Webpack可以将js、css、png等多种静态资源进行打包，使用webpack有什么好处呢？

1、模块化开发程序员在开发时可以分模块创建不同的js、css等小文件方便开发，最后使用webpack将这些小文件打包成一个文件，减少了http的请求次数。webpack可以实现按需打包，为了避免出现打包文件过大可以打包成多个文件。

2、编译typescript、ES6等高级js语法随着前端技术的强大，开发中可以使用javascript的很多高级版本，比如：typescript、ES6等，方便开发，webpack可以将打包文件转换成浏览器可识别的js语法。

3、CSS预编译webpack允许在开发中使用Sass和Less等原生CSS的扩展技术，通过sass-loader、less-loader将Sass和Less的语法编译成浏览器可识别的css语法

4.使用vue.js开发大型应用需要使用webpack打包工具

### 2.安装webpack

#### 2.1 webpack基于node.js运行，首先需要安装node.js。

		node.js  可以把它理解成前端项目的 开发运行环境，就像 java项目的 jdk一样。
	
	   这个咱们前面安装过了，安装步骤 简单   详细步骤 可查阅前面的资料。

#### 2.2 安装 npm

		npm全称NodePackageManager，他是node包管理和分发的工具，使用NPM可以对应用的依赖进行管理，		NPM的功能和服务端项目构建工具maven差不多，我们通过npm可以很方便地下载js库，打包js文件。	   node.js已经集成了npm工具，在命令提示符输入npm-v可查看当前npm版本

#### 2.3设置 npm包路径

	  包路径就是npm从远程下载的js包所存放的路径。使用npmconfigls查询NPM管理包路径（NPM下载的依赖包所存放的路径）  这个 也是 查看前面的资料  有详细配置

#### 2.4 安装cnpm

npm默认会去国外的镜像去下载js包，在开发中通常我们使用国内镜像，这里我们使用淘宝镜像

下边我们来安装cnpm：有时我们使用npm下载资源会很慢，所以我们可以安装一个cnmp(淘宝镜像)来加快下载速度。

输入命令，进行全局安装淘宝镜像。

npm  install  -g  cnpm   --registry=https://registry.npm.taobao.org

安装后，我们可以使用以下命令来查看cnpm的版本

cnpm   -v

nrm   ls         查看镜像已经指向 taobao

![image-20210103092810308](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20210103092810308.png)

命令：     nrm    use     XXX     切换镜像

如果nrm没有安装则需要进行全局安装：  cnpm   install  -g    nrm

如果执行 nrm 出异常      nrm ls报错:The "path" argument must be of type string. Received undefined   参考下面解决方案
https://www.jianshu.com/p/126ba674e395


const NRMRC = path.join(process.env[(process.platform == 'win32') ? 'USERPROFILE' : 'HOME'], '.nrmrc');


此句话的意思是更具不同的系统平台获取不同的路径。



#### 2.5 安装webpack

webpack安装分为本地安装和全局安装：

#### 2.5.1 本地安装：

    仅将webpack安装在当前项目的node_modules目录中，仅对当前项目有效。
    
    只在我的项目中使用webpack，需要进行本地安装，因为项目和项目所用的webpack的版本不一样。本地安装就会将webpack的js包下载到项目下的npm_modeuls目录下。

在门户目录下创建webpack测试目录webpacktest01：

npm install   --save-dev    webpack   或  cnpm  install  --save-dev   webpack

npm  install  --save-dev webpack-cli        (4.0以后的版本需要安装webpack-cli)

#### 2.5.2全局安装：

将webpack安装在本机，对所有项目有效，全局安装会锁定一个webpack版本，该版本可能不适用某个项目。全局安装需要添加-g参数。

全局安装就将webpack的js包下载到npm的包路径下。

npm  install    webpack  -g  或   cnpm   install   webpack   -g

#### 2.5.3 安装webpack指定的版本：

本教程使用webpack3.6.0，安装webpack3.6.0：

进入webpacktest测试目录，运行：cnpm install  --save-dev    webpack@3.6.0

全局安装：npm  install   webpack@3.6.0  -g  或  cnpm    install   webpack@3.6.0    -g

### 3.webpack 入门程序

通过本入门程序体会webpack打包的过程及模块化开发的思想

需求分析通过入门程序实现对js文件的打包，体会webpack是如何对应用进行模块化管理。

对上边1+1=2的例子使用webpack进行模块化管理

![image-20210108152555778](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20210108152555778.png)

>定义模块

创建webpacktest01目录，将vue.min.js及vue_02.html拷贝到目录下。

1、定义model01.js在webpacktest01目录下创建model01.js  将本程序使用的加法运算的js方法抽取到一个js文件，此文件就是一个模块

~~~js
// 定义 add 函数
function add(x,y){
    return x+y;
}


//function add2(x,y) {
//    return x+y+2;
//}

//导出add 方法

module.exports.add = add;
// module.exports ={add,add2};//如果有多个方法这样导出
// module.exports.add2 = add2//如果有多个方法也可以这样导出
~~~

> 定义main.js

在webpacktest01目录下创建main.js，main.js是本程序的js主文件，包括如下内容：

1、在此文件中会引用model01.js模块

2、引用vue.min.js（它也一个模块）

3、将html页面中构建vue实例的代码放在main.js中。

main.js的代码如下

~~~js
var {add} = require('./model01');
var Vue = require('./vue.min');

var VM = new Vue({
    el:"#app",
    data:{
        name:'高级程序员',// 相当于是MVVM中的Model这个角色
        num1:0,
        num2:0,
        result:0,
        url:'http://www.lxw.cn'
    },
    methods:{
        change:function(){//这里使用了导入的model01.js文件中的add方法
            this.result = add(Number.parseInt(this.num1),Number.parseInt(this.num2));
            alert(this.result) }
    }
});
~~~

>打包测试

上边将mode01.js模块及main.js主文件编写完成，下边使用webpack对这些js文件进行打包

1、进入程序目录，执行webpack main.js build.js ，这段指令表示将main.js打包输出为build.js文件执行完成，观察程序目录是否出现build.js。

2、在html中引用build.js

~~~html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>vue.js常用指令的测试</title>
</head>
<body>
<!--实现在body区域显示一个传智播客名称-->
<div id="app">
    <!--相当于MVVM的view视图-->
    <!--{{name}}-->
    <a v-bind:href="url">
    <span v-text="name"></span>
    </a>
    <input type="text" v-model="num1"/> +
    <input type="text" v-model="num2"/>=
   <!-- <span v-text="Number.parseInt(num1)+Number.parseInt(num2)"></span>-->
    <span v-text="result"></span>
    <!--{{Number.parseInt(num1)+Number.parseInt(num2)}}-->
    <button v-on:click="change">计算</button>
</div>
</body>
<!--<script src="vue.min.js"></script>-->
<script src="build.js"></script>
<script>
    //编写MVVM中的model部分及VM（ViewModel）部分

</script>
</html>
~~~

>测试总结

测试功能：

1）输入任意加数，其和会自动计算

2）点击“计算”会调用model01.js中的add方法

总结：webpack可以将js分模块开发，开发完成对各模块代码打包成一个统一的文件。前端模块开发的思想和服务端模块开发的思想是一致的，有利于多人协助开发。





### 4.webpack-dev-server

webpack-dev-server开发服务器，它的功能可以实现热加载并且自动刷新浏览器。创建一个新的程序目录，

这里我们创建webpacktest02目录，将webpack入门程序的代码拷贝进来，并在目录下创建src目录、dist目录。将main.js和model01.js   vue.js  拷贝到src目录。

>安装配置   安装webpack-dev-server

使用webpack-dev-server需要安装webpack、webpack-dev-server和html-webpack-plugin三个包。cnpm install webpack@3.6.0 webpack-dev-server@2.9.1 html-webpack-plugin@2.30.1 --save-dev安装完成，会发现程序目录出现一个package.json文件，此文件中记录了程序的依赖。执行下面的命令：

~~~shell
cnpm install webpack@3.6.0 webpack-dev-server@2.9.1 html-webpack-plugin@2.30.1 --save-dev
~~~

>配置webpack-dev-server

在package.json中配置script

![image-20210108153355389](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20210108153355389.png)

~~~js
{
  "scripts": {
    "dev": "webpack-dev-server --inline --hot --port 5008"
  },
  "devDependencies": {
    "html-webpack-plugin": "^2.30.1",
    "webpack": "^3.6.0",
    "webpack-dev-server": "^2.9.1"
  }
}

~~~

devDependencies：开发人员在开发过程中所需要的依赖。

scripts：可执行的命令

>配置webpack.config.js

在webpacktest02目录下创建webpack.config.js，webpack.config.js是webpack的配置文件。在此文件中可以配置应用的入口文件、输出配置、插件等，其中要实现热加载自动刷新功能需要配置html-webpack-plugin插件。html-webpack-plugin的作用是根据html模板在内存生成html文件，它的工作原理是根据模板文件在内存中生成一个index.html文件。

1、配置模板文件将原来的vue_02.html作为模板文件，为了和内存中的index.html文件名区别，注意将vue_02.html中的script标签去掉，内容如下：

~~~html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>vue.js常用指令的测试</title>
</head>
<body>

<div id="app">
    <!--相当于MVVM的view视图-->
    <!--{{name}}-->
    <a v-bind:href="url">
    <span v-text="name"></span>
    </a>
    <input type="text" v-model="num1"/> +
    <input type="text" v-model="num2"/>=
   <!-- <span v-text="Number.parseInt(num1)+Number.parseInt(num2)"></span>-->
    <span v-text="result"></span>
    <!--{{Number.parseInt(num1)+Number.parseInt(num2)}}-->
    <button v-on:click="change">计算</button>
</div>
</body>
<!--<script src="vue.min.js"></script>-->

</html>
~~~

>配置html-webpack-plugin

在webpack.config.js中配置html-webpack-plugin插件

~~~js
var htmlwp=require('html-webpack-plugin');

module.exports={
    entry:'./src/main.js',   //指定打包的入口文件
    output:{
        path:__dirname+'/dist',   //注意：__dirname表示webpack.config.js所在目录的绝对路径
        filename:'build.js'    //输出文件
    },
    devtool: 'eval-source-map',
    plugins:[
        new htmlwp({
            title:'首页',    //生成的页面标题<head><title>首页</title></head>
            filename:'index.html',    //webpack‐dev‐server在内存中生成的文件名称，自动将build注入到这个页面底部，才能实现自动刷新功能
            template:'vue_02.html'    //根据  vue_02.html   这个模板来生成(这个文件请程序员自己生成)})]}
        })
    ]

}

~~~

>启动

启动文件：

1、进入webpacktest02目录，执行npm run dev

2、使用webstorm，右键package.json文件，选择“Show npm Scripts”打开窗口：

![image-20210108154018599](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20210108154018599.png)

>degug调试

使用了webpack之后就不能采用传统js的调试方法在chrome中打断点

webpack将多个源文件打包成一个文件，并且文件的内容产生了很大的变化，webpack提供devtool进行调试，devtool是基于sourcemap的方式，在调试时会生成一个map文件，其内容记录生成文件和源文件的内容映射，即生成文件中的哪个位置对应源文件中的哪个位置，有了sourcemap就可以在调试时看到源代码。

配置如下：

1、在webpack.config.js中配置：

![image-20210108154121437](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20210108154121437.png)

![image-20210108154134507](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20210108154134507.png)

![image-20210108154146169](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20210108154146169.png)

# 课后练习demo

智慧云在线教育平台

用户表

	![image-20210521085028534](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20210521085028534.png)


​	

角色表

![image-20210521085045878](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20210521085045878.png)

	学生 教师 管理员

权限表

    资源权限







阶段成绩表

    javase   javaweb   html&css&js    mysql     ssm 
    
    ![image-20210521085103036](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20210521085103036.png)

试题表

	![image-20210521085112676](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20210521085112676.png)

试卷表

​	

![image-20210521085122861](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20210521085122861.png)

试卷试题中间表

![image-20210521085825901](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20210521085825901.png)





学生答卷表

![image-20210521085858552](https://gllspictures.oss-cn-beijing.aliyuncs.com/img/image-20210521085858552.png)







物料表

	学习资源表 



~~~sql
/*
SQLyog Ultimate v11.33 (64 bit)
MySQL - 5.7.15 : Database - glls_edu
*********************************************************************
*/


/*!40101 SET NAMES utf8 */;

/*!40101 SET SQL_MODE=''*/;

/*!40014 SET @OLD_UNIQUE_CHECKS=@@UNIQUE_CHECKS, UNIQUE_CHECKS=0 */;
/*!40014 SET @OLD_FOREIGN_KEY_CHECKS=@@FOREIGN_KEY_CHECKS, FOREIGN_KEY_CHECKS=0 */;
/*!40101 SET @OLD_SQL_MODE=@@SQL_MODE, SQL_MODE='NO_AUTO_VALUE_ON_ZERO' */;
/*!40111 SET @OLD_SQL_NOTES=@@SQL_NOTES, SQL_NOTES=0 */;
CREATE DATABASE /*!32312 IF NOT EXISTS*/`glls_edu` /*!40100 DEFAULT CHARACTER SET utf8 */;

USE `glls_edu`;

/*Table structure for table `t_answerpage` */

DROP TABLE IF EXISTS `t_answerpage`;

CREATE TABLE `t_answerpage` (
  `answerPageId` int(11) NOT NULL AUTO_INCREMENT COMMENT '学生答卷id',
  `pageId` int(11) DEFAULT NULL COMMENT '试卷id',
  `userId` int(11) DEFAULT NULL COMMENT '学生id',
  `answers` varchar(2000) DEFAULT NULL COMMENT '学生回答答案',
  PRIMARY KEY (`answerPageId`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8;

/*Data for the table `t_answerpage` */

/*Table structure for table `t_page` */

DROP TABLE IF EXISTS `t_page`;

CREATE TABLE `t_page` (
  `pageId` int(11) NOT NULL AUTO_INCREMENT COMMENT '试卷id',
  `pageName` varchar(32) DEFAULT NULL COMMENT '试卷名称',
  `create_time` datetime DEFAULT NULL COMMENT '创建日期',
  `update_time` datetime DEFAULT NULL COMMENT '修改日期',
  `deleted` int(11) DEFAULT NULL COMMENT '逻辑删除字段',
  PRIMARY KEY (`pageId`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8;

/*Data for the table `t_page` */

/*Table structure for table `t_page_question` */

DROP TABLE IF EXISTS `t_page_question`;

CREATE TABLE `t_page_question` (
  `tpqId` int(11) NOT NULL AUTO_INCREMENT COMMENT '试卷试题中间表id',
  `pageId` int(11) DEFAULT NULL COMMENT '试卷id',
  `questionId` int(11) DEFAULT NULL COMMENT '试题id',
  PRIMARY KEY (`tpqId`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8;

/*Data for the table `t_page_question` */

/*Table structure for table `t_question` */

DROP TABLE IF EXISTS `t_question`;

CREATE TABLE `t_question` (
  `questionId` int(11) NOT NULL AUTO_INCREMENT COMMENT '试题编号',
  `question` varchar(300) DEFAULT NULL COMMENT '试题内容',
  `partId` int(11) DEFAULT NULL COMMENT '试题阶段',
  `answer` varchar(1000) DEFAULT NULL COMMENT '试题答案',
  `fromTeacher` int(11) DEFAULT NULL COMMENT '出题人id',
  `create_tiem` datetime DEFAULT NULL COMMENT '题目创建时间',
  `update_time` datetime DEFAULT NULL COMMENT '题目修改时间',
  PRIMARY KEY (`questionId`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8;

/*Data for the table `t_question` */

/*Table structure for table `t_role` */

DROP TABLE IF EXISTS `t_role`;

CREATE TABLE `t_role` (
  `roleId` int(11) NOT NULL AUTO_INCREMENT COMMENT '角色id',
  `roleName` varchar(20) DEFAULT NULL COMMENT '角色名称',
  PRIMARY KEY (`roleId`)
) ENGINE=InnoDB AUTO_INCREMENT=4 DEFAULT CHARSET=utf8;

/*Data for the table `t_role` */

insert  into `t_role`(`roleId`,`roleName`) values (1,'admin'),(2,'teacher'),(3,'student');

/*Table structure for table `t_score` */

DROP TABLE IF EXISTS `t_score`;

CREATE TABLE `t_score` (
  `partId` int(11) NOT NULL AUTO_INCREMENT COMMENT '阶段编号',
  `score` int(11) DEFAULT NULL COMMENT '阶段成绩',
  `partName` varchar(32) DEFAULT NULL COMMENT '阶段名称',
  `userId` int(11) DEFAULT NULL COMMENT '学员id',
  `pageId` int(11) DEFAULT NULL COMMENT '试卷id',
  `partTeacherId` int(11) DEFAULT NULL COMMENT '阶段老师',
  PRIMARY KEY (`partId`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8;

/*Data for the table `t_score` */

/*Table structure for table `t_user` */

DROP TABLE IF EXISTS `t_user`;

CREATE TABLE `t_user` (
  `userId` int(11) NOT NULL AUTO_INCREMENT COMMENT '用户唯一标识主键',
  `username` varchar(32) DEFAULT NULL COMMENT '登录名唯一约束',
  `realname` varchar(32) DEFAULT NULL COMMENT '真实姓名',
  `password` varchar(50) DEFAULT NULL COMMENT '登录密码',
  `email` varchar(50) DEFAULT NULL COMMENT '邮箱',
  `sex` varchar(5) DEFAULT NULL COMMENT '性别',
  `address` varchar(32) DEFAULT NULL COMMENT '家庭住址',
  `school` varchar(32) DEFAULT NULL COMMENT '毕业院校',
  `hobby` varchar(50) DEFAULT NULL COMMENT '爱好',
  `knowmyself` varchar(500) DEFAULT NULL COMMENT '自我认知评价',
  `phone` varchar(32) DEFAULT NULL COMMENT '手机号码',
  `create_time` datetime DEFAULT NULL COMMENT '创建时间',
  `update_time` datetime DEFAULT NULL COMMENT '更新时间',
  `deleted` int(11) DEFAULT NULL COMMENT '逻辑删除字段',
  `birthday` date DEFAULT NULL COMMENT '生日',
  `picture` varchar(200) DEFAULT NULL COMMENT '头像',
  `rid` int(11) DEFAULT NULL COMMENT '角色id',
  PRIMARY KEY (`userId`)
) ENGINE=InnoDB AUTO_INCREMENT=6 DEFAULT CHARSET=utf8;

/*Data for the table `t_user` */

insert  into `t_user`(`userId`,`username`,`realname`,`password`,`email`,`sex`,`address`,`school`,`hobby`,`knowmyself`,`phone`,`create_time`,`update_time`,`deleted`,`birthday`,`picture`,`rid`) values (1,'miaoshunyu','苗顺宇','1234','123@qq.com','男',NULL,NULL,NULL,NULL,NULL,NULL,NULL,0,NULL,NULL,3),(2,'zhangshuai','张帅',NULL,'2222@qq.com','男',NULL,NULL,NULL,NULL,NULL,'2021-05-20 15:24:40','2021-05-20 15:24:40',0,NULL,NULL,3),(3,'wangmingyuan','王铭远',NULL,'123@163.com','男',NULL,NULL,NULL,NULL,NULL,'2021-05-20 16:01:12','2021-05-20 16:01:12',0,NULL,NULL,3),(4,'liuyanli','刘艳丽',NULL,'2222@163.com','女',NULL,NULL,NULL,NULL,NULL,'2021-05-20 16:02:32','2021-05-20 16:02:32',0,NULL,NULL,3),(5,'admin','glls','admin','524840158@qq.com','男',NULL,NULL,NULL,NULL,NULL,NULL,NULL,0,NULL,NULL,NULL);

/*!40101 SET SQL_MODE=@OLD_SQL_MODE */;
/*!40014 SET FOREIGN_KEY_CHECKS=@OLD_FOREIGN_KEY_CHECKS */;
/*!40014 SET UNIQUE_CHECKS=@OLD_UNIQUE_CHECKS */;
/*!40111 SET SQL_NOTES=@OLD_SQL_NOTES */;

~~~







# 补充：

  



~~~shell

~~~




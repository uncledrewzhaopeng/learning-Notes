### Vue是渐进式的javascript框架

> Vue最大特点：数据驱动视图
>
>    虚拟DOM：虚拟DOM就是一个真实的JS对象，操作JS中的内存要比直接操作DOM的速度要快。 



### MVVM框架

-   M：model层  数据层  数据的增删改查
-   V：view层  类似于HTML一个的模板     
-   VM：viewModel映射层  控制model层与view层之间的一个逻辑层   



### Vue对象

> el：代表Vue作用的范围。

- data：{ }  当前Vue所需要的一些属性。（当前组件所需要的一些状态。）
- methods：{ }  用来存放Vue所需要的函数。（当前组件所需要的函数）
- computed:计算属性   通过属性计算而得来的属性,场景:当一个属性受多个属性影响的时候就需要用到computed  最典型例子：购物车商品结算的时候 

```javascript
computed内部函数调用的时候不需要加（）

computed是依赖VM中data的属性变化而变化的，也就是说，当data中的属性发生改变时，当前函数才会执行，如果data中的属性没有发生改变，当前函数不会执行

computed中函数必须用return返回最终的结果

在computed中尽量不要去修改data中的属性值，简单来说就是不要在computed中对data的属性做赋值操作 

在computed中函数所依赖的属性如果没有发生改变的时候，那么调用当前函数的时候结果会从缓存中读取       
```

-   watch：属性监听  监听属性的变化  场景：当一条数据影响到多条数据的时候用到watch。 比如：搜索框   

```javascript
watch中函数名称是data中的属性名称，因为watch也是依赖data中的属性，当data中的属性发生改变的时候，watch中的函数就会执行。

watch中函数都有2个参数，一个是新的值，一个是旧的值   

watch中的函数是不需要调用的   

watch只会监听数据的值是否发生改变，而不会监听数据的地址是否发生变化,如果需要监听对象的变化的时候，需要进行深度监听  deep+handler   
 
特殊情况下，watch是监听不到数组变化的，例如数据的修改  通过length来清空数组 

如果想要检测到数组的变化，需要用到splice 或者$set

immediate用来做页面首次加载的时候做一次监听

this.$set() 参数1：目标元素  参数2：属性名称/数组下标   参数3：value值   
this.$delete()  参数1：目标元素  参数2：属性名称/数组下标 
```

- filter：过滤器，过滤数据。

```
全局过滤器：vue.filter()    
局部过滤器：filter()
参数1：过滤器的名称   参数2：过滤器实现的函数
如何使用：过滤器的使用通过管道符进行使用  |
	语法：数据 |  过滤器（需要传递的参数）
	过滤器中的参数是需要过滤的数据以及传递过来的参数
```



### Vue常用的指令

> v-text： 值为data中的数据，底层原理是应用的innerText 

    解析data中的数据，解析JS的表达式
    简写{{}}

> v-html：值为data中的数据，底层原理是应用的innerText  

    解析data中的数据，解析JS的表达式，可以解析html

> v-show：显示/隐藏   场景：展示页面，类似于一些选项卡等

    当值为true的时候为显示，false的时候为隐藏，底层原理是操作元素的display属性 

> v-if：  显示/隐藏   场景：权限校验的时候

    当值为true的时候为显示，false的时候为隐藏，底层原理是操作元素的创建/销毁        
    配合v-if使用的指令：v-else，v-else-if，使用这两者的时候必须使用v-if 

> v-bind：用来给元素绑定的属性   语法：  v-bind：属性 = 属性值  简写：就是一个冒号（ ：）            
> 常用的属性：src,title,alt,href,type,class,id                  

    :src=""  :title="" :href="" :id="" :type=""  :alt=""    
    :class=""   myclass:"box box1" 
    myclass1:["box2","box3"]  
    myclass2:{boxA:true,boxB:false}

> v-for:遍历  可以用来遍历任何对象（数组，字符串，对象,数字....）            

    <div v-for="(item,index) in obj/5/qianfeng/arr">{{item}}-----{{index}}</div> 

> v-on：事件绑定  语法: v-on：事件名称 = 事件函数   

    底层原理：用的是Object.defindProperty（）来做数据的劫持           
    简写：@事件名称  
    methods:{ } 用来存放Vue所需要的函数（当前组件所需要的函数） 
    修饰符之作用：修饰指令  修饰符之语法： 指令.修饰符.修饰符.... 
        stop：阻止冒泡  
        prevent：阻止浏览器默认事件                            
        enter：按下回车  
        once：事件只绑定一次
    事件对象：如果需要使用事件对象的情况下只需要给函数传递一个$event即可

> v-pre：作用是不解析html

> v-cloak：作用是防止{{}}在vue.js没有加载进来的时候显示

> v-once：数据只解析一次

> v-model:双数据绑定  可以直接修改data中的属性值，当数据发生改变时视图也会发生改变 
>  只能应用到form表单身上，其他元素无法使用
> 修饰符：number  代表输入框里面的值是一个数字类型的       

```javascript
底层原理：通过Object.defindProperty来实现
	在vue3.0中，将object.defindProperty替换成了proxy，通过data中的每一个属性加一个数据劫持（给每一个属性加了一个setter/getter方法） 
```
> v-directive：自定义指令  自定义指令必须在实例化之前

     全局自定义指令：vue.direvtive            
     局部自定义指令：directives
     语法：vue.directive（指令名称，指令实现的函数）
           第一个参数：使用指令的DOM元素
           第二个参数：是一个对象，对象中的modifiers代表的是修饰符，对象中的value值是表达式的结果



### vue实例方法

- vm.$mount  组件外部挂载

- vm.$destory  组件销毁   将vm与视图之间的关联断开。

- vm.$forceupdate  强制更新  当属性身上没有getter/setter方法到时候通过forceUpdate进行手动调用render函数的方式进行更新，因为是手动更新，因此使用的时候要注意，因为会浪费性能。                               

- vm.$on   事件的订阅   参数1：事件名称  参数2：事件函数

- vm.$once  事件的订阅  参数1：事件名称  参数2：事件函数

- vm.$off  事件的解绑   参数1：事件名称  参数2：[事件函数] 如果存在解绑对应事件，不存在则解绑所有 

- vm.$emit  事件的触发  参数1：事件名称  参数2：[需要传递的参数]



### vue生命周期(一个组件从创建到销毁的过程叫做生命周期)

> beforeCreate：创建前   

- 当组件初始化时，会执行beforeCreate，在当前生命周期中无法访问data中的属性和methods中的方法，因为当前生命周期是初始化阶段，因此我们可以在当前生命周期中加一个loading等待组件加载完毕以后再移除loading。 

> create：创建后

- 当前生命周期可以执行访问到data中当属性以及methods身上的方法。
- 当前生命周期执行的时候会将data身上的所有属性遍历添加getter/setter方法。 
-  当前生命周期执行的时候会将data与methods身上的属性和方法遍历到vm的实例身上。 
-  因为当前生命周期会遍历data身上的属性添加getter/setter，因此我们可以在当前生命周期函数中进行前后端数据的交互。 

> beforeMount：挂载前
>    

- 当前生命周期是数据和模板还未进行相结合，我们可以在当前生命周期中做数据最后的更改。

> mounted：挂载后

- 当前生命周期是数据和模板进行结合，我们可以在当前生命周期中获取到真实的DOM结构。（我们可以在当前生命周期中做方法的实例化，例如swiper，    echarts...） 

> 如何获取到真实的DOM结构？ 

    通过给元素添加ref属性（在mounted中通过this.$refs.属性即可获取。）

> beforeUpdate：更新前

- 在当前生命周期中更新的数据和模板还未进行结合，因此我们还可以对更新的数据做最后的修改。

> updated:更新后

- 更新的数据和模板进行结合，在当前生命周期中我们可以获取到数据更新后最新的DOM结构。 

> beforeDestory：销毁前

- 在当前生命周期中我们仍然可以获取到真实的DOM结构，因此我们可以做事件的移除，事件的解绑等。

> Destory：销毁后

- 在当前生命周期中我们访问不到真实的DOM结构了，以及当前vm与页面之间的关联也断开了。 

**注意！！！：beforeUpdate与updated这两个生命周期会多次执行，因此在这两个生命周期中做逻辑操作的时候一定要加条件处理，否则会极度浪费性能。 **



### vue组件： HTML，CSS，JS   灵活、复用、便于维护

> 页面上任何一个部分都是一个组件。 .vue文件就是单文件。

    组件的创建方式：
    vue.component()  全局组件，任何vm都可以使用
    components:{}   局部组件，只能局部使用
    	参数1: 组件名称  
    	参数2：组建的配置项
    	（这个配置项中，vue的配置项中有什么这里面的配置项就有什么,生命周期也会有,可以理解为小型的vue实例,唯一           不同的是当前的配置项中的data不在是一个对象，而是一个函数，返回一个对象。)                                 template:类似于Html模板，用来写组件的结果

**组件关系：父子关系，非父子关系**
**组件传值：父传子、子传父、非父子**

#### 父传子

    传递：当子组件在父组件中当做标签使用的时候，给当前子组件绑定一个自定义属性，值为需要传递的数据 
    接收：在子组件内部通过props属性来进行接收，props接收的方式有两种，一种为数组，另一种为对象。 
    1. 数组接收：
    	props：[自定义属性]
    2. 对象接收：
    	props：{
    		自定义属性：{
                type：限制外部数据的类型
                default：默认值 当父组件没有给子组件传值的时候用默认值
                required：当前属性是必须传的值
        	}
        }
#### 子传父

    1. 当子组件在父组件当做标签使用的时候，给当前子组件绑定一个自定义方法，值为接收参数的函数(这个函数不可以加（）），在子组件内部通过this.$emit来调用自定义方法，值通过函数进行传递。 
    2. 插槽作用域

#### 非父子

    1. 在vue的原型上加一个公共方法即可(只需要能让组件拥有共同的$on $emit就可以实现非父子组件传值) 
    	a、给原型上添加一个公共的vue实例
    	b、添加一个observer（手动封装的事件订阅）  
    2. 添加一个observer（手动封装的事件订阅）
    3. Eventbus
    4. vuex

#### 动态组件

> 场景：选项卡、商品列表

    通过动态切换is属性来显示不同的页面，动态组件是vue中的一个内置组件<component is=""></component>,is属性的值是哪个组件，哪个组件显示，当前组件的切换不涉及到路由的时候就可以用动态组件。

#### keep-alive

> 场景：数据的筛选、滚动条的位置、信息的填写 

    这是vue中的一个内置组件，作用是凡是被它包裹的组件，第一次被创建后就会保存在内存当中，不会经历销毁，下次进行页面切换的时候就会从缓存中读取      
    使用的方式：只需要将它包裹住切换的组件即可
    属性：	include：哪些组件需要被缓存（字符串、正则）
           exclude：哪些组件不需要被缓存（字符串、正则）
           max：最多能被缓存多少个组件（number）
    被keep-alive包裹住的组件会新增两个生命周期:
        activated：活跃状态   
        deactivated：缓存状态

> scoped：可以让每个组件的样式私有化，简单的来说就是让每个组件的类名唯一化 .

> 拦截器:  当数据发送到服务器之前以及数据响应到客户端之前的一次拦截就叫做拦截器.

#### 插槽

> 默认情况下，组件标签内部嵌套的标签或者组件默认是不显示的，如果需要进行显示就需要用到插槽。
>
> 作用:可以在封装组件的时候让组件更加的灵活。

```js
匿名插槽：
	a、在组件标签内部书写template标签，需要嵌套的内容放在template标签内部，同时给template标签加一个指令 v-slot
	b、在组件内部通过<slot></slot>进行接收嵌套的数据

命名插槽： 
	a、在组件标签内部书写template标签，需要嵌套的内容放在template标签内部，同时给template标签加一个指令v-slot：插槽名称
	b、在组件内部通过<slot name=''插槽名称></slot>进行接收嵌套的数据。 

作用域插槽：带参数的插槽
	a、在组件内部通过给<slot></slot>绑定自定义属性
	b、在父组件中给子组件标签的template标签添加一个属性
          <组件>
             <template v-slot:插槽名称='props'>
                 <标签>{{props.自定义数组}}</标签>
             </template>
          </组件>
```

### vue动画

```js
transition：内置组件   
	作用：包裹需要进行动画的元素
	特点：被包裹的元素必须经历显示和隐藏（v-if || v-show）
	transition身上有一个属性，这个属性是name，就是动画名称。

动画：
	一部分叫入场动画（入场的开始阶段 enter、入场的进行时阶段 enter-active、入场的结束阶段 enter-to）
	另一部分叫出场动画（出场的开始阶段 leave、出场的进行时阶段 leave-active、出场的结束阶段 leave-to）
动画的六个类名：
	<name>-enter
	<name>-enter-active
	<name>-enter-to
    <name>-leave
    <name>-leave-active
    <name>-leave-to 

当使用第三方动画库的时候，
	transiton 提供了六个属性：
	enter-class
	enter-active-class
	enter-to-class
    leave-class
    leave-active-class
    leave-to-class

当多个元素使用同一个动画的时候需要将transition标签换成transition-group,并在每一个子元素身上加一个key值。
```

### 路由

- 根据用户请求地址的不同返回不同数据/页面
- 前端路由：根据用户请求的地址渲染不同的页面，前端路由不会经过后端，而是根据哈希值的变化来进行数据的渲染，一般情况下前端路由都用做单页面的开发（SPA）。
- 前端路由分为两个：
  1. hashRouter（onhashChange）url路径上带#，不需要后端配置的 
  2. history路由（hshistoryAPI） url路径上不带#，使用的时候需要后端的配置（ 优点：用户体验更好一些   缺点：不利于SEO优化）


    routers：路由配置的一些规则，是一个数组，数组中的每一个对象都是一个路由的配置项。
    当路由配置成功以后，vueRouter会提供2个内置组件用来做组件的显示。
    	<router-view></router-view> 当前组件是用来做路由展示的。
    	<router-link></routr-link> 当前组件是用来做路由跳转的。 属性：to：指定跳转的路径。tag：将router-link渲染成指定的标签。
    
    路由配置项：
    	path：路由匹配的路径
    	component：当path的路由匹配成功以后就 会显示对应的组件
    	children：路由嵌套，可以理解成是一个小型的routers，值是一个数组，数组中的每一个对象就是一个二级路由的配置项。
    二级路由的配置项属性和一级的路由配置项属性是一致，注意path不要加/
    	name：命名路由
    	meta：路由信息 每个路由身上携带的信息
        props：路由解耦：针对动态路由
            a、在定义路由的时候通过 /: 属性  /: 属性来定义传递的属性
            b、在定义路由的时候需要配置一个属性props：true
            c、在路由跳转的时候通过/值，/ 值将数据传递到对应的组件中去    
            d、在对应组件内部通过props进行数据的接收 
    	redirect：重定向
     
    路由传值
    动态路由: 
        a、在定义路由的时候通过 /： 属性 /: 属性定义传递的属性
        b、在路由跳转的时候通过 / 值，/ 值将数据传递到对应的组件中去。
        c、在对应的组件内部通过this.$route.params进行数据的接收
    query传值：
        a、query传值其实就是get提交数据的形式，进行url的数据拼接。
        b、接收的时候通过this.$router.query进行接收
                     	
    动态路由传值和query传值的区别:前者路由跳转的时候参数是必须传递的，如果不传递则相对应得页面不会显示。而后者的参数是非必须传递的。



### 编程式导航

>  $route和$router的区别：前者是当前路由的一些信息，例如跳转的路径以及携带的参数等；后者是路由的实例化对象，里面有我们需要的一些方法，例如编程式导航的跳转等。

```js
this.$router.push()   // 跳转到任何页面
this.$router.back()   // 跳转到前一个页面
this.$router.forward()  // 跳转到下一个页面
this.$router.replace()  // 跳转到替换
this.$router.go()     // 指定跳转
```

### 路由守卫

> 路由钩子函数   路由跳转前后的一些验证

```js
全局守卫：beforeEach
局部守卫：
	beforeRouteEnter    进入路由前的守卫（在当前路由钩子函数中是访问不到this的） （热力图、登录的验证、权限验证、消息通知）
	beforeRouteUpdate   路由更新时的守卫（当前路由发生改变的时候，而当前组件没有经历创建和销毁的时候我们就需要用到了beforeRouteUpdate）    （未支付、未保存、答题系统、退出登录）

除此之外我们还可以通过watch来监听$route的变化也能达到同样的效果。
	beforeRouteLeave    路由离开时的守卫（）
路由守卫的参数：
	to：到哪个路由
	from：从哪个路由来
	next：进入路由
to和from就相当于一个$route,这里面都是当前路由的信息。       
```

### 路由懒加载
> 1、异步组件的方式   
>
> 2、ES6 import方式        



### vuex

> 公共状态管理模式（最好的非父子组件传值方案）                                                        

      1、cnpm install vuex -S
      2、引入vue
      3、引入vuex
      4、vue.use（vuex）
      
    vuex常用的5个属性：
    a、state：用来存储公共的状态
    	辅助函数：mapState
    书写方式： 	
    1> 数组 computed：mapState（["n"]） （括号里写数据）
    2> 对象 
        computed：{
        	...mapStated({
        		n:state=>state.n 
        		})
        	}       
                       
    b、actions：用来处理异步的数据，并且用来触发mutations中的方法
    actions中的每一个方法都会有两个参数，一个参数是对象，对象中有一个commit方法用来触发mutations中的方法，另外一个参数是选填的，是需要传递的参数。
    	辅助函数：mapActions
    使用方式：  
    1> 数组 methods：mapActions{["handleAddActions"]}
    2> 对象 methods：{
    		...mapActions({
    			handleAddActions:"handleAddActions"
    		})
    	}
    
    c、mutations  用来修改state中数据，mutations里面的方法有两个参数  
    	参数一：state   
    	参数二：commit携带过来的参数
    	辅助函数： mapMutations  mapMutations来使用Vuex中的方法时，需要在methods中进行解构
    写法：  
    1> mapMutations（[""]）  
    2> ...mapMUtations（{ handleAddMutation:"handleAddMutations"}）  
                                                                                                         
    d、getters: 属性计算  类似于组件中computed，与computed有同样的功能
    getters主要依赖state中属性，当state中的属性发生变化的时候，getters中的方法就会被触发
    	辅助函数：mapGetter
    写法：  
    1> 数组：methods: mapGetters(["handleAddActions"])
    2> 对象: methods: {
    			...mapGetters({
    				handleAddActions:"handleAddActions"
    			})
    		}
                                                                                                         e、modules：公共状态数据模块化   
    每一个小的模块都是一个小型的vuex，小模块中也会有state、getter、mutations、actions
    当导出子模块的时候切记加一个namespaced：true作用是可以使当时模块的数据私有化     
    
    注意：如果通过mapActions   mapMutations来使用vuex中的方法时，需要在methods中进行解构  
    如果通过mapState   mapGetters来使用vuex中的方法时，需要在computed中进行解构 



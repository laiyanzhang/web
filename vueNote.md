# vue note

标签（空格分隔）： vue

## 1.vue grammer

 - el、data、method、computed、watch、component、mixins、mounted
 - data采用return返回值避免变量污染
 - v-html
 - v-bind(:)
 - v-if
 - v-model
 - v-on(@)
 - v-if
 - v-else
 - v-else-if
 - v-for(value,key,index)
 - v-show
 - filter:{{a|b}}--b(a)
 - js中调用属性$与非vue对象变量区分
 
## 2.computed
 - 默认为函数名，函数名内可设置setter、getter，当js中对computed进行改变时调用setter
 - computed与method的差别：
   - 调用差别：method需要(),computed调用属性名
   - 执行差别：在vue对象没有作出改变的情况下，computed属性经过第一次执行后不再执行;method会伴随着调用不断执行。

## 3.watch
- vue对象内的属性监听，与v-model结合使用，函数名为属性名，参数为变化值
- 通过watch可以进行data内数据的互相影响

## 4.bind
- data内的值之间不可相互调用，可以通过watch方法进行data内数据互相赋值

## 5.on
- 点击触发methos内对应函数
- 事件修饰符
  - v-on:click.
  - stop：阻止点击子元素产生父元素的冒泡
  - prevent：阻止默认时间发生，如阻止表单提交并执行函数内程序
  - capture：冒泡时优先捕捉，然后再进行从内到外冒泡，同时存在capture时由外到内
  - native：将组件转化为普通html标签，从而可以实现事件触发
- 按键修饰符
  - v-on:keyup.
  - 控件内使用按键触发相应事件

## 6.表单
- 复选框与v-model结合：
  - 单个复选框结合boolean值
  - 多个复选框结合数组值
- 单选按钮与v-model结合
  - 每个单选按钮v-model均与data结合，被选中的按钮的value值与data结合。
- 下拉列表与v-model结合
  - select标签v-model与data结合，被选中的option的value值与data结合
- 修饰符
  - v-model.修饰符
  - .lazy:发生更新的是change时间而不是input时间
  - .number:将input内的值转化为数字写入data中
  - .trim:过滤输入的首尾空格

## 7.component
- 定义：tagname，option
- option：
  - template：近似于子元素
  - props（[]）：接受父元素数据（单向绑定），数据以数据形式存储
  - props（{}）：接受父元素数据的同时进行数据类型验证，数据以字典形式存储
  - data:类似于vue的data
  - methods：子元素触发该方法（$emit）从而触发父元素的事件，$emit(event,data)
  - model:默认值：prop:'value'，event:'input',可根据需要修改prop与event，使用：
    v-model="vue"
    props：传入的值（值：类型）
    model：根据需求修改prop与event
    v-bind:prop="prop"
    v-on:event="(&cent;emit('event',$event.target.prop)"
    子组件的值与事件传入父组件中

## 8.directive
- v-directive
- 不适用钩子函数时完全适用js表达式
- 钩子函数：
  - bind：绑定到元素时调用，只调用一次
  - inserted：被绑定元素插入父节点时调用
  - update：被绑定元素所在模板更新时调用
  - componentUpdated：被绑定元素完成更新调用
  - unbind：解绑时调用，只调用一次
- 钩子参数：
  - el：被绑定元素
  - binding
    name：指令名
    value：绑定值
    oldVaule：绑定前一个值
    expression：绑定值的表达式或变量名
    arg：传给指令的参数：v-directive:arg
    modifiers：修饰符对象：v-directive:foo.bar {foo:true,bar:true}
  - vonde：编译生成的虚拟结点
  - oldVnode：上一个虚拟结点

## 9.transition
- 概念：淡入淡出过程，相对于transition，enter为淡入过程，leave为淡出过程，-to结束状态
- transition内可自定义类，自定义类优先级高于定义duration
- v-on：before-enter、enter、after-enter、enter-cancelled

## 10.mixins
- 选项合并：组件与混入对象含有同名选项时进行合并，两者都执行，组件数据优先
- method选项中相同函数名：vue实例优先级高，仅执行vue内函数

## 11.ajax
- vue的mounted属性
- 使用axios完成ajax同步请求
- axios.get().then().catch();
- axios.post().then().catch();
- 并发请求：axios.all([x(),y()]).then(axios.spread(function(acct,perms)
- 配置请求：axios(config)、axios(url[,config])发送请求,axios.create([config])建立对象后需要再配置相关信息才能发送请求
- 配置默认值：axios.default.data,配置优先顺序：config配置参数，default默认值，库内默认值
- 拦截器：axios.interceptor.request/response.use(function(config),function(error):发送请求前、错误后
- get（）内可配置validateStatus定义状态码错误范围
- 异步加载：methods的方法：this.&cent;http.get(url,option),this.$http.post(url,body,option)
- 异步全局对象：Vue.http.get()
- option:url、body、headers、params、method、timeout、before、progress、credentials、emulateHTTP、emulateJSON


## 12.响应接口
- vue不允许在已经创建的实例上动态增加新的根级响应属性
- vm.data.newdata="num":增加属性不可使用get、set方法
- vue实例外：Vue.set(vm.obj,'data',num)；vue实例内this.$set(this.obj,'data',num),属性可使用get、set方法
- Vue.delete()删除对应属性


   

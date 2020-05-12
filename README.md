# qianduan

前端代码库
vue 的学习使用 vue 全家桶：vue.js+ vue.cli + vuex +vue-touter + asiox
vue 和 react 的区别？
答：vue 属于配置型的框架，配置的选项都是内只固定的，也就是说 vue 的学习就是框架的配置熟悉过程，而且是一个渐进型（可以有很多选项但是这些选项都是可配置、可选的）的框架。所以 vue 的学习和使用模式相对来说固定的（也就是好学），相对来说发挥空间小。
react 强调的是动手能力更多，不是配置性的，要求少，结构没有 vue 那么牢固和紧凑，也就是说开发者可发挥得空间比较大自由度比较高。
vue 适合开发小项目 react 适合开发中大项目

vue 中 innerText:{{}} innerHtml:v-html
属性（特征）v-bind 或：
事件：v-on 或@
实例 class：v-bind； :class="{class:boolean 值}"
style： v-bind :style="对象

vue 计算属性和方法的区别
计算属性是一种特殊的属性，它不是方法
1、使用上的区别，计算属性不需要加圆括号调用，方法需要
2、计算属性和方法的写法基本一致，但是计算属性内部务必要有 return 返回值
3、计算属性有缓存，方法没有，也就是说计算属性是依赖现有属性的，属性变化后计算属性才重新求值，否则使用缓存，方法每次调用都会返回计算
4、计算属性是依赖属性的 方法未必
5、方法名和计算属性不要重名，否则计算属性名称被覆盖

watch 监听的都是 data 中定义的属性
template 一般用于控制语句：条件或循环，但是不能在 template 上使用 key
vue 生命周期
beforecreate 在 beforecreate 中无法得到当前 vue 实例的属性和方法，因为此时还未完成生命周期和属性、事件的初始化
created 完成了编译工作 但是还没有完成挂载，也就是说此时无法使用\$el
beforemount 挂载
mounted
beforeupdate 更新
updated
beforedestroy 销毁
destroyed

组件可以认为是一个 vue 的是列。组件是一个可复用的 vue 实例
new Vue 创建的实例为根实例，一般在一个 vue 项目中只有一个根实例
全局注册组件：
注意事项：
1、必须写在根实例前
2、组件的名字：不要有任何字母的大写，使用小写或连字符（-）的写法，不要和 html 的关键字，保留字冲突
3、不能在组件中使用 el 挂载元素，组件中应该使用 template 来渲染和加载
4、组建的 template 模板需要遵循单个根元素的规则
重要：！！！组件可复用，组件是一个自成一体的实例内容（组件内部的 methods，data 等操作都是为自己的 template 服务的，无法对外服务）

vue 传值之父子传值--属性传值
注意：
1、props 和 data 中定义的属性不要重名
2、props 的属性是只读的，data 中定义的属性是可读可写的
vue 子给父传值
v-on：back 所监听的事件名称 back，必须和 this.\$emit('自定义事件','传递的值')

vue 插槽
为什么使用插槽？
插槽可以赋予组件更大的灵活性和定制型

非 props 属性
非 props 属性指的是在组件中传递了属性，但是组件内部并没有定义 props 接受该属性的情况，比如下面的 id 和 class；这些非 props 属性会显示到模板的顶级元素上
有 props 接受的属性不会显示到模板的顶级元素

属性替换和合并的意思实在组件上指定了一些属性，最终这些属性会和组建的 template 模板顶级元素做合并或替换，策略是 class 和 style 属性做合并，其他属性替换

inheritAttrs：false 禁用属性继承， 禁用后 class 仍然会合并

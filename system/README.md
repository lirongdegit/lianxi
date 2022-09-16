# system

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).



## vue封装的过度与动画
1.作用：在插入，更新或移除DOM元素时，在合适的时候给元素添加样式类名。

   2.
  1.要准备好样式
     元素进入的样式  v-enter:进入的起点 v-enter-active 进入过程
     v-enter-to 进入的终点

     离开的样式：v-leave v-leave-active v-leave-to

2.使用<transition>包裹要过渡的元素，并配置name属性。
 <transition name="hello" appear>
      <h1 v-show="isShow">你好啊</h1>
     </transition>


3.若多个元素需要过度，则需要，且每个元素要指定key值。
 <transition-group 
     appear
     name="animate__animated animate__bounce" 
     enter-active-class="animate__backInDown"
     leave-active-class="animate__fadeOutUp"
     >
      <h1 v-show="!isShow" key="1">你好啊</h1>
      <h1 v-show="isShow" key="2">李蓉</h1>
 </transition-group >



VUE脚手架配置代理解决跨域问题

1.在vue.config.js添加如下配置
devServer:{
     proxy:"http://localhost:5000"
}
说明：
1.优点：配置简单，请求资源时直接发给前端即可。
2.缺点：不能配置多个代理，不能灵活地控制请求是否走代理。
3.工作方式：当请求了不存在的资源，那么该请求会转发给服务器（优先匹配前端资源）


2.module.exports = {
     devServer:{
          proxy:{
               '/api1':{
                target:'http://localhost:5000',
                changeOrigin:true,
                pathRewrite:{
                    '^/api1': ''
                },

                '/api2':{
                target:'http://localhost:5000',
                changeOrigin:true,
                pathRewrite:{
                    '^/api2': ''
                }

               }
          }
     }
}

注意：请求资源的时候必须得加前缀。

插槽：作用：
1.让父组件可以向子组件指定位置插入html结构，也是一种组件间通信的方式，适用于父组件向子组件。

2.默认插槽，具名插槽，作用域插槽。
3.使用方式

1.默认插槽
父组件中   <category>
            <div>html解构</div>
          </category>

子组件中   <template>
             <div>
             <slot>默认插槽内容</slot>
           </template>   

2.具名插槽
    <category>
       <template slot="center">
          <div>html解构</div>
       </template>   

      <template v-slot="footer">
          <div>html2解构</div>
       </template>   
     
     </category>

子组件中
      <template>
         <div>
            <slot name="center">默认插槽内容</slot>
            <slot name="center">默认插槽内容</slot>
          </div>
     </template>   

3.作用于插槽
  1.理解：数据在组件的自身，但根据数据生成的结构需要组建的使用者来决定，（game数据在Catageroy组件中，但是用数据所遍历出来的结构由APP组件决定）
  2.具体编码


  vuex
  概念:专门在Vue中实现集中式状态（数据）管理的vue插件，对vue应用中多个组件的共享状态进行集中式的管理，也是一种组件间的通信方式，且适用于任意组件中的通信。

  使用场景：1、多个组件依赖于同一状态。
  2.来自不同组件的行为需要变更同一状态。   

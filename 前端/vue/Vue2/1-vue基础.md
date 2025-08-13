# vue 基础

* Vue是什么

  * Vue 是一个用于构建用户界面的渐进式框架

* Vue 使用

  1. 引入Vue
  2. 创建Vue管理的dom元素
  3. 创建Vue实例
     1. el：选择Vue管理的dom元素
     2. data：渲染数据

* ``` vue
  <!DOCTYPE html>
  <html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>初始Vue</title>
  </head>
  <body>
    <div id="app">
     <!-- 差值表达式 -->  
      {{ message }}
    </div>
  </body>
  
  <!-- <script src="https://unpkg.com/vue@3/dist/vue.global.js"></script> -->
  <script src="https://cdn.jsdelivr.net/npm/vue@2.7.16/dist/vue.js"></script>
  <script>
    const app = new Vue({
      //  通过el 配置选择器，指定Vue实例挂载的DOM元素
      el: '#app',
      // 通过data配置选渲染的数据
      data: {
        message: 'Hello Vue!'
      }
    });
  </script>
  </html>
  ```

* 差值表达式 {{}}

  * 差值表达式是一种Vue的模板语法
  * 作用：
    * 利用表达式进行差值，渲染到页面中
    * 表达式：是可以被求值的代码，js引擎会将其计算出一个结果
  * 语法{{表达式}}

* 响应式

  * 数据变化，视图自动更新
  * 访问：实例名.属性名
  * 修改：实例名.属性名 = ‘新数据’


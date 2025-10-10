# vuex

* 概述
  * vuex是一个vue的状态管理工具

* 场景
  * 某个状态在很多个组件来使用
  * 多个组件共同维护一份数据

* 优势
  * 共同维护一份数据，数据集中化管理
  * 响应式变化
  * 操作简洁

* 创建和导出仓库

  * ```JS
    import Vue from 'vue'
    import Vuex from 'vuex'
    
    Vue.use(Vuex)
    // 创建仓库
    const store = new Vuex.Store({
    
    })
    // 导出仓库
    export default store
    ```

* 核心概念 state 状态
  * 提供数据
    * State提供唯一的公共数据源，所有共享的数据都要统一放到Store中的State中存储
  * 使用数据
    * 通过store直接访问
      * 模板使用 - {{$store.state.要用的数据名}}
      * 组件逻辑中 - this.$store.state.要用的数据名
      * js模块中：store.state.要用的数据名
    * 通过辅助函数
      * mapState是辅助函数，帮助我们把store中的数据自动映射到组件的计算属性中
      * 引入mapState
        * import {mapState} from ’vuex‘
      * 使用mapState
        * 在computed中添加...mapState(['需要的仓库数据‘])

* 核心概念 - mutations 必须同步

  * 目标：明确vuex同样遵循单向数据流，组件中不能直接修改仓库的数据

  * 目标：明确vuex同样遵循单向数据流，组件中不能直接修改仓库的数据

  * 通过：strict：true 开启严格模式

    1. 定义木头mutations对象，对象中存放修改state的方法

       ```js
        mutations: {
           addCount (state) {
             state.count++
           }
         }
       ```

       

    2. 组件中提交调用muations中的方法

       ```js
        methods: {
           addCount () {
             this.$store.commit('addCount')
           }
         }
       ```

    3. mutations 提交传参

       ```js
       // 第一个参数 仓库数据，第二个参数传递过来的参数
       addCount (state, n) {
             state.count += n
           }
       // count形参
        addCount (count) {
          // 第一个参数是要调用的仓库修改函数， 第二个参数是要传递的参数
             this.$store.commit('addCount', count)
           }
       // 注意：要是想要传递多个参数，需用复杂数据类型
       ```

* 辅助函数mapMutations

  * 引入mapMutations
    * import {mapMutations} from ’vuex‘
  * 使用mapMutations
    * 在methods中添加...mapMutations(['需要的提交函数‘])

* 核心概念 - actions

  * 目标：处理异步操作
  * 注意：不能直接操作数据仓库，必须通过muations中的方法进行操作

* 辅助函数mapactions

  * 引入mapactions
    * import {mapactions} from ’vuex‘
  * 使用mapactions
    * 在methods中添加...mapactions(['需要的提交函数‘])

* 核心概念 - getters

  * 目标：类似于计算属性

* 辅助函数mapgetters

  * 引入mapgetters
    * import {mapgetters} from ’vuex‘
  * 使用mapState
    * 在computed中添加...mapgetters(['需要的仓库数据‘])

## vuex - module模块

* 在store中新建modules中新建模块文件
* 在store主文件中导入需要的模块文件在store对象中添加modules对象，并把需要的模块放入modules对象中
* 访问模块中的各种属性
  * state
    * $store.state.模块名.属性名
    * ...mapState('模块名'['属性名']) 需要开启命名空间
  * getters
    * 直接通过模块名访问$store.getters['模块名/需要的变量']
    * ...mapGetters('模块名'，['需要的变量']) 需要开启命名空间
  * Mutations
    * 注意：默认模块中的mutation和actions 会被挂载到全局，需要开启命名空间，才会挂载到子模块
    * 直接通过模块名访问$store.commit['模块名/需要的方法'，额外参数]
    * ...mapMutations('模块名'，['需要的方法']) 需要开启命名空间
  * actions
    * 注意：默认模块中的mutation和actions 会被挂载到全局，需要开启命名空间，才会挂载到子模块
    * 直接通过模块名访问$store.dispatch['模块名/需要的方法'，额外参数]
    * ...mapActions('模块名'，['需要的方法']) 需要开启命名空间

## JSON -serve 模拟后端接口  * 通过：strict：true 开启严格模式
    1. 定义mutations对象，对象中存放修改state的方法
    2. 组件中提交调用mutations
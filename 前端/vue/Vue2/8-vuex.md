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

* 核心概念 - mutations

  * 目标：明确vuex同样遵循单向数据流，组件中不能直接修改仓库的数据
  * 通过：strict：true 开启严格模式
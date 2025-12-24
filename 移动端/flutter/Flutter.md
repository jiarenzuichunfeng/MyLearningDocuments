# Flutter

## Cupertino widget ios样式

## Material component widgets 通用样式

*  热重载
	* 需要在有状态组件或无状态组件中实现
* 热重启
### MaterialApp 通过样式框架
| 属性                       | 作用                         |
| :------------------------- | ---------------------------- |
| title                      | 应用名称（系统级展示）       |
| home                       | 应用首页（初始路由）         |
| routes                     | 命名路由表（路由管理）       |
| initialRoute               | 初始路由名称（替代 home）    |
| onGenerateRoute            | 动态生成路由（处理复杂路由） |
| theme                      | 亮色主题配置                 |
| darkTheme                  | 暗黑主题配置                 |
| themeMode                  | 主题模式                     |
| locale                     | 应用本地化语言               |
| localizationsDelegates     | 本地化代理                   |
| debugShowCheckedModeBanner | 是否显示调试标签             |
| navigatorKey               | 全局导航键（跨组件导航）     |

* title 

### 脚手架 Scaffold

* SafeArea

  | 参数                        | 作用                                       | 默认值            | 常用场景                                       |
  | --------------------------- | ------------------------------------------ | ----------------- | ---------------------------------------------- |
  | `child`                     | 需要适配安全区域的子组件                   | 必传              | 页面主体、列表、表单等                         |
  | `top`                       | 是否避开顶部不安全区域（状态栏 / 刘海）    | `true`            | 不需要顶部适配时设为 `false`（如沉浸式导航栏） |
  | `bottom`                    | 是否避开底部不安全区域（小黑条 / 灵动岛）  | `true`            | 底部有自定义导航栏时可设为 `false`             |
  | `left`                      | 是否避开左侧不安全区域                     | `true`            | 仅部分异形屏（如折叠屏）需要调整               |
  | `right`                     | 是否避开右侧不安全区域                     | `true`            | 仅部分异形屏（如折叠屏）需要调整               |
  | `minimum`                   | 安全区域的最小内边距                       | `EdgeInsets.zero` | 希望内容与安全区域边界保持额外间距时使用       |
  | `maintainBottomViewPadding` | 键盘弹出时，是否保留底部安全区域的 padding | `false`           |                                                |

* Scaffold

  | 参数                         | 作用             | 常用场景                                    |
  | ---------------------------- | ---------------- | ------------------------------------------- |
  | appBar                       | 顶部导航栏       | 页面标题、返回按钮、操作按钮                |
  | body                         | 页面主体内容     | 核心布局（列表、表单、自定义组件）          |
  | floatingActionButton (FAB)   | 浮动操作按钮     | 主要操作（添加、提交、刷新等）              |
  | floatingActionButtonLocation | FAB 位置         | 调整 FAB 在页面的位置（如底部居中、右下角） |
  | bottomNavigationBar          | 底部导航栏       | 多标签页面切换（首页 / 分类 / 我的等）      |
  | drawer                       | 左侧侧边抽屉     | 个人中心、设置、菜单等                      |
  | endDrawer                    | 右侧侧边抽屉     | 筛选、更多操作（少用）                      |
  | backgroundColor              | 页面背景色       | 自定义页面整体背景                          |
  | resizeToAvoidBottomInset     | 是否避免键盘遮挡 | 表单页面（true：自动上移避开键盘）          |
  | persistentFooterButtons      | 底部持久按钮     | 固定在底部的操作按钮（如确定 / 取消）       |
  | ScaffoldMessenger            | 底部提示条       |                                             |
### 小组件
* Container 盒子
* Center 居中组件
* Padding 内间距组件
* 布局组件
  * Expanded 扩展组件
  * Column 垂直布局组件
  * Row 水平布局组件
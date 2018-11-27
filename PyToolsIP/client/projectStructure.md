# PyToolsIP项目结构
  * 整个项目主要分成两部分，其中一部分为公共基础框架，另一部分则为具体工具层。
  * 项目结构如下所示。

|—— [launcher -> 启动模块](启动页（launcher）)
|
|—— [common -> 公共基础框架](公共基础框架（common）)
|
|—— [tools -> 具体工具层](具体工具层（tools）)
|
|—— ProjectConfig.py -> 项目配置文件
|
|—— main.py -> 项目主入口


### 启动模块（launcher）
  * 该模块的主要作用是，在启动项目时，显示启动窗口，并校验项目的相关环境，以及部分资源的加载。

|—— view -> 功能视图合集
|
|—— \_load.py -> 加载入口【包括全局变量包加载及资源加载等功能】

### 公共基础框架（common）
  * 该框架主要集合公共配置、UI控件、基础组件及核心功能（如，组件绑定系统、热键管理系统、事件分发系统等功能）。
  * 以下对代码中每个模块的功能进行简要说明。

|—— behavior -> 公共组件合集
|
|—— config -> 配置模块
|
|—— core -> 核心功能模块
|	 |
|	 |—— [behaviorCore -> 组件功能模块](./common/Behavior_Core.md)
|	 |
|	 |—— [eventDispatchCore -> 事件分发功能模块](./common/Event_Dispatch_Core.md)
|	 |
|	 |—— [hotKeyCore -> 热键功能模块](./common/Hot_Key_Core.md)
|
|—— data -> 数据处理类合集
|
|—— dialog -> 弹窗模块合集
|
|—— function -> 公共函数合集
|
|—— json -> json数据合集
|
|—— template -> 创建模板合集
|		|
|		|—— module -> 弹窗、视图、窗口、组件等模板
|		|
|		|—— createModule.py -> 创建模板入口
|
|—— ui -> 扩展控件合集
|
|—— utils -> 常用方法合集
|
|—— view -> 视图模块合集
|
|—— window -> 窗口模块合集
|
|—— \_load.py -> 加载入口【包括全局变量包加载及资源加载等功能】



### 具体工具层（tools）
  * 该层主要放置玩家下载的工具，并且确保每个工具在结构上相互独立。
  * 由于每个工具的项目结构可能不同，这里主要展示工具模板的结构（对应路径：client/template）。
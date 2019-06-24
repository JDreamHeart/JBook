# PyToolsIP项目结构
  * 项目结构如下所示。
```
|—— assets -> 资源文件
|
|—— include -> 工程依赖
|
|—— run -> 运行脚本
|
|—— template -> 工具模板
|
|—— update -> 更新目录
|
|—— depend.mod -> 依赖模块配置
|
|—— pytoolsip.py / pytoolsip.exe -> 运行入口/程序
```

## 资源文件（assets）
  * 主要放置工程脚本资源。
```
|—— common -> 公共基础框架
|
|—— launcher -> 启动模块
|
|—— ProjectConfig.py -> 项目配置文件
|
|—— build.py -> 构建项目脚本（加载依赖模块）
|
|—— main.py -> 项目主入口
```

### 启动模块（launcher）
  * 该模块的主要作用是，在启动项目时，显示启动窗口，并校验项目的相关环境，以及部分资源的加载。
```
|—— behavior -> 功能组件合集
|
|—— json -> json文件合集
|
|—— view -> 功能视图合集
|
|—— window -> 启动窗口
|
|—— _load.py -> 加载入口【包括全局变量包加载及资源加载等功能】
```

### 公共基础框架（common）
  * 该框架主要集合公共配置、UI控件、基础组件及核心功能（如，组件绑定系统、热键管理系统、事件分发系统等功能）。
  * 以下对代码中每个模块的功能进行简要说明。
```
|—— behavior -> 公共组件合集
|
|—— config -> 配置模块
|
|—— core -> 核心功能模块
|	 |
|	 |—— behaviorCore -> 组件功能模块
|	 |
|	 |—— eventDispatchCore -> 事件分发功能模块
|	 |
|	 |—— hotKeyCore -> 热键功能模块
|	 |
|	 |—— logCore -> 日志功能模块
|	 |
|	 |—— timerCore -> 定时器功能模块
|
|—— data -> 数据处理类合集
|
|—— dialog -> 弹窗模块合集
|
|—— function -> 公共函数合集
|
|—— net -> 网络层
|
|—— template -> 创建模板合集
|		|
|		|—— module -> 弹窗、视图、窗口、组件等模板
|		|
|		|—— createModule.py -> 创建模板入口
|
|—— ui -> 扩展控件合集
|
|—— view -> 视图模块合集
|
|—— window -> 窗口模块合集
|
|—— _load.py -> 加载入口【包括全局变量包加载及资源加载等功能】
```

### 工程依赖（include）
  * 该层主要放置工程所要依赖的环境，如python。
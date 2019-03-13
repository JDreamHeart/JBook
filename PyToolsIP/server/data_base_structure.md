# 数据库结构

----
## 1 user表
  * id：玩家唯一ID
  * name：玩家名
  * password：登录密码
  * email：绑定邮箱

## 2 tool表
  * id：工具唯一ID
  * uid：开发玩家的ID【外键至user的id】
  * name：工具名称
  * description：工具描述【限制在280字符以内】
  * url：工具链接地址
  * score：工具平均评分
  * download：工具下载数
  * time：工具上传时间

## 3 comment表
  * id：评论唯一ID
  * uid：玩家ID【外键至user的id】
  * tid：工具ID【外键至tool的id】
  * score：评分
  * content：评论内容【限制在280字符以内】
  * time：评论时间

## 4 collection表
  * id：收藏唯一ID
  * uid：玩家ID【外键至user的id】
  * tid：工具ID【外键至tool的id】
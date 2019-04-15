# 关于GITLAB若干权限问题

## 权限分类

权限分为访问权限和行为权限两个层次.

### 访问权限 - Visibility Level

这个是在建立项目时就需要选定的，主要用于决定哪些人可以访问此项目，包含3种

* Private - 私有，只有属于该项目成员才有原先查看
* Internal - 内部，用个Gitlab账号的人都可以clone
* Public - 公开，任何人可以clone

### 行为权限

在满足行为权限之前，必须具备访问权限（如果没有访问权限，那就无所谓行为权限了），行为权限是指对该项目进行某些操作，比如提交、创建问题、创建新分支、删除分支、创建标签、删除标签等.

## 角色

Gitlab定义了以下几个角色:

* Guest - 访客
* Reporter - 报告者; 可以理解为测试员、产品经理等，一般负责提交issue等
* Developer - 开发者; 负责开发
* Master - 主人; 一般是组长，负责对Master分支进行维护
* Owner - 拥有者; 一般是项目经理

## 权限

不同角色，拥有不同权限，下面列出Gitlab各角色权限

1. 工程权限

|行为	|Guest|	Reporter|	Developer	|Master	|Owner|
|--|--|--|--|--|--|
|创建issue|	✓	|✓	|✓	|✓	|✓|
|留言评论|	✓	|✓	|✓	|✓	|✓|
|更新代码|	| 	✓	|✓	|✓	|✓|
|下载工程|	 	|✓	|✓	|✓	|✓|
|创建代码片段|	 	|✓	|✓	|✓	|✓|
|创建合并请求|	 |	 |✓	|✓	|✓|
|创建新分支||	 | 	✓	|✓	|✓|
|提交代码到非保护分支|	 |	| 	✓|	✓|	✓|
|强制提交到非保护分支|	 |	| 	✓|	✓|	✓|
|移除非保护分支|	 |	| 	✓|	✓|	✓|
|添加tag|	 |	| 	✓|	✓|	✓|
|创建wiki|	 |	| 	✓|	✓|	✓|
|管理issue处理者|	 |	| 	✓|	✓|	✓|
|管理labels|	 |	| 	✓|	✓|	✓|
|创建里程碑	|	 |	| 	| 	 	 	✓|	✓|
|添加项目成员	|	 |	| 	| 	 	 	✓|	✓|
|提交保护分支	|	 |	| 	| 	 	 	✓|	✓|
|使能分支保护	|	 |	| 	| 	 	 	✓|	✓|
|修改/移除tag	|	 |	| 	| 	 	 	✓|	✓|
|编辑工程	|	 |	| 	| 	 	 	✓|	✓|
|添加deploy keys	|	 |	| 	| 	 	 	✓|	✓|
|配置hooks	|	 |	| 	| 	 	 	✓|	✓|
|切换visibility level	|	 |	| 	| 	 |	✓|
|切换工程namespace|	 |	| 	| 	 |	✓|
|移除工程|	 |	| 	| 	 |	✓|
|强制提交保护分支|	 |	| 	| 	 |	✓|
|移除保护分支|	 |	| 	| 	 |	✓|

PS: 关于保护分支的设置，可以进入Settings->Protected branches进行管理

2. 组权限

|行为	|Guest	|Reporter	|Developer	|Master	|Owner|
|--|--|--|--|--|--|
|浏览组	|✓	|✓	|✓	|✓	|✓|
|编辑组	 | | | ||	 	 	 	✓|
|创建项目	 | | | |	 	 	✓|	✓|
|管理组成员	| | | || 	 	 	 	✓|
|移除组	| | | || 	 	 	 	 	✓|

原文： <https://www.cnblogs.com/dzcWeb/p/8919970.html>
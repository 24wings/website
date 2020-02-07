#目录
[TOC]

---

# 插件设计

**引言**

> 插件实体参阅 odoo 社区的一篇文章 从 0 `开始创建一个 Odoo 插件模`[^1]

## 1.插件的商店显示

- 插件在商店的显示信息应当是固定的,不能在程序中通过编程来动态变更.可以查看下载量,评论,评级
- 且应当有多种不同的方式编辑,或设置.例如 c#语言类,xml,json,html 静态语言的好处是智能语法提示和类型约束,json,xml 等配置文件的好处是不用编译整个项目,当插件配置参数过多而且需要调试插件的版本依赖等情况，插件易于调整
- 插件的资源的多平台性,例如移动端,小程序,Web 手机端,Pc 端等

### 1.1 图标显示

插件图标具备以下特点

- 跨平台跨设备
- 插件

## 2.插件的类图设计

```puml
@startuml
interface IPluginDescription<<插件描述接口>> {
  + string Summary #副标题
  + string Author #作者，多个作者时以逗号间隔
  + string Description #描述
  + string License #证书，常用用 AGPL-3，其它选项：LGPL-3或其它OSI证书
  + string Website #获取插件更多详情的网址
  + string Category  #插件分类,详情阅读开发者文档 xxx.xxx.com
  + string Version #版本号
  + List<string> Depends #依赖的模块列表，如无，则至少会依赖 base
  + bool Application #是否应用程序,设置后以应用程序启动,否则以后台服务启动
}

interface IPlugin<<插件接口>>{
  + OnInstall
  + Dictionary<string,List<object>> PluginPresetData() #插件预设代码

}

IPlugin--|>IPluginDescription
@enduml
```

[^1]: [从 0 开始创建一个 Odoo 插件模块](https://alanhou.org/create-odoo-addon-module/)

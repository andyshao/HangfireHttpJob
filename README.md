使用说明
====
1.数据库配置，sqlserver ,redis 只需要在config中配置连接，就可以直接跑起来添加任务运行，mysql数据库需要用项目中的脚本先创建数据库及表，
然后配置连接就可以直接使用，其他数据源暂时没试

2.运行方式，宿主程序为webapi，需要用配置文件中的website地址运行，打开才是hangfire面板

3.添加了basic认证，账号密码在config配置，用来登录hangfire面板

4.任务类型：

周期任务: 在周期任务面板，可以添加，编辑

计划任务：在作业中的计划下，可以新增计划任务，计划任务只会执行一次，可以设置执行时间

Windows服务部署
====
控制台方式运行,需要加参数 --console

Windows服务发布：直接发布webapi项目,在publish目录用管理员方式运行安装服务bat脚本，即可安装成功。

可以多实例部署




新增接口健康检查
====
可以通过在config配置地址，需要在被检测的接口中实现检查需要的接口，只需要简单实现可以访问到就行，
通过设置检查时间，每隔一段时间去检查健康状况，并可以在ui界面查看，ui界面地址为ip：端口/hc
可以提供json数据格式获取，将hc，换hc-api ,或者通过自定义json格式数据返回，代码中已经实现并注释

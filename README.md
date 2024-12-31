> #### 作者主页：[舒克日记](https://blog.csdn.net/cativen)
>
>  简介：Java领域优质创作者、Java项目、学习资料、技术互助
>
> <b><font color=red>文中获取源码</font></b>

# 项目介绍

系统有管理员、用户两个角色。

​

主要的模块：用户信息管理、车辆信息管理、租赁信息管理、合同信息管理、轮播图管理、新闻资讯管理

# 环境要求

1.运行环境：最好是java jdk1.8,我们在这个平台上运行的。其他版本理论上也可以。

2.IDE环境：IDEA,Eclipse,Myeclipse都可以。推荐IDEA;

3.tomcat环境：Tomcat7.x,8.X,9.x版本均可

4.硬件环境：windows7/8/10 4G内存以上；或者Mac OS;

5.是否Maven项目：是；查看源码目录中是否包含pom.xml;若包含，则为maven项目，否则为非maven.项目

6.数据库：MySql5.7/8.0等版本均可；

# 技术栈

运行环境：jdk8 + tomcat9 + mysql5.7 + windows10

服务端技术：Java、Spring、SpringMVC、Mybatis，SSM

# 使用说明

1.使用Navicati或者其它工具，在mysql中创建对应sq文件名称的数据库，并导入项目的sql文件；

2.使用IDEA/Eclipse/MyEclipse导入项目，修改配置，运行项目；

3.将项目中config-propertiesi配置文件中的数据库配置改为自己的配置，然后运行；

# 运行指导

idea导入源码空间站顶目教程说明(Vindows版)-ssm篇：

http://mtw.so/5MHvZq

源码地址：[http://www.codegym.top](http://www.codegym.top/)



# 运行截图

## 功能模块截图

![img](https://i-blog.csdnimg.cn/img_convert/9e59aa87383ddca6427b372dd44ecf6f.png)

###

### 项目截图

前台

![ssm107电动车租赁网站jsp0](https://i-blog.csdnimg.cn/img_convert/0f39e3e0e99a99678ddf841bbf925e66.png)

![ssm107电动车租赁网站jsp1](https://i-blog.csdnimg.cn/img_convert/4b804ad9df5bc60ce92c551d482fc30d.png)

![ssm107电动车租赁网站jsp2](https://i-blog.csdnimg.cn/img_convert/aeee80c982e83cf4c285f514c525533d.png)

后台

![ssm107电动车租赁网站jsp3](https://i-blog.csdnimg.cn/img_convert/544dc050bbb13de19602ba9746acb993.png)

![ssm107电动车租赁网站jsp4](https://i-blog.csdnimg.cn/img_convert/0fdc4be1a7b6f8a6bc428dc867d55b92.png)

![ssm107电动车租赁网站jsp5](https://i-blog.csdnimg.cn/img_convert/8e6d47f94761c4fd2c402c5776e84a64.png)

![ssm107电动车租赁网站jsp6](https://i-blog.csdnimg.cn/img_convert/dd9ca06d3621f1ff39d97c8a9fc953e2.png)

![ssm107电动车租赁网站jsp7](https://i-blog.csdnimg.cn/img_convert/072fc455881b115220503cf82525f800.png)
### 代码

```
    @Operation(summary = "新增/修改游客")
    @PostMapping("/save")
    public SingleResponse<GuestDTO> save(@RequestBody GuestDTO guestDTO) {
        if (StringUtils.isEmpty(guestDTO.getId())) {
            guestDTO.setCreatorId(RequestUtils.getCurrentUserId());
        }

        guestDTO.setTenantId(RequestUtils.getCurrentTenantId());
        guestDTO.setModifierId(RequestUtils.getCurrentUserId());
        return guestService.save(guestDTO);
    }

```

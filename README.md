##Spring-Boot With Dubbox ##
该项目整合了最新的Spring Boot和功能强大的RPC框架Dubbox<br>

最新版本的Spring Boot包含了Metrics模块<br>

 Spring Boot:<br>
 
> 1、微内核<br>
> 2、配置简单<br>
> 3、模块化<br>
> 4、开箱即用<br>
> 5、完全兼容Spring<br>
> 6、设计理念极其先进，很多思想来自OSGi，但是在现有技术的实现<br>




----------


Dubbox:<br>
-------
 > 1、完全兼容Dubbo<br>
 > 2、功能强大<br>
 > 3、性能强悍<br>
 > 4、运行稳定<br>
 > 5、可扩展性较好, Api和Spi分离<br>

缺点:

> 1、官方停止维护已经两年之久了<br>
 > 2、依赖较为陈旧<br>
 > 3、运行时较重，应该微内核和模块化这个框架<br>
 > 4、配置较为复杂，学习成本较高<br>

建议：<br>

    大家有机会一起维护Dubbox 模块化和微内核这个框架


 ---------------------------------------
 
 boot-dubbo-normal-client<br>

 * 这个项目我想以一个第三方的项目使用dubbox
 * 这个项目跟spring boot没有一点关系。
 
如果仅仅测试dubbo:<br>
 * boot-dubbo-simple
 * boot-dubbo-simple-client

上述两个项目就够用了<br>

boot-dubbo-infrastructure<br>
这个模块项目只与数据库相关，其中集成了Spring-Data-Jpa以及Mybatis<br>
 * Spring-Data-Jpa一般负责增删改，这个及其简单
 * Mybatis负责较为复杂的查询

boot-dubbo-service<br>
该项目依赖api和boot-dubbo-infrastructure<br>
它要实现api约定的接口，另外依赖boot-dubbo-infrastructure对不同数据表的操作以及对事务的操作<br>

boot-dubbo-web<br>
该项目依赖api，它是dubbo的客户端，它通过调用api等于invoke到serice的服务上，从而实现了rpc的调用和服务治理。<br>

说明：<br>
 * service:一般我们的service瓶颈在IO或者数据库上，部署无需太多
 * web:一般的压力在web上，如果很多用户并发，session以及转换都在web上，web建议多部署几台

 


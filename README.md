
# 趣味探店

一款基于 Spring Boot + Redis 的高并发本地生活服务平台，采用前后端分离架构，聚焦商户查询、优惠券秒杀、博客互动等核心场景，旨在解决单体应用在高并发读取、超卖风险及分布式会话下的性能瓶颈。


## 技术栈


Spring Boot, MyBatis-Plus, Redis , MySQL, Redisson, RabbitMQ , Lombok, Hutool, Nginx
## Mac开发环境搭建

1.安装JDK8

2.通过Homebrew安装MySQL、Redis、Maven、Nginx
     
①利用DataGrip创建MySQL数据库
    
②Redis图形化工具Another

## 项目成果


1、分布式鉴权与状态治理：基于 Redis 重构集群会话解决 Session 共享难题；结合自定义拦截器与 ThreadLocal 实现无状态鉴权及 Token 自动续期，在保障线程隔离的同时支持系统横向扩展。

2、高可用缓存体系构建：采用 Cache Aside 模式配合 MQ 异步重试保障双层缓存一致性；通过缓存空值、逻辑过期及互斥锁策略化解穿透、击穿与雪崩风险，显著减轻高并发下的数据库负载。

3、高并发秒杀链路攻坚：编写 Redis + Lua 脚本保障库存预检原子性，结合乐观锁杜绝超卖；引入分布式锁实现“一人一单”约束，并基于 RabbitMQ 异步削峰重构下单流程，缓解瞬时压力。

4、社交互动性能优化：利用 Redis ZSet 实现点赞排行榜，将动态排序复杂度优化至O(logN)；基于Set 集合运算高效实现共同关注与粉丝比对，替代传统多表关联查询，提升检索效能。
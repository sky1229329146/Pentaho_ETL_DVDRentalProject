# Penteho_ETL_DVDRentalProject
## 项目名称
基于sakila数据库的DVD在线租赁项目

## 项目介绍
基于一个虚拟的DVD出租连锁店Sakila，通过建立星型模型进行进行分析，这个星型模型来自MySQL免费的sakila数据库。在这个项目中，系统定期从源数据库sakila删除增量数据。然后转换成符合星型模型的数据，最后把数据加载到目标数据库的租赁业务星型模型中。

## 项目要点

1.每个商店维护自己的租赁影片清单，当客户取走或归还DVD光盘时会有一个专门的店员对这个清单进行维护。

2.影片描写的内容同样在维护信息范围之内，如分类（动作，冒险，喜剧等），演员，等级，特殊分类（例如被删除的情节和预告片）。

3.必须在商店注册成为会员才可以租赁光盘。

4.客户可以在任何一家商店租赁一张光盘或多张光盘，同时，商店希望客户在每张光盘对应的租赁租赁归还之前租赁的光盘。

5.顾客可以在任意时间对任何租赁的光盘的。

6.计算演员对客户租赁影片的贡献值。

拓展：通过客户的租赁数据分析客户对影片类型和演员的个人倾向

## 建模--星型模型
事实表与多个维度表关联,维度表之间没有没有关联
## 设计规范
1.每张表都有自增主键列，列名采用“表名_id”的规则命名
2.外键约束引用主键，且名字与主键列的相同
3.每张表都有一列叫做【last_update】，用来记录增加或更新数据时的时间
## ETL实现
1.生成和加载静态变化维度表dim_time和dim_data
2.生成和加载缓慢变化维度表dim_store,dim_address,dim_staff,dim_film,dim_actor,dim_customer
3.




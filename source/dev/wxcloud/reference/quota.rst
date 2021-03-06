资源配额
==========

这里列出云开发基础资源配额，API调用次数限制包含小程序端和服务端两部分


+--------+-----------------------------+------------+
|  分类  |          配额种类           |    额度    |
+========+=============================+============+
| 存储   | 容量                        | 5GB        |
+--------+-----------------------------+------------+
|        | 下载操作次数                | 5万/天     |
+--------+-----------------------------+------------+
|        | 上传操作次数                | 2万/天     |
+--------+-----------------------------+------------+
|        | 外网下行流量                | 无         |
+--------+-----------------------------+------------+
|        | CDN回源流量 [1]_            | 5GB/月     |
+--------+-----------------------------+------------+
| CDN    | CDN流量                     | 5GB/月     |
+--------+-----------------------------+------------+
| 云函数 | 调用次数                    | 20万次/月  |
+--------+-----------------------------+------------+
|        | 资源使用量GBs [2]_          | 4万/月     |
+--------+-----------------------------+------------+
|        | 外网出流量                  | 1GB/月     |
+--------+-----------------------------+------------+
|        | (单个云函数)同时连接数 [3]_ | 20         |
+--------+-----------------------------+------------+
|        | 数量限制                    | 20个       |
+--------+-----------------------------+------------+
|        | (单次运行)运行内存最大      | 256MB [4]_ |
+--------+-----------------------------+------------+
| 数据库 | 容量                        | 2GB        |
+--------+-----------------------------+------------+
|        | QPS                         | 30         |
+--------+-----------------------------+------------+
|        | 同时连接数 [5]_             | 20         |
+--------+-----------------------------+------------+
|        | 读操作次数                  | 5万/天     |
+--------+-----------------------------+------------+
|        | 写操作次数                  | 3万/天     |
+--------+-----------------------------+------------+
|        | 集合限制                    | 100个      |
+--------+-----------------------------+------------+
|        | 单集合索引限制              | 10个       |
+--------+-----------------------------+------------+


以上均是一个环境的配额，不是所有环境的总和限制。

如需申请上调，开发者可以"申请调整小程序云开发调用资源上限"为主题， `发送邮件 <mailto:miniprogram@tencent.com>`_  申请调整，
并在正文中注明小程序帐号AppID、需要调整的环境名称、需要调整的资源上限(仅限资源配额中所列内容)、小程序服务类目(可在小程序基本设置中查询)、
资源调整原因以及产品计划上线时间。

.. note::

  小程序·云开发将在2019年春节期间2月3日至2月11日暂停资源配额调整申请处理。2月3日至2月11日提交的申请将在2月12日统一处理。请各位开发者合理安排申请时间，避免影响功能迭代。

注：

.. [1] 指开启了CDN加速后，CDN回源存储时产生的流量。
.. [2] 资源使用量=函数配置内存X运行计费时长。用户资源使用量，是由函数配置内存，乘以函数运行时的计费时长得出，其中配置内存转换为GB单位，计费时长由毫秒(ms)转换为秒。(s)单位，因此，资源使用量的计算单位为GBs(GB-秒)。例如，配置为256MB的函数，单次运行了1760ms，计费时长为1800ms，则单次运行的资源使用量为(256/1024)*(1800/1000)=0.45GBs。针对函数的每次运行，均会计算资源使用量，并按月汇总求和，作为当月的资源使用量。
.. [3] 云函数并发运行数量，如同时有三十个云函数调用请求，则有二十个会同时执行，剩下十个请求会被拒绝；每个云环境分别有一个同时连接数限制、独立计数。
.. [4] 云函数运行时最大可用内存为256MB，在控制台云函数运行日志中展示的内存信息是当次运行实际内存占用，可能低于256MB，计费时按配置内存即256MB计算。
.. [5] 数据库请求并发数量，如同时有三十个数据库操作请求，则有二十个会同时执行，剩下十个在队列中等待有空余资源再执行；小程序端和云函数端发起的数据库操作算入同一个同时连接数限制，每个云环境分别有一个同时连接数限制、独立计数。
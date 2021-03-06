控制台
==============

云开发提供了一个控制台用于可视化管理云资源。控制台包含以下几大模块。

* 概览：查看云资源的总体使用情况
* 用户管理：查看小程序的用户访问记录
* 数据库：管理数据库集合、记录、权限设置、索引设置
* 存储管理：管理云文件、权限设置
* 云函数：管理云函数、查看调用日志、监控记录
* 统计分析：查看云资源详细使用统计

在用户管理中会显示使用云能力的小程序的访问用户列表，默认以访问时间倒叙排列，
访问时间的触发点是在小程序端调用 wx.cloud.init 方法，且其中的 traceUser 参数传值为 true。例：

.. code-block:: js

  wx.cloud.init({
    traceUser: true
  })

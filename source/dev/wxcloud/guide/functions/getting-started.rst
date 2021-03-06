我的第一个云函数
================

我们以定义一个将两个数字相加的函数作为我们第一个云函数的示例。

在项目根目录找到 project.config.json 文件，新增 cloudfunctionRoot 字段，指定本地已存在的目录作为云函数的本地根目录

示例：
.. code-block::

  {
    "cloudfunctionRoot": "./functions/"
  }

project.config.json 的其他配置，详见文档

完成指定之后，云函数的根目录的图标会变成 “云目录图标”，云函数根目录下的第一级目录（云函数目录）是与云函数名字相同的，如果对应的线上环境存在该云函数，则我们会用一个特殊的 “云图标” 标明



接着，我们在云函数根目录上右键，在右键菜单中，可以选择创建一个新的 Node.js 云函数，我们将该云函数命名为 add。开发者工具在本地创建出云函数目录和入口 index.js 文件，同时在线上环境中创建出对应的云函数。创建成功后，工具会提示是否立即本地安装依赖，确定后工具会自动安装 wx-server-sdk。我们可以看到类似如下的一个云函数模板：

.. code-block::

  const cloud = require('wx-server-sdk')
  // 云函数入口函数
  exports.main = async (event, context) => {

  }

云函数的传入参数有两个，一个是 event 对象，一个是 context 对象。event 指的是触发云函数的事件，当小程序端调用云函数时，event 就是小程序端调用云函数时传入的参数，外加后端自动注入的小程序用户的 openid 和小程序的 appid。context 对象包含了此处调用的调用信息和运行状态，可以用它来了解服务运行的情况。在模板中也默认 require 了 wx-server-sdk，这是一个帮助我们在云函数中操作数据库、存储以及调用其他云函数的微信提供的库，关于 wx-server-sdk 的使用我们在另一个章节讲述。

我们填充一下模板：

.. code-block::

  exports.main = async (event, context) => ({
    sum: event.a + event.b
  })

本段代码的意思是将传入的 a 和 b 相加并作为 sum 字段返回给调用端。

在小程序中调用这个云函数前，我们还需要先将该云函数部署到云端。在云函数目录上右键，在右键菜单中，我们可以将云函数整体打包上传并部署到线上环境中。

部署完成后，我们可以在小程序中调用该云函数：

.. code-block::

  wx.cloud.callFunction({
    // 云函数名称
    name: 'add',
    // 传给云函数的参数
    data: {
      a: 1,
      b: 2,
    },
    success(res) {
      console.log(res.result.sum) // 3
    },
    fail: console.error
  })

当然，Promise 风格的调用也是支持的：

.. code-block::

  wx.cloud.callFunction({
    // 云函数名称
    name: 'add',
    // 传给云函数的参数
    data: {
      a: 1,
      b: 2,
    },
  })
    .then(res => {
      console.log(res.result) // 3
    })
    .catch(console.error)

那么到这里，我们就成功创建了我们的第一个云函数，并在小程序中成功调用！

在下一章节，我们介绍云函数和小程序登录态如何无缝结合，以及如何在云函数端获取小程序用户信息（openid 和 appid）。
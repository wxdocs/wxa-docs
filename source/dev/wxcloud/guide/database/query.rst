指令
==========

使用数据库 API 提供的 where 方法我们可以构造复杂的查询条件完成复杂的查询任务。在本节中我们还是使用上一章节中使用的示例数据。

查询指令
----------

假设我们需要查询进度大于 30% 的待办事项，那么传入对象表示全等匹配的方式就无法满足了，这时就需要用到查询指令。数据库 API 提供了大于、小于等多种查询指令，这些指令都暴露在 db.command 对象上。比如查询进度大于 30% 的待办事项：

.. code-block:: js

  const _ = db.command
  db.collection('todos').where({
    // gt 方法用于指定一个 "大于" 条件，此处 _.gt(30) 是一个 "大于 30" 的条件
    progress: _.gt(30)
  })
    .get({
      success(res) {
        console.log(res.data)
      }
    })

API 提供了以下查询指令：

查询指令	说明
eq	等于
neq	不等于
lt	小于
lte	小于或等于
gt	大于
gte	大于或等于
in	字段值在给定数组中
nin	字段值不在给定数组中
更多具体的查询指令 API 文档可参考数据库 API 文档。

逻辑指令
----------

除了指定一个字段满足一个条件之外，我们还可以通过指定一个字段需同时满足多个条件，比如用 and 逻辑指令查询进度在 30% 和 70% 之间的待办事项：

.. code-block:: js

  const _ = db.command
  db.collection('todos').where({
    // and 方法用于指定一个 "与" 条件，此处表示需同时满足 _.gt(30) 和 _.lt(70) 两个条件
    progress: _.gt(30).and(_.lt(70))
  })
    .get({
      success(res) {
        console.log(res.data)
      }
    })

既然有 and，当然也有 or 了，比如查询进度为 0 或 100 的待办事项：

.. code-block:: js

  const _ = db.command
  db.collection('todos').where({
    // or 方法用于指定一个 "或" 条件，此处表示需满足 _.eq(0) 或 _.eq(100)
    progress: _.eq(0).or(_.eq(100))
  })
    .get({
      success(res) {
        console.log(res.data)
      }
    })

如果我们需要跨字段进行 "或" 操作，可以做到吗？答案是肯定的，or 指令还可以用来接受多个（可以多于两个）查询条件，
表示需满足多个查询条件中的任意一个，比如我们查询进度小于或等于 50% 或颜色为白色或黄色的待办事项：

.. code-block:: js

  const _ = db.command
  db.collection('todos').where(_.or([
    {
      progress: _.lte(50)
    },
    {
      style: {
        color: _.in(['white', 'yellow'])
      }
    }
  ]))
    .get({
      success(res) {
        console.log(res.data)
      }
    })

具体的逻辑查询指令 API 文档可参考数据库 API 文档。
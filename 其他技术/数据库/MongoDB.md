# MongoDB

数据库命令

显示所有数据库

show dbs

却换到指定的数据库， 如果不存在会自动创建数据库

use 数据库名称

显示当前数据库

db

删除当前数据库

在要删除的数据库下，db.dropDatabase()

不在，到数据库下在进行删除

集合命令

创建集合

db.createCollection(’集合名称‘)

显示当前数据库中的所有集合

show collections

删除某个集合

db.集合名,.drop()

重命名集合

db.集合名,.renameCollection（’新集合名‘）

文档命令

插入文档

db.集合名,.insert（文档对象）

查询文档

db.集合名,.find(’查询条件‘)

更改文档

db.集合名,.update(查询条件，新的文档) 全部更新，新文档替换旧文档

db.集合名,.update({name：’张三‘}，{$age:{age:19}})

删除文档

db.集合名,.remove(查询条件)

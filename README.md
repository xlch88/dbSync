# dbSync
MySQL 数据库结构同步工具，用于程序更新时同步新旧版本的数据库字段。

# 可同步内容
- 字段名
- 字段类型
- 字段长度
- 字段是否为NULL
- 字段默认值
- 字段备注
- 字段是否自增长
- 字段主键、唯一、索引

具体参见dbSync.data.php

# 使用例子
```php
include('dbSyncTool.class.php');
$syncData = include('dbSync.data.php');

if($mysql = mysqli_connect($db_host, $db_user, $db_pass, $db_name, $db_port)){
  $dbSyncTool = new dbSyncTool($mysql, $syncData['data'], $syncData['option']);
  $dbSyncTool->fix();
}
```

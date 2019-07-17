# ab-manager-indexeddb@结构化数据存取

用于客户端存储大量结构化数据(包括，文件 / blobs)

1. 引入

```js
import { IndexedDBManager } from ab-manager-database;
```

2. 初始化

```js
const db = new IndexedDBManager('test', options);
```

> `options`：初始化数据库时对数据表和索引的配置（可选）

```
// 作为对象传入
{
  name: 'store',               // 表名（必填）
  keyPath: 'id',               // 主键（可选，默认主键自增）
  indexes: [                   // 索引（可选）
    {
      name: 'nameIndex',       // 索引名（必填）
      key: 'name',             // 表中对应属性名（必填）
      unique: false            // 是否唯一（可选，默认false）
    },
    {
      name: 'age',
      key: 'age',
      unique: true
    }
  ]
}

// 作为数组传入
[
  {
    name: 'store1',
    indexes: [
      {
        name: 'name',
        key: 'name',
        unique: false 
      },
      {
        name: 'age',
        key: 'age',
        unique: true
      }
    ]
  },
  {
    name: 'store2',
    keyPath: 'id',
    indexes: [
      {
        name: 'name',
        key: 'name',
        unique: false
      }
    ]
  }
]
```

3. 新建数据表

```js
await db.addStore('user', 'id');
```

| 参数     | 说明                            | 必填   | 类型     | 默认值  |
| :------ | :------------------------------ | :---- | :------- | :----- |
| store   | 表名                             | 是    | String  | -       |
| key     | 主键(不传该参数时，默认生成自增主键) | 否    | String  | -      |

4.  删除数据表

```js
await db.deleteStore('user');
```

| 参数     | 说明                            | 必填   | 类型     | 默认值  |
| :------ | :-----------------------------: | :---- | :------- | :----- |
| store   | 表名                             | 是    | String  | -       |

5.  清空数据表

```js
await db.clearStore('user');
```

| 参数     | 说明                            | 必填   | 类型     | 默认值  |
| :------ | :------------------------------ | :---- | :------- | :----- |
| store   | 表名                             | 是    | String  | -       |

6. 新建索引

```js
const index = [
  {
    name: 'name',       // 索引名（必填）
    key: 'name',        // 表中对应属性名（必填）
    unique: false       // 是否唯一（可选，默认false）
  },
  {
    name: 'age',
    key: 'age',
    unique: true 
  }
];

await db.addIndex('user', index);
```

| 参数     | 说明        | 必填  | 类型             | 默认值  |
| :------ | :---------- | :---- | :-------------- | :----- |
| store   | 表名        | 是    | String          | -      |
| index   | 索引配置项  | 是    | Array / Object  | -      |

7. 删除索引

```js
await db.deleteIndex('user', 'name');
```

| 参数     | 说明     | 必填   | 类型     | 默认值  |
| :------ | :------- | :---- | :------- | :----- |
| store   | 表名     | 是    | String   | -      |
| index   | 索引名   | 否    | String   | -      |

8. 新增/修改数据

```js
const data = {
  id: 1001,
  name: 'zz', 
  age: 22, 
  email: '2418184580@qq.com'
}

await db.set('user', data, 'id');
```

```js
/** user表    Key(Key path: "id")
{id: 1001, name: 'aa', age: 25, email: 'aa@example.com'}，
{id: 1002, name: 'bb', age: 22, email: 'bb@example.com'}，
{id: 1003, name: 'cc', age: 26, email: 'cc@example.com'}，
{id: 1004, name: 'dd', age: 21, email: 'dd@example.com'}
**/

// 向表中添加一条数据
const data1 = {id: 1005, name: 'ee', age: 23, email: 'ee@example.com'};
await db.set('user', data1);

// 将id为1001的数据中email的值修改为'1001@example.com'
const data2 = {id: 1001, name: 'aa', age: 25, email: '1001@example.com'};
await db.set('user', data2);
```

```js
/** user表    Key(autoIncrement: true)
{name: 'aa', age: 25, email: 'aa@example.com'}，
{name: 'bb', age: 22, email: 'bb@example.com'}，
{name: 'cc', age: 26, email: 'cc@example.com'}，
{name: 'dd', age: 21, email: 'dd@example.com'}
**/

// 向表中添加一条数据，主键自增1
const data1 = {name: 'ee', age: 23, email: 'ee@example.com'};
await db.set('user', data1);

// 将Key为1的数据中email的值修改为'1001@example.com'
const data2 = {name: 'aa', age: 25, email: '1001@example.com'};
await db.set('user', data2, 1);
```

| 参数     | 说明                                    | 必填   | 类型      | 默认值  |
| :------ | :-------------------------------------- | :---- | :------- | :----- |
| store   | 表名                                    | 是    | String   | -      |
| data    | 数据对象                                | 是    | Object   | -      |
| key     | 主键的值（不传该参数时，数据对象中必须包含key） | 否    | String   | -      |

9. 根据主键获取数据

```js
let data = await db.get('user', 1001);    // 主键为id，获取id=1001的数据
```

| 参数     | 说明       | 必填  | 类型      | 默认值  |
| :------ | :-------- | :---- | :------- | :----- |
| store   | 表名      | 是    | String   | -      |
| key     | 主键的值  | 是    | Any      | -      |


10. 根据主键移除数据

```js
await db.remove('user', 1001);    // 主键为id，移除id=1001的数据
```

| 参数     | 说明       | 必填  | 类型      | 默认值  |
| :------ | :-------- | :---- | :------- | :----- |
| store   | 表名      | 是    | String   | -      |
| key     | 主键的值  | 是    | Any      | -      |

11. 获取游标范围内数据

```js
// 检索"aa"和"bb"之间的数据（包括"aa"和"dd"），结果按Key值升序排列
let data1 = await db.query('user', { index: 'name', start: 'aa', end: 'dd', direction: 'next' });

// 检索"aa"之后的所有数据（包括"aa"），并过滤掉重复数据，结果按Key值降序排列
let data2 = await db.query('user', { index: 'name', start: 'aa', direction: 'prevunique' });

// 检索"dd"之前的所有数据（包括"aa"），结果按Key值升序排列
let data3 = await db.query('user', { index: 'name', end: 'dd'});

// 检索Key值为"cc"的数据
let data3 = await db.query('user', { index: 'name', start: 'cc', end: 'cc'});

```

| 参数     | 说明             | 必填  | 类型      | 默认值                                                                     |
| :------ | :-------------- | :---- | :------- | :------------------------------------------------------------------------- |
| store   | 表名            | 是    | String   | -                                                                           |
| opt     | 检索条件配置项   | 是    | Object   | `{ index: undefined, start: undefined, end: undefined, direction: 'next' }` |


`opt`属性：

| 属性名     | 说明                                                               | 必填  | 类型      | 默认值      | 可选值 |
| :-------- | :---------------------------------------------------------------- | :---- | :------- | :---------- | :---- |
| index     | 索引名（不设置该属性时 ，在数据表中检索；设置该属性时，在对应索引表中检索）| 否    | String   | `undefined` | - |
| start     | 游标开始位置                                                       | 否    | Any      | `undefined` | - |
| end       | 游标结束位置                                                       | 否    | Any      | `undefined` | - |
| direction | 游标移动方向                                                       | 否    | String   | `'next'`    | `next`：游标中的数据按Key值升序排列，Key值相等的数据都被读取<br>`nextunique`：游标中的数据按Key值升序排列，Key值相等只读取第一条数据<br>`prev`：游标中的数据按Key值降序排列，Key值相等的数据都被读取<br>`prevunique`：游标中的数据按Key值降序排列，Key值相等只读取第一条数据 |
	
> *注：只有在索引表中检索，并且索引的`unique`为`false`时，才可能出现`Key`值相等的数据*

12. 导出数据库中的数据

```js
const data = await db.exportData();

/** data中的数据结构
{
  dbName: "test",              // 数据库名
  stores: [{                   // 数据表项
    name: "store1",            // 表名
    keyPath: "id",             // 主键
    indexes: [{name: "age",key: "age",unique: false}],                // 索引项
    data: [{name:"zz","age":22,"email":"1@qq.com","remark":"qwq"}]    // 数据项
  }]
}
**/
```

13. 向数据库导入数据

```js
// const data = await db.exportData();

const db1 = new IndexedDBManager(data.dbName);
db1.importData(data);
```

**IndexedDBManager Attributes**

| 参数         | 说明         | 类型             | 默认值     |
| :---------- | :----------- | :-------------- | :-------- |
| dbName      | 数据库名称    | String          | -         |
| options     | 初始化配置项  | Array / Object  | -         |

**IndexedDBManager Methods**

| 方法名       | 说明             | 参数                                          |
| :---------- | :--------------- | :--------------------------------------------|
| addStore    | 新建数据表        | store：表名<br>key：主键                       |
| deleteStore | 删除数据表        | store：表名                                   |
| clearStore  | 清空数据表        | store：表名                                   |
| addIndex    | 新建索引          | store：表名<br>index：索引配置项               |
| deleteIndex | 删除索引          | store：表名<br>index：索引名                  |
| get         | 根据主键获取数据   | store：表名<br>key：主键的值                  |
| set         | 新增/修改数据      | store：表名<br>data：数据对象<br>key：主键的值 |
| remove      | 根据主键移除数据   | store：表名<br>key：主键的值                  |
| query       | 获取游标范围内数据 | store：表名<br>opt：检索条件配置项             |
| close       | 关闭数据库        | -                                           |
| delete      | 删除数据库        | -                                           |
| exportData  | 导出数据库        | -                                           |
| importData  | 导入数据库        | data：备份的数据库                                           |

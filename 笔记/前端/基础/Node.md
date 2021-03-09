## Node.js

[TOC]

#### NPM 包管理器

- **常用命令**

  - **参数**

  | 参数                      | 作用                                                         |
  | ------------------------- | ------------------------------------------------------------ |
  | **-g**                    | **全局**                                                     |
  | **-S 或 --save**          | **包信息将加入到 `dependencies`（==生产==阶段的依赖）**      |
  | **-D 或 --save-dev**      | **包信息将加入到 `devDependencies`（==开发==阶段的依赖）**   |
  | **-O 或 --save-optional** | **包信息将加入到 `optionalDependencies`（==可选==阶段的依赖）** |

  > **安装模块**

  ```shell
  npm install 包名
  npm install 包名@0.0.0	#安装指定版本
  ```

  > 卸载模块 

  ```shell
  npm uninstall 包名
  ```

- **package.json 		对项目或者模块包的描述**

  ```json
  {
  	"name": "包的名称",
  	"description": "自述文件",
  	"version": "版本号",
  	"main": "index.js",	//入口文件
  	"scripts": {
  	  //脚本命令
  	},
  	"repository": { //包代码的Repo信息
  	  "type": "git / svn",
  	  "url": "代码存放地址"
  	},
  	"license": "ISC",//软件授权条款
  	"bugs": {	//bug 提交地址
  	  "url": ""
  	},
  	"homepage": "包官网URL"
  }
  ```

#### 文件操作

- **导入模块**

```js
var fs = require("fs");
```

- **读取文件**

```js
fs.readFile("文件名", function (err, data) {
  if (err) {
    console.log(err);
  } else {
    //打印读取内容
    console.log(data.toString());
  }
});
```

- **写入文本**

```js
var msg = "文本";
fs.writeFile("文件名", msg, function (err) {
  if (err) {
    console.log(err);
  } else {
    console.log("写入成功");
  }
});
```

| 函数名             | 作用             |
| ------------------ | ---------------- |
| **fs.open()**      | **打开文件**     |
| **fs.stat()**      | **获取文件信息** |
| **fs.readFile()**  | **读取文件**     |
| **fs.writeFile()** | **写入文件**     |
| **fs.close()**     | **关闭文件**     |
| **fs.unlink()**    | **删除文件**     |
| **fs.mkdir()**     | **创建目录**     |
| **fs.readdir()**   | **读取目录**     |

#### async 异步函数



#### node 连接 MySQL

- **下载模块**

```shell
npm install mysql
```

- **连接数据库**

```js
//导入模块
var mysql = require("mysql");
//创建连接
var connection = mysql.createConnection({
  host: "localhost", //主机名
  user: "root", //用户名
  password: "000000", //密码
  port: "3306", //端口号
  database: "wly", //数据库名
});
//开始连接
connection.connect();
var sql = "sql语句";
//执行sql语句
connection.query(sql, function (err, res) {
  if (err) {
    console.log(err);
  }else {
    console.log(res);
  }
});
//关闭连接
connection.end();
```


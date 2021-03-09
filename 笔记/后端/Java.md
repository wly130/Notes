## JAVA

## 目录

[TOC]

## 注解

| 注解                  | 作用                             |
| --------------------- | -------------------------------- |
| **@Override**         | 检查是否是重写方法               |
| **@Deprecated**       | 标记过时方法                     |
| **@SuppressWarnings** | 指示编译器去忽略注解中声明的警告 |

## 变量

- **局部变量** 只能在**本方法内**使用,**必须初始化**,才能使用
- **成员变量** **有默认值**,**无须初始化**
- **静态变量**

## 常量

- **final** 定义**常量**,内容**不可变**,常量名**字母大写**

|   进制   | &nbsp;        |
| :------: | ------------- |
|  二进制  | a = 01100100; |
|  十进制  | a = 100;      |
|  八进制  | a = 0144;     |
| 十六进制 | a = 0x64;     |

## 数据类型

#### 基本数据类型

| 整数型 | 字节数 |       范围       |    默认值    |
| :----: | :----: | :--------------: | :----------: |
|  byte  | 1 字节 |  -2^7^ ~ 2^7^-1  | byte a = 0;  |
| short  | 2 字节 | -2^15^ ~ 2^15^-1 | short a = 0; |
|  int   | 4 字节 | -2^31^ ~ 2^31^-1 |  int a = 0;  |
|  long  | 8 字节 | -2^63^ ~ 2^63^-1 | long a = 0L; |

| 浮点型 | 字节数 |     默认值      |
| :----: | :----: | :-------------: |
| double | 8 字节 | double a = 00d; |
| float  | 4 字节 | float a = 00F;  |

| 字符型 | 字节数 |
| :----: | :----: |
|  char  | 2 字节 |

| 布尔型  |      默认值      |
| :-----: | :--------------: |
| boolean | **true / false** |

#### 引用数据类型

| 类型       | &nbsp;     |
| ---------- | ---------- |
| **字符串** | String     |
| **接口**   | implements |
| **数组**   | Array      |

### 修饰符

| 修饰符        | 范围                                                                                                     |
| ------------- | -------------------------------------------------------------------------------------------------------- |
| **default**   | 默认在同一包内可见,不使用任何修饰符                                                                      |
| **private**   | 在同一类内可见,不能修饰类                                                                                |
| **public**    | 对所有类可见                                                                                             |
| **protected** | 对同一包内的类和所有子类可见,不能修饰类                                                                  |
| **static**    | 用来修饰类方法和类变量                                                                                   |
| **final**     | 用来修饰类,方法和变量, final 修饰的类不能够被继承,饰的方法不能被继承类重新定义,修饰的变量为常量,不可修改 |
| **abstract**  | 用来创建抽象类和抽象方法                                                                                 |

- **访问控制和继承**
  - **父类**中声明为 **public** 的方法在**子类**中也必须为 **public**
  - **父类**中声明为 **protected**的方法在**子类**中声明为 **protected**,或者声明为 **public**,不能声明为 **private**
  - **父类**中声明为 **private** 的方法,**不能够被继承**

[返回顶部](#目录)

## 抽象

```java
    //抽象方法的定义格式
    public abstract 返回值类型 方法名(参数){

    }
    //抽象类的定义格式
    abstract class 类名{

    }
```

- **抽象类的特点：**
  - **抽象类和抽象方法都要被 abstract 修饰,抽象方法一定要定义在抽象类中**
  - **抽象类不可以直接创建对象**
  - **只有覆盖了抽象类中所有的抽象方法后,其子类才可以创建对象,否则该子类还是一个抽象类**

[返回顶部](#目录)

## 方法

```java
    //方法的定义
    修饰符 返回值类型 方法名(参数类型 参数名){
        方法体
        return 返回值;
    }
```

- **形参** 声明时用于**接收外部传来的数据**,值不确定
- **实参** 调用时传递的**实际数据**,值确定
- **无返回值为 void**
- **方法重载** ==方法名==**相同**,但**形参**的**类型**和**个数不同**
- **finalize()** 方法用来**清除回收对象**

[返回顶部](#目录)

## 字符串

[返回顶部](#目录)

## IO 流

| File 类方法         | 作用                                                   |
| ------------------- | ------------------------------------------------------ |
| **getName**         | 获取文件名称                                           |
| **getParent**       | 获取文件的父路径                                       |
| **getPath**         | 获取文件的相对路径                                     |
| **getAbsolutePath** | 获取文件的绝对路径                                     |
| **exists**          | 判断文件是否存在                                       |
| **isFile**          | 判断是不是文件类型                                     |
| **isDirectory**     | 判断是不是文件夹类型                                   |
| **delete**          | 删除文件或文件夹,删除成功返回结果为 true               |
| **mkdir**           | 创建指定目录                                           |
| **mkdirs**          | 创建此路径名指定的目录,包括父目录                      |
| **setReadOnly**     | 设置文件或文件夹的只读属性创建文件夹,创建成功返回 true |
| **length**          | 获取文件的长度                                         |
| **lastModified**    | 获取文件的最后修改时间                                 |
| **list**            | 获取文件夹中的文件和子文件夹的名称                     |
| **listFiles**       | 返回一个路径名数组                                     |

### 输入流

| InputStream        | 作用                                                                                                             |
| ------------------ | ---------------------------------------------------------------------------------------------------------------- |
| available()        | 返回可读有效字节数                                                                                               |
| read()             | 从当前数据流中读取一个字节                                                                                       |
| read(byte[] bytes) | 从当前输入流读取一定的 byte 数据                                                                                 |
| reset()            | 将当前的输入流重新定位到最后一次调用 mark()方法时的位置                                                          |
| mark(int read)     | 在当前输入流中做标记位置,当调用 reset()方法时将返回到该位置,从标记位置开始,到再读入 read 个字符,标记都维持有效。 |
| markSupported()    | 测试当前输入流是否支持 mark()和 reset()方法                                                                      |
| skip(long n)       | 跳过和丢弃当前输入的 n 个字节数据                                                                                |
| close()            | 关闭当前输入流                                                                                                   |

### 输出流

| OutputStream                    | 作用                                                      |
| ------------------------------- | --------------------------------------------------------- |
| write(byte[] b)                 | 将 byte[] 数组中的数据写入当前输出流                      |
| write(byte[] b,int off,int len) | 将 byte[]数组下标 off 开始的 len 长度的数据写入当前输出流 |
| write(int b)                    | 写入一个 byte 数据到当前输出流                            |
| flush()                         | 刷新当前输出流,并强制写入所有缓冲的字节数据               |
| close()                         | 关闭当前输出流                                            |

### 字符输入流

| 子类              | 功能描述                         |
| ----------------- | -------------------------------- |
| CharArrayReader   | 从字符数组读取的输入流           |
| BufferedReader    | 缓冲输入字符流                   |
| PipedReader       | 输入管道                         |
| InputStreamReader | 将字节转换到字符的输入流         |
| FilterReader      | 过滤输入流                       |
| StringReader      | 从字符串读取的输入流             |
| LineNumberReader  | 为输入数据附加行号               |
| PushbackReader    | 返回一个字符并把此字节放回输入流 |
| FileReader        | 从文件读取的输入流               |

| IO 流          | 类名             |
| -------------- | ---------------- |
| 文件字节输入流 | FileInputStream  |
| 文件字节输出流 | FileOutputStream |
| 字符输入流     | Reader           |
| 字符输出流     | Writer           |
| 文件字符输入流 | FileReader       |
| 文件字符输出流 | FileWriter       |
| 字符缓冲输出流 | BufferedWriter   |

[返回顶部](#目录)

## 异常处理

```java
    try{
       // 程序代码
    }catch(异常类型 异常的变量名){
       // 程序代码
    }finally{
       // 程序代码
    }

    //throws/throw 关键字
    public void 方法名() throws 异常类型{
        throw new 异常类型();
    }

    /*finally 关键字
        放在最后,无论是否发生异常,finally 代码块中的代码总会被执行*/
    //自定义异常
    class 类名 extends Exception{

    }
```

[返回顶部](#目录)

## 包装类

| 基本类型 |  包装类   |
| :------: | :-------: |
| boolean  |  Boolean  |
|   char   | Character |
|   int    |  Integer  |
|   byte   |   Byte    |
|  short   |   Short   |
|   long   |   Long    |
|  float   |   Float   |
|  double  |  Double   |

| Character 类方法 | 作用                 |
| ---------------- | -------------------- |
| isLetter()       | 是否是一个字母       |
| isDigit()        | 是否是一个数字字符   |
| isWhitespace()   | 是否是一个空白字符   |
| isUpperCase()    | 是否是大写字母       |
| isLowerCase()    | 是否是小写字母       |
| toUpperCase()    | 指定字母的大写形式   |
| toLowerCase()    | 指定字母的小写形式   |
| toString()       | 返回字符的字符串形式 |

[返回顶部](#目录)

## 继承

```java
        class 父类 {

        }

        class 子类 extends 父类 {

        }
    //extends     继承
    //implements  继承多个接口
        public class 子类 implements 父类1,父类2 {

        }
    //uper 与 this 关键字
        super 调用父类方法
        this  调用自己的方法
    //final 关键字
    //声明类可以把类定义为不能继承的,或者用于修饰方法,该方法不能被子类重写
        final class 类名 {  // 声明类

        }
```

[返回顶部](#目录)

## 封装

```java
    private String name;
    // 读取
    public String getName(){
        return name;
    }
    // 写入
    public void setName(String name){
        this.name = name;
    }
```

[返回顶部](#目录)

## 多态

#### 实现多态3个必要条件

> > - **继承:** 在多态中必须存在有继承关系的子类和父类
> > - **重写:** 子类对父类中某些方法进行重新定义,在调用这法时就会调用子类的方法
> > - **向上转型:** 在多态中需要将子类的引用赋给父类对象,这样该引用才既能可以调用父类的方法,又能调用子类方法

## 集合

| 集合接口       | 作用                       |
| -------------- | -------------------------- |
| **Collection** | 存储一组不唯一，无序的对象 |
| **List**       | 存储有序重复的元素         |
| **Set**        | 存储无序不重复的数据       |
| **SortedSet**  | 保存有序的集合             |
| **Map**        | 存储一组键值对象           |
| **SortedMap**  | 使 Key 保持在升序排列      |

| 集合实现类     | 作用                                        |
| -------------- | ------------------------------------------- |
| **ArrayList**  | 可以动态修改的数组                          |
| **LinkedList** | 线性表,允许有 null                          |
| **HashSet**    | 无序不重复的集合,允许有 null 但最多只能一个 |
| **HashMap**    | 散列表,存储键值对映射,无序的                |
| **TreeSet**    | 实现排序功能                                |

| 集合方法          | 作用                             |
| ----------------- | -------------------------------- |
| **add()**         | 添加元素                         |
| **addAll()**      | 将集合添加至另一集合             |
| **addFirst()**    | 元素添加到头部                   |
| **addLast()**     | 元素添加到尾部                   |
| **put()**         | Map 添加元素                     |
| **offer()**       | 向链表末尾添加元素               |
| **clear()**       | 清除集合中所有元素               |
| **contains()**    | 判断集合是否包含某个元素         |
| **containsAll()** | 判断集合中是否包含给定的集合元素 |
| **isEmpty()**     | 此集合不包含元素则返回 true      |
| **iterator()**    | 迭代器                           |
| **size()**        | 返回集合中的元素数               |
| **get()**         | 返回指定位置元素                 |
| **set()**         | 返回被修改元素                   |
| **indexOf()**     | 查找指定元素第一次出现的索引     |
| **lastIndexOf()** | 查找指定元素最后一次出现的索引   |

- **迭代器**

```java
    Iterator<?> it = ArryList.iterator();// 获取
    it.hasNext();   // 判断是否为空
    it.next();      // 输出集合元素
    it.remove();    // 删除集合元素
```

[返回顶部](#目录)

## 泛型

- 在数据类型**不确定**时使用
- **通配符?** 可以接收**任何数据类型**
  
  > **泛型类**

```java
    public class Show<T>{
        private T key;
        public Show(T key) {
            this.key = key;
        }
        public T getKey(){
            return key;
        }
    }
```

> **泛型接口**

```java
    public interface Impl<T> {
        public T next();
    }
    public class NewShow<T> implements Show<T>{
        @Override
        public T next() {
            return null;
        }
    }
```

> **泛型方法**

```java
    public static <T> void Show(T t){

    }
```

[返回顶部](#目录)

## 多线程

- 线程的**生命周期:**
  - **新建**
  - **就绪**
  - **运行**
  - **阻塞**
  - **死亡**

| Thread 方法     | 作用                               |
| --------------- | ---------------------------------- |
| start()         | 启动线程                           |
| run()           | 执行方法                           |
| setName()       | 改变线程名称                       |
| getName()       | 返回线程名称                       |
| interrupt()     | 中断线程                           |
| stop()          | 强制结束线程                       |
| sleep(n)        | 在 n 毫秒内暂停线程                |
| yield()         | 暂停当前线程对象并执行其他线程     |
| currentThread() | 返回对当前正在执行的线程对象的引用 |

### 创建线程

> **实现 Runnable 接口**

```java
    public class Show implements Runnable{
        public void run(){}     // 重写执行方法
        public static void main(String args[]){
            Show R = new Show();//新建对象
            R.start();// 启动线程
        }
    }
```

> **继承 Thread 类**

```java
    public class Show extends Thread{
        public void run(){}     // 重写执行方法
        public static void main(String args[]){
            Show T = new Show();//新建对象
            T.start();// 启动线程
        }
    }
```

> **Callable 和 Future 创建线程**

```java
    public class Show implements Callable<Integer>{
        public static void main(String[] args){
            Show C = new Show();
            FutureTask<Integer> F = new FutureTask<>(C);
            new Thread(F, "").start();// 启动线程
        }
        @Override
        public Integer call() {     //重写call()方法
            return 0;
        }
    }
```

[返回顶部](#目录)

## JDBC

#### 第一种方法

> **连接数据库**

```java
    Class.forName("com.mysql.jdbc.cj.Driver");
    Connection conn = DriverManager.getConnection(
                    "jdbc:mysql://localhost:3306/wly?useUnicode=true&
                    characterEncoding=utf8serverTimezone=UTC&
                    useSSL=false","root","000000");
```

> **Statement 接口**

```java
    Statement s = conn.createStatement();
    String sql = "sql语句";
    s.execute(sql);    //执行sql语句
```

> **PreparedStatement 接口**

```java
    PreparedStatement pstmt = conn.prepareStatement(sql);
    String sql = "sql语句";
    pstmt.setString(1, Name);  //给占位符赋值
    pstmt.executeUpdate();     //执行sql语句
```

#### 第二种方法

> **mysql.properties 文件**

```java
    driver=com.mysql.cj.jdbc.Driver
    url=jdbc:mysql://localhost:3306/wly?useUnicode=true& characterEncoding=utf8&serverTimezone=UTC&useSSL=false
    user=root
    password=000000
```

> **JDBCUtils 类**

```java
import java.io.IOException;
import java.io.InputStream;
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
import java.sql.ResultSet;
import java.sql.SQLException;
import java.util.Properties;

public class JDBCUtils {
	private static String url;
	private static String user;// 用户名
	private static String password;// 密码
	private static String driver;// 驱动类
	// 加载配置文件信息
	static {
		try {
			InputStream in = JDBCUtils.class.getClassLoader().getResourceAsStream("mysql.properties");
			Properties props = new Properties();
			props.load(in);
			driver = props.getProperty("driver");
			url = props.getProperty("url");
			user = props.getProperty("user");
			password = props.getProperty("password");
		} catch (IOException e) {
			System.out.println("数据库连接失败1");
		}
	}

	// 获取连接方法
	public static Connection getConn() {
		Connection conn = null;
		try {
			Class.forName(driver);
			conn = DriverManager.getConnection(url, user, password);
		} catch (Exception e) {
			e.printStackTrace();
		}
		return conn;
	}

	// 释放资源方法
	public static void release(Connection conn, PreparedStatement pstmt,ResultSet rs) {
		if (pstmt != null) {
			try {
				pstmt.close();
			} catch (SQLException e) {
				e.printStackTrace();
			}
		}
		if (conn != null) {
			try {
				conn.close();
			} catch (SQLException e) {
				e.printStackTrace();
			}
		}
		if (rs != null) {
			try {
				conn.close();
			} catch (SQLException e) {
				e.printStackTrace();
			}
		}
	}
}
```

> **测试类**

```java
    Connection conn = null;
    PreparedStatement pstmt = null;
    try {
    	conn = JDBCUtils.getConn();
    	String sql = "SQL语句";
    	pstmt = conn.prepareStatement(sql);
    	pstmt.executeUpdate();
    	System.out.println("执行成功");
    } catch (Exception e) {
    	System.out.println("数据库连接失败");
    } finally {
        //释放资源
    	JDBCUtils.release(conn, pstmt, null);
    }
```

[返回顶部](#目录)

### JDBC 操作

> **添加/删除/修改数据**

```java
    Statement st = null;
    String sql1 = "insert into 表名 (Name,Sex,Age) values(?,?,?)";//添加
    String sql2 = "update 表名 set Age=? where Name=?";//修改
    String sql3 = "delete from 表名 where Name=?";//删除
    try{
        st = conn.createStatement();
        st.execute(sql1);
        st.execute(sql2);
        st.execute(sql3);
    } catch (SQLException e) {
        e.printStackTrace();
    }
```

> **查询数据**

```java
    String sql = "select * from 表名";
    PreparedStatement pstmt = conn.prepareStatement(sql);
    ResultSet rs = pstmt.executeQuery();
    while(rs.next()){
       String name = rs.getString(1);
       int id = rs.getInt(2);
       int age = rs.getInt(3);
    }
```

> **批处理操作**
>
> > 使用**Statement**完成批处理

```java
    Connection conn = null;
    Statement st = null;
    ResultSet rs = null;
    try{
        conn = JdbcUtils.getConnection();
        String sql1 = "insert into testbatch(id,name) values(1,'aaa')";
        String sql2 = "insert into testbatch(id,name) values(2,'bbb')";
        String sql3 = "update testbatch set name='gacl' where id=1";
        String sql4 = "insert into testbatch(id,name) values(5,'FFF')";
        String sql5 = "delete from testbatch where id=2";
        st = conn.createStatement();
        //添加要批量执行的SQL
        st.addBatch(sql1);
        st.addBatch(sql2);
        st.addBatch(sql3);
        st.addBatch(sql4);
        st.addBatch(sql5);
        //执行批处理SQL语句
        st.executeBatch();
        //清除批处理命令
        st.clearBatch();
    }catch (Exception e) {
        e.printStackTrace();
    }finally{
        JdbcUtils.release(conn, st, rs);
    }
```

> 使用**PreparedStatement**完成批处理

```java
    Connection conn = null;
    PreparedStatement st = null;
    ResultSet rs = null;
    try{
        conn = JdbcUtils.getConnection();
        String sql = "insert into 表名(id,name)values(?,?)";
        st = conn.prepareStatement(sql);
        for(int i=1; i<1000; i++){
            st.setInt(1, i);
            st.setString(2, "n" + i);
            st.addBatch();
            if(i%100==0){
                st.executeBatch();//执行批处理SQL语句
                st.clearBatch();//清除批处理命令
            }
        }
        st.executeBatch();
    }catch (Exception e) {
        e.printStackTrace();
    }finally{
        JdbcUtils.release(conn, st, rs);
    }
```

[返回顶部](#目录)
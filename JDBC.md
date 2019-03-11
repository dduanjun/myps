---
date: 2019-03-10 17:30
status: public
title: JDBC
---

# JDBC技术
## 1.简介
__JDBC__(Java DataBase Connection)一套用于执行`SQL语句`的Java API
## 2.JDBC访问数据库的步骤
- 导入`java.sql`包
- 加载数据库驱动程序
- 定义数据库的连接地址，用户名和密码
- 得到与数据库的链接对象
- 声明SQL语句
- 得到语句对象
- 执行SQL语句
- 处理SQL语句的返回结果
- 关闭对象

```java
import java.sql.*;
Class.forName = ("com.mysql.jdbc.Driver");
String url = "jdbc:mysql://host:port/dbName";
String username = "root";
String passworld = "root";
Connection con = DriverManager.getConnection(url,username,password);
String sql = "select * from bookinf";
Statement stmt = con.createStatement();
ResultSet rs = stmt.executeQuery(sql);

PreparedStatement pstmt = con.preparedStatement(sql);
pstmt.setString(1,"ss");
pstmt.setFloat(2,Float.parseFloat(price));
ResultSet rs = pstmt.executeQuery();
int result = pstmt.executeUpdate();//update

while(rs.(next)){
  int id = rs.getInt(1);
  String bookname = rs.getString(2);
}

rs.close();
stmt.close();
con.close();
```

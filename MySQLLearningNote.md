# MySQL Learning Note

## 安装与配置
   * 安装
       + 官网参考
       + 参考
   * 配置
       + 官网参考
       + 参考
## 数据库管理
   * 数据库启动与停止
      + 启动
         * 方法一
         ```sql
       
         ```
      + 停止
         * 方法一
         ```sql
       
         ```
   * 数据库连接
      + 本地连接
      + 远程连接
      ```sql
          CREATE USER 'root'@'192.168.1.6' IDENTIFIED BY 'root123'; # 创建用户
          GRANT ALL PRIVILEGES ON *.* TO 'root'@'192.168.1.6'; # 赋予用户权限
       
       # 成功后会出现这行代码
       # Query OK, 0 rows affected (0.02 sec)
      ```
   * 用户管理
      + 密码设置
      ```sql
          shell> mysql -u root
          mysql> UPDATE mysql.user SET Password = PASSWORD('newpwd') WHERE User = 'root';
          mysql> FLUSH PRIVILEGES;

          shell> mysqladmin -u root password "newpwd" -- mysqladmin: [Warning] Using a password on the command line interface can be insecure.
          shell> mysqladmin -u root -h host_name password "newpwd"
      ```
## 数据库操作
   * 创建数据库
      + 创建脚本
      ```sql
          CREATE database testdb
      ```
   * 创建表
   * 创建索引

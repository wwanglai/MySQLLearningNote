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
         ./mysqld --datadir=/Users/jennywang/data/mysqldatadev/data_8.0.19 --console # 使用指定数据库
         ./mysqld --console # 使用默认的数据库，顺序详见MySQL书本第
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
      ```sql
          # 只有一个MySql实例的时候使用下面的语句
          mysql -u root -p;
          # 服务器端有多个sql实例
          mysql -u root -p --socket=/tmp/mariadb.sock;
          mysql -u root -p --socket=/tmp/mariadb_3305.sock; # 服务器端有多个sql实例，端口模式
          也可以：
          mysql -u root -p -P3305     -- 说明：-P表示端口；-p表示是Password
          mysql -u root -p -h 192.168.0.104 -P 3307
          是否成功
          不成功
          是否忘记
          初始密码
          是
          Reset the Root Password
          B.5.3.2 How to Reset the Root Password
          步骤
          1.
          Log on to your system as Administrator.
          2.
          Stop the MySQL server if it is running.
          3.
          Create a text file containing the password-assignment statement on a single line.
          E:\Softwares\Oracle\Database\MySQL\mysql-init.txt
          # MySQL 5.7.6 and later:
          ALTER USER 'root'@'localhost' IDENTIFIED BY 'root123';
          4.
          Open a console window to get to the command prompt
          5. 
          Start the MySQL server with the special --init-file option (notice that the backslash in the option value is doubled):
          步骤
          1.可以先进入目录
          C:\> cd "E:\Softwares\Oracle\Database\MySQL\mysql-8.0.13-winx64\bin"
          2. 
          方法 1
          mysqld --init-file=E:/Softwares/Oracle/Database/MySQL/mysql-init.txt
          方法 2
          推荐，已经设置了MYSQL_HOME,可以直接运行命令
          E:\> mysqld --init-file=E:\\Softwares\\Oracle\\Database\\MySQL\\mysql-init.txt
          否
          成功
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
   
## 数据库维护
   # 数据库测试命令
   ```sql
        Checking&Query The Server
        2.9.3 Testing the Server
        shell> bin/mysqladmin version
        shell> bin/mysqladmin variables
        mysqladmin version status proc
        shell> bin/mysqladmin -u root -p version
        Enter password: (enter root password here)
        shell> bin/mysqlshow
        shell> bin/mysqlshow mysql

        mysqlshow -u root mysql
        shell> bin/mysql -e "SELECT User, Host, plugin FROM mysql.user" mysql
   ```

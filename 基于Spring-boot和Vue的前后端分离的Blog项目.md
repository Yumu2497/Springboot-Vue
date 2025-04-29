# 前期准备
## 软件安装以及环境配置
### 安装Java
1. 打开Java下载网址[Java Downloads | Oracle 中国](https://www.oracle.com/cn/java/technologies/downloads/)
2. ![](https://pic1.imgdb.cn/item/680e34a158cb8da5c8d054b9.png)
   如果想下载其他版本请自行在网上搜索
3. 等待下载完成后安装
   
   ![](https://pic1.imgdb.cn/item/680e34a158cb8da5c8d054b5.png)
   
   下一步
   
   ![](https://pic1.imgdb.cn/item/680e34a158cb8da5c8d054b7.png)
   
   选择是否更换安装目录，建议默认即可，如果你C盘空间够的话。
   ==请记住你的安装目录！请记住你的安装目录！请记住你的安装目录！==
   安装完成
5. 配置Java环境变量
   按住快捷键Win+Q
   搜索“编辑系统环境变量”
   
   ![](https://pic1.imgdb.cn/item/680e34a158cb8da5c8d054ba.png)

   ![](https://pic1.imgdb.cn/item/680e34a158cb8da5c8d054b6.png)
   
   ![](https://pic1.imgdb.cn/item/680e34a158cb8da5c8d054b8.png)
   
   变量名：JAVA_HOME
   变量值：**你自己的JAVA安装目录**
   点击 确定
   
   ![](https://pic1.imgdb.cn/item/680e358358cb8da5c8d05548.png)
  
   找到PATH，双击打开
   
   ![](https://pic1.imgdb.cn/item/680e358358cb8da5c8d0554b.png)
   
   新建并填写  %JAVA_HOME%\bin
   
   ![](https://pic1.imgdb.cn/item/680e362958cb8da5c8d0559e.png)
   
   填写完后全部确定
7. 快捷键Win+R,运行cmd
   
   ![](https://pic1.imgdb.cn/item/680e358358cb8da5c8d0554a.png)
   
   在cmd中输入  javac -version
   
   ![](https://pic1.imgdb.cn/item/680e358358cb8da5c8d05549.png)
   
   若正确输出版本号则环境配置正确
   
### 安装开发工具（VSCode/IDEA)
选择你自己喜欢的
VSCode：

[Download Visual Studio Code - Mac, Linux, Windows](https://code.visualstudio.com/Download)

安装与你系统对应的版本

![](https://pic1.imgdb.cn/item/680e364a58cb8da5c8d055b0.png)

IDEA： [下载 IntelliJ IDEA](https://www.jetbrains.com/zh-cn/idea/download/?section=windows)
   
选择免费的社区版
  
![](https://pic1.imgdb.cn/item/680e364a58cb8da5c8d055b3.png)

### 安装MySQL数据库
安装
-[MySQL Community Server](https://dev.mysql.com/downloads/mysql/)
![](https://pic1.imgdb.cn/item/680e364a58cb8da5c8d055b1.png)
![](https://pic1.imgdb.cn/item/680e364b58cb8da5c8d055b5.png)
-[MySQL Workbench](https://dev.mysql.com/downloads/workbench/)
![](https://pic1.imgdb.cn/item/680e364a58cb8da5c8d055b2.png)
一定要先安装- [MySQL Community Server](https://dev.mysql.com/downloads/mysql/)再安装- [MySQL Workbench](https://dev.mysql.com/downloads/workbench/)
==安装 [MySQL Community Server](https://dev.mysql.com/downloads/mysql/)过程中会让你输入password，请你务必记住你自己的password==
### 安装Maven
打开[Download Apache Maven – Maven](https://maven.apache.org/download.cgi)
选择并安装
![](https://pic1.imgdb.cn/item/680e36d858cb8da5c8d055f9.png)
==将你下载的压缩包解压，并记住解压目录==
配置Maven环境变量
![](https://pic1.imgdb.cn/item/680e36ee58cb8da5c8d05604.png)
![](https://pic1.imgdb.cn/item/680e370758cb8da5c8d05613.png)
双击Path
![](https://pic1.imgdb.cn/item/680e371258cb8da5c8d05619.png)
填写  %MAVEN_HOME%\bin
![](https://pic1.imgdb.cn/item/680e371d58cb8da5c8d05620.png)
全部点击确定
打开cmd，输入 mvn -v
![](https://pic1.imgdb.cn/item/680e372658cb8da5c8d05622.png)
若正确出现版本，则环境配置完成
## 构建Spring-boot项目
### 利用官方在线工具
打开[Spring Initializr](https://start.spring.io/)
![](https://pic1.imgdb.cn/item/680e373f58cb8da5c8d0562e.png)
将下载下来的框架解压到你的工作目录，可以自己专门创建一个
![](https://pic1.imgdb.cn/item/680e375058cb8da5c8d0563a.png)
打开IDEA，打开你的项目文件
![](https://pic1.imgdb.cn/item/680e376e58cb8da5c8d05645.png)或是直接将文件拖动到IDEA或VSCode图标上
例如
![](https://pic1.imgdb.cn/item/680e387258cb8da5c8d056c3.png)
### 更换IDEA的Maven主路径为自己下载的
打开设置，如图操作
![](https://pic1.imgdb.cn/item/680e3f6e58cb8da5c8d05adf.png)
### 为Maven更换阿里镜像源
打开 `C:\Users\你的用户名\.m2\settings.xml` 
一般settings.xml都在这里
或者
右键IDEA里的pom.xml文件
![](https://pic1.imgdb.cn/item/680e3c3d58cb8da5c8d05930.png)
也可以打开setting.xml

==将你的setting.xml原本的内容删完，填写以下内容==
```
<?xml version="1.0" encoding="UTF-8"?>  
<settings xmlns="http://maven.apache.org/SETTINGS/1.0.0"  
          xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
          xsi:schemaLocation="http://maven.apache.org/SETTINGS/1.0.0 http://maven.apache.org/xsd/settings-1.0.0.xsd">  
    <mirrors>        <!-- 阿里云镜像 -->  
        <mirror>  
            <id>aliyunmaven</id>  
            <mirrorOf>central</mirrorOf>  
            <name>阿里云公共仓库</name>  
            <url>https://maven.aliyun.com/repository/public</url>  
        </mirror>
	</mirrors>
</settings>
```
![](https://pic1.imgdb.cn/item/680e3bb058cb8da5c8d058d4.png)
### 为项目选择JDK24
打开项目结构
![](https://pic1.imgdb.cn/item/680e427e58cb8da5c8d05ccf.png)
选择刚刚自己下载的Java24，应用并确定
![](https://pic1.imgdb.cn/item/680e42ba58cb8da5c8d05ce4.png)
### 安装spring-boot-starter-web依赖
打开你的pom.xml文件
找到`<dependencies></dependencies>`包裹的内容
![](https://pic1.imgdb.cn/item/680e3df658cb8da5c8d05a1f.png)
添加以下代码
```pom.xml
<dependency>  
    <groupId>org.springframework.boot</groupId>  
    <artifactId>spring-boot-starter-web</artifactId>  
</dependency>
```
添加完后请记得同步Maven更改，==切记切记切记，以后每次更改pom.xml都要进行这一步==
![](https://pic1.imgdb.cn/item/680e3e8a58cb8da5c8d05a76.png)
如果你没有找到右上角的按钮，请右键pom.xml --> Maven --> 同步项目
![](https://pic1.imgdb.cn/item/680e400858cb8da5c8d05b3f.png)

# 编写你的后端
## 创造你的第一个控制器
接下来便可以正式写代码了
右键com.example.demo，新建一个名为 controller 的软件包
![](https://pic1.imgdb.cn/item/680e431a58cb8da5c8d05d18.png)
==你无需删除前面的com.example.demo，接着在后面填写contorller== 然后回车
![](https://pic1.imgdb.cn/item/680e436b58cb8da5c8d05d33.png)
右键controller，新建一个Java类
![](https://pic1.imgdb.cn/item/680e493f58cb8da5c8d05fa6.png)
填写HelloController，回车
![](https://pic1.imgdb.cn/item/680e495b58cb8da5c8d05fca.png)
依据传统，我们写一个Hello，World！
```Java
package com.example.demo.controller;  
  
import org.springframework.web.bind.annotation.GetMapping;  
import org.springframework.web.bind.annotation.RestController;  
  
@RestController("/")  
public class HelloController {  
    @GetMapping  
    public String Hello() {  
        return "Hello, World!";  
    }  
}
```
![](https://pic1.imgdb.cn/item/680e450458cb8da5c8d05db6.png)
其中
`@RestController("/")`是一个组合注解，它结合了`@Controller`和`@ResponseBody`两个注解的功能。
1. **标记为控制器**：告诉Spring这个类是一个控制器，可以处理HTTP请求
2. **自动JSON转换**：所有方法的返回值都会自动转换为JSON格式响应
3. **路径映射**：括号中的`"/"`表示这个控制器映射到根路径

`@GetMapping`是一个专门处理HTTP GET请求的注解。
1. **处理GET请求**：只响应HTTP GET方法的请求
2. **路径映射**：可以指定路径，如果不指定则使用类级别的路径
3. **简洁易用**：比传统的`@RequestMapping(method = RequestMethod.GET)`更简洁

运行你的项目
![](https://pic1.imgdb.cn/item/680e469e58cb8da5c8d05e67.png)
或者右键项目主文件，DemoApplication.java
![](https://pic1.imgdb.cn/item/680e46ba58cb8da5c8d05e71.png)
当终端出现这些字样代表运行成功，然后在浏览器的地址栏输入`localhost:8080`,冒号后面的端口号8080请注意终端中的提示，如果你和我不一样，请自行修改端口号，不过默认都是8080
![](https://pic1.imgdb.cn/item/680e470358cb8da5c8d05ea1.png)
这时你的浏览器应该会出现Hello，World！字样，代表你成功运行了你的第一个控制器。
![](https://pic1.imgdb.cn/item/680e479f58cb8da5c8d05ef2.png)
## 创建你的数据库
快捷键Win+Q，搜索MySQL并打开MySQL 9.2 Command Line Client
![](https://pic1.imgdb.cn/item/680e4c6658cb8da5c8d060b9.png)
输入你的密码，密码是在MYSQL安装过程中设置的，[跳转到MYSQL的安装](#安装MySQL数据库)
![](https://pic1.imgdb.cn/item/680e4cde58cb8da5c8d060d8.png)
输入SQL命令：`CREATE DATABASE blog CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;`
并回车
![](https://pic1.imgdb.cn/item/680f099358cb8da5c8d14aa4.png)
输入：`SHOW DATABASES;`来列出所有数据库，会发现已经有了blog。
![](https://pic1.imgdb.cn/item/680f0a0558cb8da5c8d14ceb.png)
创建用户并设置密码：`CREATE USER 'blog_user'@'%' IDENTIFIED BY '123456';`
在这里的用户名是`blog_user`，密码是`123456`。你也可以按自己想的修改用户名与密码。
授予用户对blog数据库的所有权限：`GRANT ALL PRIVILEGES ON blog.* TO 'blog_user'@'%';`
最后刷新权限：`FLUSH PRIVILEGES;`

快捷键Win+Q，搜索MySQL并打开Workbench
![](https://pic1.imgdb.cn/item/680f0c5858cb8da5c8d171cd.png)
点击+号按钮
![](https://pic1.imgdb.cn/item/680f0cfc58cb8da5c8d17bf4.png)
填写信息
![](https://pic1.imgdb.cn/item/680f0de558cb8da5c8d186e8.png)
这时你的主页会出现这个数据库，单击打开
![](https://pic1.imgdb.cn/item/680f0e5058cb8da5c8d1898e.png)

按图所示创建user表
![](https://pic1.imgdb.cn/item/680f130758cb8da5c8d18f16.png)
![](https://pic1.imgdb.cn/item/680f133d58cb8da5c8d18f2f.png)
打开user表并随便填写一些假数据
![](https://pic1.imgdb.cn/item/680f14d958cb8da5c8d18fc9.png)
至此你已经成功创建了你的user表

## 连接你的数据库
安装MySQL依赖
[Maven Repository: com.mysql » mysql-connector-j » 9.2.0](https://mvnrepository.com/artifact/com.mysql/mysql-connector-j/9.2.0)
```xml
<dependency>
    <groupId>com.mysql</groupId>
    <artifactId>mysql-connector-j</artifactId>
    <version>9.2.0</version>
</dependency>
```

打开application.properties，配置数据库连接
注意要在spring.datasource.url=jdbc:mysql://localhost:3306/后填写自己的数据库名，
spring.datasource.username=数据库用户
spring.datasource.password=这里填写密码
```properties
# MySQL数据库连接配置  
spring.datasource.url=jdbc:mysql://localhost:3306/blog  
spring.datasource.username=blog_user  
spring.datasource.password=这里填写密码  
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver
```
![](https://pic1.imgdb.cn/item/680f4be558cb8da5c8d250be.png)
## 将后端与你的数据库关联起来
新建软件包entity，并创建一个User类，其中User类和user表同名，可以不区分大小写，因为类名命名规则通常都是首字母大写的驼峰命名法则。
![](https://pic1.imgdb.cn/item/680f161b58cb8da5c8d1950e.png)

到此我们需要安装Lombok依赖，用于减少样板代码，提高开发效率。
在此我推荐去相关依赖的官网，找到最新版本的依赖导入方式，否则会出现各种奇奇怪怪的报错。
Lombok官网Maven依赖导入：[Maven](https://projectlombok.org/setup/maven)、
找到这两段代码。
![](https://pic1.imgdb.cn/item/680f17c958cb8da5c8d197ba.png)
```xml
<dependency>
	<groupId>org.projectlombok</groupId>
	<artifactId>lombok</artifactId>
	<version>1.18.38</version>
	<scope>provided</scope>
</dependency>
```
```xml
<plugin>
	<groupId>org.apache.maven.plugins</groupId>
	<artifactId>maven-compiler-plugin</artifactId>
	<configuration>
		<annotationProcessorPaths>
			<path>
				<groupId>org.projectlombok</groupId>
				<artifactId>lombok</artifactId>
				<version>1.18.38</version>
			</path>
		</annotationProcessorPaths>
	</configuration>
</plugin>
```
==请注意，找到对应的地方，一个是`<dependency></dependency>`，一个是`<plugin></plugin>` ==
![](https://pic1.imgdb.cn/item/680f196558cb8da5c8d19c30.png)
导入依赖后不要忘记同步一下Maven更改
在设置里找到插件并下载lombok插件
![](https://pic1.imgdb.cn/item/680f1aa558cb8da5c8d1a7c2.png)
点击构建、执行、部署 -> 编译器 -> 注解处理器 -> 启用注解处理 ->确定
![](https://pic1.imgdb.cn/item/680f1af358cb8da5c8d1aa72.png)
接下来回到User类继续编写。
```Java
package com.example.demo.entity;  
  
import lombok.Data;  
  
@Data  
public class User {  
    private Integer id;  
    private String username;  
    private String password;  
}
```
在这里，我们使用了Lombok的Data注解，自动为id，username，password这些声明生成了**对应的操作方法**（如 `getter`、`setter`、`toString()`、`equals()`/`hashCode()` 等）
我们只需声明变量，无需手动编写对应方法，提高了开发效率。
这里的id，username，password和user表的内容会自动一一对应。
> **请注意**，MySQL里的命名方式采用下划线命名，而Java采用驼峰命名。
> 如果MySQL里的命名是user_name，则Java里要写成userName。当然你也可以手动映射对应，用@Column(username = "user_name")注解来解决，更多其他方法请自行查找，在此不过多赘述。

## 在后端执行对应的数据库操作
数据库操作这块也有一个依赖可以方便我们提高开发效率
**MyBatis-Plus**：[安装 | MyBatis-Plus](https://baomidou.com/getting-started/install/)
找到Spring Boot3对应的依赖,并添加到pom.xml中，之前已经演示过很多次在此不做赘述。
```xml
<dependency>
    <groupId>com.baomidou</groupId>
    <artifactId>mybatis-plus-spring-boot3-starter</artifactId>
    <version>3.5.12</version>
</dependency>
```
![](https://pic1.imgdb.cn/item/680f267f58cb8da5c8d1ce62.png)
创建一个新的软件包mapper，并创建一个UserMapper接口，==注意是接口==
![](https://pic1.imgdb.cn/item/680f276158cb8da5c8d1d34d.png)
在UserMapper中写入
```Java
package com.example.demo.mapper;  
  
import com.baomidou.mybatisplus.core.mapper.BaseMapper;  
import com.example.demo.entity.User;  
  
public interface UserMapper extends BaseMapper<User> {  
      
}
```
**我们的UserMapper继承了mybatisplus的BaseMapper，BaseMapper已经包含了许多常用的CRUD（增删改查）操作，无需我们手动写SQL代码，可直接操作 User 实体对应的数据库表**。
**如果你有其他操作需求，可自行在UserMapper里添加代码。**

在DemoApplication.java主文件添加`@MapperScan("com.example.demo.mapper")`
![](https://pic1.imgdb.cn/item/680f442d58cb8da5c8d24c9d.png)
`@MapperScan("com.example.demo.mapper")`会自动将com.example.demo.mapper目录下的所有mapper类添加@Mapper注解。
@Mapper的作用是**标识一个接口是 MyBatis 的 Mapper 接口**，并告诉 MyBatis 需要为这个接口生成动态代理实现类，从而能够执行 SQL 操作。
## 利用Thymeleaf将数据展示到前端浏览器

安装Thymeleaf依赖
[Maven Repository: org.springframework.boot » spring-boot-starter-thymeleaf » 3.4.5](https://mvnrepository.com/artifact/org.springframework.boot/spring-boot-starter-thymeleaf/3.4.5)
```xml
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-thymeleaf</artifactId>
</dependency>
```
可以省略`<version>`， 会自动继承`<parent></parent>`里的Spring Boot的版本

接着我们来编写UserController控制器
```Java
package com.example.demo.controller;  
  
import com.example.demo.entity.User;  
import com.example.demo.mapper.UserMapper;  
import org.springframework.beans.factory.annotation.Autowired;  
import org.springframework.stereotype.Controller;  
import org.springframework.ui.Model;  
import org.springframework.web.bind.annotation.GetMapping;  
  
import java.util.List;  
  
@Controller  
public class UserController {  
    @Autowired  
    private UserMapper userMapper;  
  
    @GetMapping("/alluser")  
    public String alluser(Model model) {  
        List<User> userList = userMapper.selectList(null);  
        model.addAttribute("userList", userList);  
        return  "alluser";  
    }  
}
```
`@Autowired` 是 Spring 的依赖注入注解，用于自动装配 Bean。
这里 Spring 会自动查找 `UserMapper` 类型的 Bean 并注入到 `userMapper` 字段中。
`@GetMapping` 是 Spring MVC 的请求映射注解，专门处理 HTTP GET 请求。
`Model` 是 Spring MVC 提供的一个接口，用于在控制器和视图之间传递数据。
`model.addAttribute("userList", userList);`这将 `userList` 数据添加到模型中，可以在视图中通过 `${userList}` 或 Thymeleaf 的 `th:each` 访问。

![](https://pic1.imgdb.cn/item/680f53dd58cb8da5c8d2544d.png)
接着写一个网页
```html
<!DOCTYPE html>  
<html xmlns:th="http://www.thymeleaf.org">  
    <head>        
	    <meta charset="UTF-8">  
        <meta name="viewport" content="width=device-width, initial-scale=1.0">  
        <title>Document</title>  
    </head>  
    <body>        
	    <p style="text-align: center;">用户列表</p>  
        <div style="padding: 0 10%">  
            <p style="width: 33%;float: left;">ID</p>  
            <p style="width: 33%;float: left;">用户名</p>  
            <p style="width: 33%;float: left;">密码</p>  
        </div>        
        <div style="padding: 0 10%" th:each="user : ${userList}">  
            <p style="width: 33%;float: left;" th:text="${user.id}"></p>  
            <p style="width: 33%;float: left;" th:text="${user.username}"></p>  
            <p style="width: 33%;float: left;" th:text="${user.password}"></p>  
        </div>    
	</body>
</html>
```
`th:each="user : ${userList}`就像Python 里的`for user in userList`一样，我们可以用 . 符号取出user里的id，username，password等属性。

在resources里创建一个templates文件夹，创建一个alluser.html,这里的alluser与控制器返回的要对应

![](https://pic1.imgdb.cn/item/680f55a558cb8da5c8d254f5.png)

接着我们来运行一下

打开浏览器并在网址栏输入localhost:8080/alluser
![](https://pic1.imgdb.cn/item/680f567958cb8da5c8d25561.png)
可以发现我们取出了数据库里的所有user并展示在了浏览器上
# 正式进行前后端分离

## 安装Node.js

我们需要Node.js来构建Vue

在此我推荐用nvm来管理Node.js版本，nvm对于Node.js就像anaconda对于Python一样。

当你需要在多个Node.js版本之间切换时，nvm会很有用，如果你不需要，请在[Node.js官网](https://nodejs.org/zh-cn/download)下载偶数版本，推荐20,18

如果使用nvm，则需要卸载之前安装过的Node.js，没安装过则可以忽略。
选择nvm，[开始 下载nvm - nvm中文官网](https://nvm.uihtm.com/doc/download-nvm.html)
本地下载最新版。解压安装程序并运行。安装流程不多赘述，不过要记住安装时选择的目录。
==一共有两个目录，一个是nvm目录，一个是Node.js目录==
**配置nvm环境**
打开系统环境变量，配置NVM_HOME，填写nvm目录，配置NVM_SYMLINK，填写Node.js目录
![](https://pic1.imgdb.cn/item/680f858758cb8da5c8d26568.png)
然后在path里添加%NVM_HOME%与%NVM_SYMLINK%
![](https://pic1.imgdb.cn/item/680f860558cb8da5c8d2658f.png)
快捷键Win+R，打开CMD，输入nvm -v，正确出现版本则安装完成
![](https://pic1.imgdb.cn/item/680f868358cb8da5c8d265c5.png)
输入`nvm list available` 列出可安装的版本
![](https://pic1.imgdb.cn/item/680f86d958cb8da5c8d265e5.png)
选择LTS列下的偶数版本
输入`nvm install 版本号`进行安装
安装完成之后输入`node -v`与`npm -v`进行验证，出现版本号则安装完成
![](https://pic1.imgdb.cn/item/680f87ba58cb8da5c8d26635.png)
## 选择前端框架Vue
创建一个新的空文件夹来开始进行Vue的搭建
进入VSCode，打开这个空文件夹，打开终端输入`npm create vite@latest ./ -- --template vue-ts`，之后左边会出现一堆文件。根据它的提示依次输入`npm install`，`npm run dev`
最后Ctrl+鼠标左键，点击蓝色的地址。
![](https://pic1.imgdb.cn/item/680f8bf458cb8da5c8d26848.png)
便会得到这样一个页面
![](https://pic1.imgdb.cn/item/680f8c5c58cb8da5c8d26878.png)
在VSCode插件商店搜索Vue安装官方插件
![](https://pic1.imgdb.cn/item/680f8cd458cb8da5c8d268b8.png)

## 实现登录与注册


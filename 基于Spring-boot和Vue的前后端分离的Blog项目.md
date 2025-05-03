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
	@TableId(type = IdType.AUTO)
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
==一共有两个目录，一个是nvm目录，一个是Nodejs目录==
**配置nvm环境**
打开系统环境变量，配置NVM_HOME，填写nvm目录，配置NVM_SYMLINK，填写Nodejs目录
![](https://pic1.imgdb.cn/item/680f858758cb8da5c8d26568.png)
然后在path里添加%NVM_HOME%与%NVM_SYMLINK%
![](https://pic1.imgdb.cn/item/680f860558cb8da5c8d2658f.png)
快捷键Win+R，打开CMD，输入nvm -v，正确出现版本则安装完成
![](https://pic1.imgdb.cn/item/680f868358cb8da5c8d265c5.png)
输入`nvm list available` 列出可安装的版本
![](https://pic1.imgdb.cn/item/680f86d958cb8da5c8d265e5.png)
选择LTS列下的偶数版本
输入`nvm install 版本号`进行安装
然后输入 `nvm use 版本号` 启用这个版本
启用完成之后输入`node -v`与`npm -v`进行验证，出现版本号则安装完成
![](https://pic1.imgdb.cn/item/680f87ba58cb8da5c8d26635.png)
## 选择前端框架Vue

先了解一下Vue和单页面应用。
**Vue.js**（简称 Vue）是一个用于构建用户界面的 **渐进式 JavaScript 框架**
**单页面应用（Single Page Application, SPA）** 是一种 Web 应用模式，整个应用只有一个 HTML 页面，通过动态加载内容（如 JavaScript）实现页面切换，**无需重新加载整个页面**。

创建一个新的空文件夹来开始进行Vue的搭建
进入VSCode，打开这个空文件夹，打开终端输入`npm create vite@latest ./ -- --template vue-ts`，之后左边会出现一堆文件。根据它的提示依次输入`npm install`，`npm run dev`
最后Ctrl+鼠标左键，点击蓝色的地址。
以后每次运行都可以在对应的目录下输入`npm run dev`
![](https://pic1.imgdb.cn/item/680f8bf458cb8da5c8d26848.png)
便会得到这样一个页面
![](https://pic1.imgdb.cn/item/680f8c5c58cb8da5c8d26878.png)
在VSCode插件商店搜索Vue安装官方插件
![](https://pic1.imgdb.cn/item/680f8cd458cb8da5c8d268b8.png)

## 安装第三方库
安装element
[安装 | Element Plus](https://element-plus.org/zh-CN/guide/installation.html)
element提供了开箱即用的各种组件，可以拿来就用而不用自己写，如果你想要其他的组件库请自行寻找
在终端输入`npm install element-plus --save`
![](https://pic1.imgdb.cn/item/6810c8bf58cb8da5c8d46806.png)

在全局注册element
打开main.ts，写入
```ts
import { createApp } from 'vue'
import './style.css'
import App from './App.vue'
import ElementPlus from 'element-plus'
import 'element-plus/dist/index.css'

const app = createApp(App)
app.use(ElementPlus)
app.mount('#app')
```
![](https://pic1.imgdb.cn/item/6810d33d58cb8da5c8d46c40.png)

安装router
Vue Router 是 Vue.js 官方的路由管理器，它与 Vue.js 核心深度集成，让构建单页面应用(SPA)变得轻而易举。
终端输入`npm install vue-router@4`
![](https://pic1.imgdb.cn/item/6810cdf758cb8da5c8d46a2c.png)

安装axios
Vue 版本推荐使用 axios 来完成 ajax 请求。
Axios 是一个基于 Promise 的 HTTP 库，可以用在浏览器和 node.js 中。
终端输入`npm install axios`
![](https://pic1.imgdb.cn/item/6810d15d58cb8da5c8d46ba1.png)
## 实现登录与注册

### 创建一个登录视图
在创建登录注册View之前，先把它自带的样式删干净。
找到src目录下的style.css,全部删除
![](https://pic1.imgdb.cn/item/6810b95458cb8da5c8d460bd.png)
找到App.vue，删除 template 和 style 里的内容
![](https://pic1.imgdb.cn/item/6810bf4658cb8da5c8d46360.png)
使用Vue在你更改内容后会实时热更新网页上的内容，十分便捷直观。
当你删完之后你应该会发现页面一片空白了

现在开始创建登录视图
在src下新建views，创建Login.vue
![](https://pic1.imgdb.cn/item/6810d51158cb8da5c8d46cc9.png)
```vue
<template>
    <div class="login-container">
        <el-card class="login-card">
            <div class="login-header">
                <h2>登录</h2>
            </div>
            
            <el-form ref="loginFormRef" :model="loginForm" :rules="loginRules" class="login-form"
                @submit.prevent="handleLogin">
                <el-form-item prop="username">
                    <p>用户名：</p>
                    <el-input v-model="loginForm.username" placeholder="请输入用户名" prefix-icon="User" />
                </el-form-item>
                <el-form-item prop="password">
                    <p>密码：</p>
                    <el-input v-model="loginForm.password" type="password" placeholder="请输入密码" prefix-icon="Lock"
                        show-password />
                </el-form-item>
                <el-form-item prop="remember" class="remember-me">
                    <el-checkbox v-model="loginForm.remember">记住我</el-checkbox>
                </el-form-item>
                <el-form-item>
                    <el-button type="primary" class="login-btn" native-type="submit" :loading="loading">登录</el-button>
                </el-form-item>
            </el-form>
            <div class="login-footer">
                <el-link type="primary" @click="forgetDialogVisible = true">忘记密码?</el-link>
                <el-link type="primary" @click="registerDialogVisible = true">注册账号</el-link>
            </div>
        </el-card>
        <!-- 忘记密码对话框 -->
        <el-dialog v-model="forgetDialogVisible" title="忘记密码" width="30%">
            <span>请联系系统管理员重置密码</span>
            <template #footer>
                <el-button @click="forgetDialogVisible = false">关闭</el-button>
            </template>
        </el-dialog>

  

        <!-- 注册对话框 -->
        <el-dialog v-model="registerDialogVisible" title="注册账号" width="30%">
            <span>请联系系统管理员创建账号</span>
            <template #footer>
                <el-button @click="registerDialogVisible = false">关闭</el-button>
            </template>
        </el-dialog>
    </div>
</template>

<script setup>
import { ref, reactive } from 'vue'
import { ElMessage } from 'element-plus'
import { useRouter } from 'vue-router'
  
const router = useRouter()

// 表单引用
const loginFormRef = ref(null)
  
// 响应式数据
const loginForm = reactive({
    username: '',
    password: '',
    remember: false
})

const loading = ref(false)
const forgetDialogVisible = ref(false)
const registerDialogVisible = ref(false)
  
// 验证规则
const loginRules = reactive({
    username: [
        { required: true, message: '请输入用户名', trigger: 'blur' },
        { min: 3, max: 20, message: '长度在 3 到 20 个字符', trigger: 'blur' }
    ],
    password: [
        { required: true, message: '请输入密码', trigger: 'blur' },
        { min: 6, max: 20, message: '长度在 6 到 20 个字符', trigger: 'blur' }
    ]
})
  
// 登录方法
const handleLogin = async () => {
    try {
        // 验证表单
        const valid = await loginFormRef.value.validate()
        if (!valid) return
        loading.value = true
        // 这里替换为实际的登录API调用
        // const response = await axios.post('/api/login', loginForm)

        // 模拟登录成功
        await new Promise(resolve => setTimeout(resolve, 1000))

        ElMessage.success('登录成功')
        router.push('/')
    } catch (error) {
        ElMessage.error(error.response?.data?.message || '登录失败')
    } finally {
        loading.value = false
    }
}

</script>

<style scoped>

.login-container {
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    background-color: #f5f7fa;
}
  
.login-card {
    width: 400px;
    padding: 20px;
    border-radius: 5px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

.login-header {
    text-align: center;
    margin-bottom: 30px;
}

.login-header h2 {
    color: #409EFF;
}

.login-form {
    margin-top: 20px;
}
.login-btn {
    width: 50%;
    margin: 0 auto;
}

.login-footer {
    display: flex;
    justify-content: space-between;
    margin-top: 10px;
}
</style>
```

这仅仅是一个最基础的框架，还没有实现任何功能

### 实现路由
首先安装@types/node
![](https://pic1.imgdb.cn/item/6810dbd958cb8da5c8d4706c.png)
修改vite.config.ts
```ts
import { defineConfig } from 'vite'
import vue from '@vitejs/plugin-vue'
import path from 'path'

export default defineConfig({
  plugins: [vue()],
  resolve: {
    alias: {
      '@': path.resolve(__dirname, './src')
    }
  }
})
```
![](https://pic1.imgdb.cn/item/6810dc7458cb8da5c8d472e7.png)
在src下创建新文件shims-vue.d.ts
```ts
declare module '*.vue' {
    import { DefineComponent } from 'vue'
    const component: DefineComponent<{}, {}, any>
    export default component
}
```
![](https://pic1.imgdb.cn/item/6810dd2858cb8da5c8d47bbf.png)
创建路由
在src下创建新文件夹router，在里面创建index.ts

```ts
import { createRouter, createWebHistory } from "vue-router";

const router = createRouter({
    history: createWebHistory(),
    routes: [
        {
            path: '/login',
            name: 'Login',
            component: () => import('@/views/Login.vue'),
        }
    ]
})

export default router
```

![](https://pic1.imgdb.cn/item/6810dd9858cb8da5c8d48376.png)
在main.ts里全局使用router
写入`import router from './router'` 和 `app.use(router)`
![](https://pic1.imgdb.cn/item/6810de3d58cb8da5c8d48e4f.png)
在App.vue里加入`<router-view />`
![](https://pic1.imgdb.cn/item/6810de9358cb8da5c8d493ab.png)

现在我们打开浏览器，输入 http://localhost:5173/login 就可以看见我们刚刚写的登录视图了

### 实现前后端Api对接
创建前端Api
在src下创建新文件api，创建新文件index.js

```ts
import axios from 'axios';

// 创建axios实例
const api = axios.create({
  baseURL: 'http://localhost:8080', // SpringBoot后端API基础URL
  timeout: 5000
});

export default api;
```
![](https://pic1.imgdb.cn/item/6810ecef58cb8da5c8d4a376.png)
创建新文件LoginApi.ts，这个方法可以将用户名与密码传给后端
```ts
import api from '@/api'

// 用户登录
export function login(username: string, password: string) {
  return api.post('/user/login', {
    username,
    password
  })
}
```

接下来打开IDEA
首先实现**跨域资源共享 (CORS)**
跨域资源共享（**CORS**，Cross-Origin Resource Sharing）是一种基于 HTTP 头的安全机制，用于控制不同源的网页资源（如前端 JavaScript）能否访问另一个源的服务器数据。它是浏览器强制实施的策略，旨在防止恶意网站窃取用户数据。

新建软件包config，新建Java类CorsConfig
```Java
package com.example.demo.config;  
  
import org.springframework.context.annotation.Configuration;  
import org.springframework.web.servlet.config.annotation.CorsRegistry;  
import org.springframework.web.servlet.config.annotation.WebMvcConfigurer;  
  
@Configuration  
public class CorsConfig implements WebMvcConfigurer {  
    @Override  
    public void addCorsMappings(CorsRegistry registry) {  
        registry.addMapping("/**")  
                .allowedOrigins("http://localhost:5173") // 前端地址  
                .allowedMethods("GET", "POST", "PUT", "DELETE")  
                .allowedHeaders("*")  
                .allowCredentials(true);  
    }  
}
```
![](https://pic1.imgdb.cn/item/6810ee0158cb8da5c8d4a411.png)

接下来新建一个登录控制器LoginController
```Java
package com.example.demo.controller;  
  
import com.baomidou.mybatisplus.core.conditions.query.QueryWrapper;  
import com.example.demo.entity.User;  
import com.example.demo.mapper.UserMapper;  
import org.springframework.beans.factory.annotation.Autowired;  
import org.springframework.web.bind.annotation.PostMapping;  
import org.springframework.web.bind.annotation.RequestBody;  
import org.springframework.web.bind.annotation.RequestMapping;  
import org.springframework.web.bind.annotation.RestController;  
  
@RestController  
@RequestMapping("/user")  
public class LoginController {  
    @Autowired  
    private UserMapper userMapper;  
  
    @PostMapping("/login")  
    public String login(@RequestBody User user) {  
        System.out.println("登录："+user);  
        QueryWrapper<User> wrapper = new QueryWrapper<>();  
        wrapper.eq("username", user.getUsername());  
        User dbUser = userMapper.selectOne(wrapper);  
        if (dbUser == null) {  
            return "该用户不存在！";  
        } else if (!dbUser.getPassword().equals(user.getPassword())) {  
            return "密码错误！";  
        }  
        return "登录成功";  
    }  
}
```
![](https://pic1.imgdb.cn/item/6810ee6f58cb8da5c8d4a442.png)
这是一个最最简单的控制器，接收参数是前端传来的user，dbuser来获取数据库里与前端传来的username对应的用户，所以在这里可以发现，数据库的用户名不能有重复的。后面就是几个简单的判断。
这个控制器实现了基本功能，但是安全性和健壮性不是很高，我在这仅仅作为演示。

回到我们的Vue
修改如图所示的代码，调用登录方法并将返回值赋给response，我们打印一下response
```vue
const response = login(loginForm.username, loginForm.password)
console.log(response)
ElMessage.warning(response.data)
```
![](https://pic1.imgdb.cn/item/6810f2bd58cb8da5c8d4a624.png)
现在你可以在登录界面输入用户名与密码，登录一下试试，你会发现页面上方会弹出登录后端返回的信息，说明Api对接成功了。
按F12打开控制台，可以看到console.log打印出来的信息
![](https://pic1.imgdb.cn/item/6810f35058cb8da5c8d4a663.png)

### 关于工程化与约定

写到这里，想必你会有一点疑惑，为什么要创建这么多文件夹，这么多文件，而且命名风格与格式要求，这里就简单介绍一下**工程化**与**约定**。

在软件开发中，**工程化**和**约定**是提升团队协作效率、保障代码质量和维护性的两大核心手段。
 **1. 工程化（Engineering）**
**定义**：通过工具、流程、标准化技术栈等手段，将开发、构建、测试、部署等环节系统化、自动化，减少人为不可控因素。
**核心目标**：
- **自动化**：通过工具（如 Webpack、GitHub Actions）替代重复劳动。
- **标准化**：统一技术栈、目录结构、构建流程等。
- **可维护性**：代码结构清晰，文档完善，便于后续迭代。
- **质量保障**：集成代码检查（ESLint）、测试（Jest）、性能监控等。

比如我们用Spring boot和Vue等工具来实现快速开发，而不用重复造轮子，这就是一种工程化的体现。

**2. 约定（Convention）**
**定义**：团队或社区达成的共识性规则，包括代码风格、命名规范、设计模式等，通常通过文档或工具固化。
**核心目标**：
- **一致性**：统一代码风格（如变量命名用 `camelCase` 还是 `snake_case`）。
- **降低认知成本**：新成员快速理解项目结构（如 `src/components` 存放组件）。
- **减少决策成本**：避免在琐碎细节上争论（如缩进用空格还是 Tab）。

我们之所以创建这么多文件夹和文件，是为了统一规范，可快速帮助我们理解整个项目的结构。
什么地方该放什么，哪些文件有什么关联，这个文件的作用是什么，通过一种达成共识的约定，我们可以快速上手并修改。
比如我们约定，将所有视图文件都放在views里，又或者将所有控制器都放在controller里。
Java的命名风格是驼峰命名，每个单词开头大写。MySQL命名风格是下划线，每个单词中间加一个下划线。

### 简单写一个注册视图并对接Api

#### 注册视图
注册视图和登录视图的框架完全一样，只是改了名字，你完全可以复制登录框架的代码，在登录的代码基础上改一改就是注册视图了。
![](https://pic1.imgdb.cn/item/6816346f58cb8da5c8d9f7dc.png)
我在此还是贴上我的代码
```vue
<template>
    <div class="register-container">
        <el-card class="register-card">
            <div class="register-header">
                <h2>注册</h2>
            </div>

            <el-form ref="registerFormRef" :model="registerForm" :rules="registerRules" class="register-form"
                @submit.prevent="handleRegister">
                <el-form-item prop="username">
                    <p>用户名：</p>
                    <el-input v-model="registerForm.username" placeholder="请输入用户名" prefix-icon="User" />
                </el-form-item>

                <el-form-item prop="password">
                    <p>密码：</p>
                    <el-input v-model="registerForm.password" type="password" placeholder="请输入密码" prefix-icon="Lock"
                        show-password />
                </el-form-item>

                <el-form-item prop="repassword">
                    <p>重复密码：</p>
                    <el-input v-model="registerForm.repassword" type="password" placeholder="请重复密码" prefix-icon="Lock"
                        show-password />
                </el-form-item>

                <el-form-item prop="remember" class="remember-me">
                    <el-checkbox v-model="registerForm.remember">记住我</el-checkbox>
                </el-form-item>

                <el-form-item>
                    <el-button type="primary" class="register-btn" native-type="submit"
                        :loading="loading">注册</el-button>
                </el-form-item>
            </el-form>

            <div class="register-footer">
                <el-link type="primary" @click="forgetDialogVisible = true">忘记密码?</el-link>
                <el-link type="primary" @click="router.push('/login')">登录账号</el-link>
            </div>
        </el-card>

        <!-- 忘记密码对话框 -->
        <el-dialog v-model="forgetDialogVisible" title="忘记密码" width="30%">
            <span>请联系系统管理员重置密码</span>
            <template #footer>
                <el-button @click="forgetDialogVisible = false">关闭</el-button>
            </template>
        </el-dialog>
    </div>
</template>

<script setup>
import { ref, reactive } from 'vue'
import { ElMessage, ElNotification } from 'element-plus'
import { useRouter } from 'vue-router'
import { register } from '@/api/Api'

const router = useRouter()

// 表单引用
const registerFormRef = ref(null)

// 响应式数据
const registerForm = reactive({
    username: '',
    password: '',
    repassword: '',
    remember: false
})

const loading = ref(false)
const forgetDialogVisible = ref(false)

// 验证规则
const registerRules = reactive({
    username: [
        { required: true, message: '请输入用户名', trigger: 'blur' },
        { min: 3, max: 20, message: '长度在 3 到 20 个字符', trigger: 'blur' }
    ],
    password: [
        { required: true, message: '请输入密码', trigger: 'blur' },
        { min: 6, max: 20, message: '长度在 6 到 20 个字符', trigger: 'blur' }
    ],
    repassword: [
        { required: true, message: '请重复密码', trigger: 'blur' },
        { min: 6, max: 20, message: '长度在 6 到 20 个字符', trigger: 'blur' },
        {
            validator: (rule, value, callback) => {
                if (value !== registerForm.password) {
                    callback(new Error('两次输入的密码不一致'))
                } else {
                    callback()
                }
            }, trigger: 'blur'
        }
    ],
})

// 注册方法
const handleRegister = async () => {
    try {
        // 验证表单
        const valid = await registerFormRef.value.validate()
        if (!valid) return

        loading.value = true

        const response = await register(registerForm.username, registerForm.password)
        // ElMessage.warning(response.data)
        // console.log(response.data)
        if (response.data == '注册成功') {
            // 三秒后跳转到登录页面
            const countdown = ref(3);

            // 显示通知并动态更新倒计时
            const notification = ElNotification.success({
                title: '注册成功',
                message: `${countdown.value}秒后跳转至登录页面`, // 初始消息
                duration: 0, // 不自动关闭
                showClose: false, // 隐藏关闭按钮（可选）
            });

            const countdownElement = document.querySelector('.el-notification__content p');
            const timer = setInterval(() => {
                countdown.value--;
                console.log(countdownElement.textContent)
                countdownElement.textContent = `${countdown.value}秒后跳转至登录页面`;

                if (countdown.value <= 0) {
                    clearInterval(timer);
                    notification.close(); // 关闭通知
                    router.push('/login'); // 跳转登录页
                }
            }, 1000);
        } else {
            ElMessage.error('用户名已存在')
        }

    } catch (error) {
        ElMessage.error(error.response?.data?.message || '注册失败')
    } finally {
        loading.value = false
    }
}
</script>

<style scoped>
.register-container {
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    background-color: #f5f7fa;
}

.register-card {
    width: 400px;
    padding: 20px;
    border-radius: 5px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

.register-header {
    text-align: center;
    margin-bottom: 30px;
}

.register-header h2 {
    color: #409EFF;
}

.register-form {
    margin-top: 20px;
}

.register-btn {
    width: 50%;
    margin: 0 auto;
}

.register-footer {
    display: flex;
    justify-content: space-between;
    margin-top: 10px;
}
</style>
```
可以发现并没有改太多的地方。
#### 对接注册api
我将原来的LoginApi改名为Api，更通用一点，记得改名后要把之前导入这个Api的地方同样也改名。
![](https://pic1.imgdb.cn/item/6816365758cb8da5c8d9f8f6.png)
然后添加
```ts
const register = (username: string, password: string) => {
  return api.post('/user/register', {
    username,
    password
  })
}
```
之前是在function前面加上export，导出方法，现在可以在后面统一export
```ts
export {
	login,
	register
}
```
当然你也可以在每个函数面前加export，两种不同的方法罢了。

我们来到IDEA，编写后端的Controller
![](https://pic1.imgdb.cn/item/68163cdd58cb8da5c8d9fc48.png)
在LoginController里添加
```Java
@PostMapping("/register")  
public  String register(@RequestBody User user) {  
    QueryWrapper<User> wrapper = new QueryWrapper<>();  
    wrapper.eq("username", user.getUsername());  
    User dbUser = userMapper.selectOne(wrapper);  
    System.out.println(dbUser);  
    System.out.println(user);  
    if (dbUser == null) {  
        userMapper.insert(user);  
        return "注册成功";  
    }  
    return "用户名已存在";  
}
```

最后进行测试，别忘记运行两个项目
输入用户名密码点击注册后，你应该可以在MySQL数据库的用户表里看见刚刚注册的用户信息


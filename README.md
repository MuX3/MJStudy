# MJStudy
It's a start!

jdk 11.0.8

项目构建：Maven 3.6.3

web框架：Springboot

数据持久层：MyBatis

数据库：MySQL

前端框架：Vue

## 项目创建

配置Maven国内镜像：

在maven的`setting.xml`文件中添加：

```
<mirrors>

    <mirror>
        <id>aliyunmaven</id>
        <mirrorOf>*</mirrorOf>
        <name>阿里云公共仓库</name>
        <url>https://maven.aliyun.com/repository/public</url>
    </mirror>

</mirrors>
```

maven命令创建web骨架项目：`mvn archetype:generate -DgroupId=com.mjstudy -DartifactId=mjstudy -DarchetypeArtifactId=maven-archetype-webapp`

> **mvn archetype:generate -DgroupId=com.mycompany.app -DartifactId=myapp -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false**
>
> 　　mvn archetype:generate　                   　  固定写法
>
> 　　-DgroupId　　　　　　　　　　　　　　　　　　　　　　　组织标识（包名）
>
> 　　-DartifactId　　　　　　　　　　　　　　　　　　　　　 　项目名称
>
> 　　-DarchetypeArtifactId　　 　　　　　　　　　　　　　 　 指定ArchetypeId，maven-archetype-quickstart，创建一个Java Project；maven-archetype-webapp，创建一个Web Project
>
> 　　-DinteractiveMode　　　　　　　　　　　　　　　　　　　是否使用交互模式

然后在IDEA中设置，忽略HTTPS的SSL证书验证就好了，在Maven-Importing-VM options for importer里添加`-Dmaven.wagon.http.ssl.insecure=true -Dmaven.wagon.http.ssl.allowall=true`

web.xml默认的servlet版本为2.3，这个版本下的el表达式默认不工作，修改web.xml的servlet版本为3.1：

```xml
<?xml version="1.0" encoding="utf-8"?>
<web-app xmlns="http://xmlns.jcp.org/xml/ns/javaee"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://xmlns.jcp.org/xml/ns/javaee
                      http://xmlns.jcp.org/xml/ns/javaee/web-app_3_1.xsd"
         version="3.1"
         metadata-complete="true">
</web-app>
```

git 不允许提交空目录， 但是有一个hack的方式。 就是在要提交的空目录新建一个文件隐藏文件(以.开头)，这样就不是空目录了。 而这个文件名我们一般叫做 .gitkeep
MyBatis JPetStore
=================

JPetStore 6 is a full web application built on top of MyBatis 3, Spring 4 and Stripes.

Essentials
----------

* [See the docs](http://www.mybatis.org/jpetstore-6)

## Other versions that you may want to know about

- JPetstore on top of Spring, Spring MVC, MyBatis 3, and Spring Security https://github.com/making/spring-jpetstore
- JPetstore with Vaadin and Spring Boot with Java Config https://github.com/igor-baiborodine/jpetstore-6-vaadin-spring-boot

## Build Project
  - with maven: `mvn clean install`
  - with gradle: `gradle clean build`

## Running with Tomcat
Running JPetStore sample under Tomcat (using maven).
- Clone this repository
- Open command prompt/shell and change to cloned directory
- Issue following command to run project using Tomcat

mvn clean tomcat:run

- Run application in browser http://localhost:8080/jpetstore/ 
- Press Ctrl-C to stop the server.

## Run with Gradle

```
gradle jettyRun
```

## Run RobotFramework Test Case

```
pybot -d target -x target/xunit.xml -v SERVER:<IP:PORT> src/test
```
***WiseBuild配置注意事项：***

WiseBuild 构建命令写法如下（实际中请将172.20.9.3换成正确的maven私服地址，对于WiseCloud，它就是artifactory服务的虚IP，需暴露32778端口）：
```
gradle clean build --refresh-dependencies -PMavenRepoServerIP=172.20.9.3 -PMavenRepoServerPort=32778
```

构建环境选择：
```
dgroup/java8-gradle
```

归档文件写法：
```
./docker/*.war
```

Dockerfile路径：
```
docker/Dockerfile
```

镜像标签格式示例：
```
registry.wise2c.com/wise2c-demo/jpetstore:${BUILD_NUMBER}
```

测试环境选择：
```
rocketcity/robotframework-docker
```

构建命令写法（这里的172.20.8.4:8383请更换为实际部署JPetStoreDemo的访问入口）：
```
pybot -d target -x target/xunit.xml -v SERVER:172.20.8.4:8383 src/test
```

SonarQube参数（需放在Java编译阶段后执行，源码目录可直接填 . ）：
```
-Dsonar.java.binaries=build
```


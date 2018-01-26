## 1.编写pom
### 1.1 modelVersion
它只能是4.0.0

### 1.2 groupId、artifactId、version
1. 这3个元素定义了一个项目的基本坐标
2. groupId:定义了项目属于哪个组织，比如公司techown的项目shwzoo，我们可以定义groupId com.techown.shwzoo
3. artifactId:定义了当前maven项目在组中的唯一ID,可以定义为zoo-domain，zoo-web等等
4. version是只artifactId指定的maven项目的版本，如artifactId指定的maven项目是zoo-web，那就是zoo-web这个项目的版本，不是指整个groupId的版本
5. SNAPSHOP意思是快照，表示开发中，不稳定版本

### 1.3 编写主代码，并使用maven命令进行编译
1. 在src/main/java目录（maven约定）下编写主代码
2. 在项目根目录下运行 mvn clean compile 命令进行编译
3. clear 清理target目录，compile编译主代码至target目录

### 1.4 编写测试代码，并使用maven命令执行测试
1. 在src/test/java目录（maven约定）下编写主代码
2. 在项目根目录下运行 mvn clean test 命令执行测试

### 1.5 使用maven命令打包
1. 执行mvm clean package 默认生成jar文件,文件默认在target目录
2. 执行maven clean install 将jar文件安装到本地maven仓库
```
mvn install:install-file -Dfile=E:\workspace\aggregate-pay\lib\alipay-sdk-java-ALL20171201155700.jar -DgroupId=com.techown.alipay -DartifactId=alipay-sdk-java-ALL -Dversion=20171201155700 -Dpackaging=jar
```
3. 命令包含关系 install-package-test-compile，建议每个命令前都加clean
4. 默认情况下打包生成的jar是无法运行的，因为带有main方法的类，不会添加到manifest中。为生成可执行jar文件，需要借助maven-shade-plugin插件
### 1.6 使用Archetype生成项目骨架（不重要一般都是用IDE工具，下一张将，介绍）
1. 执行 mvn archetype:generate
2. 按照选择默认的archetype，应该是6，maven-archetype-quickstart

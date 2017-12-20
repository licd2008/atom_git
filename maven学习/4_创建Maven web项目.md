# Eclipse创建Maven Web项目

## 1. 选择 Maven Project，点击Next
![image/4-1](image/4-1.png)

## 2. 选中“Create a simple project(skip archetype selection)”，点击Next
![image/4-2](image/4-2.png)

## 3. 填写信息，点击Finish，创建出的Maven项目会提示缺少web.xml,继续执行下面操作，生成web.xml
![image/4-3](image/4-3.png)

## 4. 在项目上右击选择 → Properties → Project Facets
![image/4-4](image/4-4.png)

## 5. 不勾选“Dynamic Web Module”，将java版本修改成你想要设置的版本，我这里选择1.8，点击Apply，你会发现项目的jre变成1.8
![image/4-5](image/4-5.png)

## 6. 勾选“Dynamic Web Module”,选择3.0
![image/4-6](image/4-6.png)

## 7. 点击4-6图中的Further configuration available..,按照4-7图中填写Content director，然后勾选“General web.xml deployment descriptor”，点击OK,窗口关闭，点击外层窗口的Apply，最后点击OK，现在一个3.0版本的xml已经生成了
![image/4-7](image/4-7.png)

## 8. 修改pom.xml添加如下配置，然后在项目上右击选择Maven → Update Project...
    <build>
      	<plugins>
      		<plugin>
      			<groupId>org.apache.maven.plugins</groupId>
    	  		<artifactId>maven-compiler-plugin</artifactId>
    	  		<version>3.7.0</version>
    	  		<configuration>
    	  			<source>1.8</source>
    	  			<target>1.8</target>
    	  			<encoding>UTF-8</encoding>
    	  		</configuration>
      		</plugin>
      	</plugins>
      </build>
## 9. 已经完成Mave Web项目的创建

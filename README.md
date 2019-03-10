# maven-training

## simple walk through:

1. Install maven, configure `JAVA_HOME`, `MAVEN_HOME`, `PATH`, call `mvn --help`, `mvn --version`.
2. Write simple pom.xml, run maven clean. Be carefull w/ file extensions not showing up in windows.
```
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>

</project>
```
```
    <groupId>cf.mindaugas</groupId>
    <artifactId>sda-maven-demo</artifactId>
    <version>1.0-SNAPSHOT</version>
```
3. Build a simple project from command line - hello world, by hand or by using this command (junit added by default):
```
mvn archetype:generate\
         -DarchetypeArtifactId=maven-archetype-quickstart\
         -DinteractiveMode=false -DgroupId=my.pkg.path\
         -DartifactId=myartifact
```
4. Command chaining - `mvn clean deploy` and `mvn clean test`:
```
[ERROR] Failed to execute goal org.apache.maven.plugins:maven-compiler-plugin:3.1:compile (default-compile) on project myartifact: Compilation failure: Compilation failure:
[ERROR] Source option 5 is no longer supported. Use 6 or later.
[ERROR] Target option 1.5 is no longer supported. Use 1.6 or later.
```
```
<properties>
    <maven.compiler.source>1.6</maven.compiler.source>
    <maven.compiler.target>1.6</maven.compiler.target>
</properties>
```
5. Commit the "Hello world" project just generated to github.
6. Build same (or similar) project with your ide.

![image](https://user-images.githubusercontent.com/7895269/53935028-91bb4580-40ad-11e9-8258-ccccf9f0de35.png)

7. Using the jar pluging launch your created application (solving the `no main manifest attribute`).

```
<build>
  <plugins>
    <plugin>
      <!-- Build an executable JAR -->
      <groupId>org.apache.maven.plugins</groupId>
      <artifactId>maven-jar-plugin</artifactId>
      <version>3.1.0</version>
      <configuration>
        <archive>
          <manifest>
            <addClasspath>true</addClasspath>
            <classpathPrefix>lib/</classpathPrefix>
            <mainClass>com.mypackage.MyClass</mainClass>
          </manifest>
        </archive>
      </configuration>
    </plugin>
  </plugins>
</build>
```

8. Goal chaining in command line and ide.
9. Override default build directory / compiled file name inside the build directive.
A. Convert old projects into maven projects.
B. Add scope to junit dependency (maven scopes).
C. Unit testing in maven: cmd and ide.
D. Import an existing project as a maven project.

## resources:

- Good simple tutorial: http://www.java2s.com/Tutorials/Java/Maven_Tutorial/index.htm

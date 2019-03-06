# maven-training

1. Install maven, configure `JAVA_HOME`, `MAVEN_HOME`, `PATH`, call `mvn --help`, `mvn --version`.
2. Write simple pom.xml, run maven clean.
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
3. Build a simple project from command line - hello world, by hand or by using this command:
```mvn archetype:generate -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false -DgroupId=my.package.path -DartifactId=myartifact```
4. Command chaining: mvn clean deploy
5. Build same or similar project with your ide.
6. Override default build directory / compiled file name inside the build directive.
X. Add junit testing framework.
7. Add scope to junit dependency (maven scopes).
X. Unit testing in maven: cmd and ide.
8. Import an existing project as a maven project → from my github to students machine.

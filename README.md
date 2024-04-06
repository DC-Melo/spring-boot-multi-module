# spring-boot-multi-module
command line step by step spring-boot-multi-module


## Create Create a Root Project
```
mvn archetype:generate -DinteractiveMode=false -DarchetypeArtifactId=pom-root -DarchetypeVersion=RELEASE -DarchetypeGroupId=org.codehaus.mojo.archetypes -DgroupId=com.company -DartifactId=spring-boot-multi-module
```
## Create the Application Project
```
spring init --build=maven --java-version=17 --description="Demo project for Spring Boot" --packaging=jar --group-id=com.company --artifact-id=demo --package-name=com.company.demo --dependencies=web --name=demo demo-service
```

## Move common elements to parents pom.xml, especial build elements. Then run Application
```
mvn clean package spring-boot:run --projects demo-service
```



# Spring-Boot: Simple Multi-Module Project

With this setup the usual `mvn clean spring-boot:run` is possible **in the root directory of the project**.

This feature is missing in several tutorials, e.g.

* [Getting Started - Creating a Multi Module Project](https://spring.io/guides/gs/multi-module/)
* [Multi-Module Project With Spring Boot](https://www.baeldung.com/spring-boot-multiple-modules)
* [Multiple modules in Spring Boot apps](https://blog.frankel.ch/multiple-modules-spring-boot-apps/)

See also

* https://github.com/spring-projects/spring-boot/issues/3436


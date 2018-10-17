# Spring Tutorial

## Building a RESTful Web Service using Java with Gradle
System requirements:  
    - JDK 6 or later  
    - Integrated Development Environment(IDE) or text editor 

Customize the greeting with an optional name parameter in the query string.  
The name parameter value overrides the default value of "World".  
       
## Steps
### Create a Java application with Gradle:
    - Create project directory: `mkdir SpringTutorial`
    - In the project directory, to create java application with gradle run command: `gradle init --type java-application`
        - This command will generate subdirectories for project source file and test file.  
        
### Create a Gradle build file:  
     buildscript {
        repositories {
            mavenCentral()
        }
        dependencies {
            classpath("org.springframework.boot:spring-boot-gradle-plugin:2.0.5.RELEASE")
        }
     }  
     
    apply plugin: 'java'
    apply plugin: 'eclipse'
    apply plugin: 'idea'
    apply plugin: 'org.springframework.boot'
    apply plugin: 'io.spring.dependency-management'  
     
    bootJar {
        baseName = 'gs-rest-service'
        version =  '0.1.0'
    }
     
    repositories {
        mavenCentral()
    }
     
    sourceCompatibility = 1.8
    targetCompatibility = 1.8
     
    dependencies {
        compile("org.springframework.boot:spring-boot-starter-web")
        testCompile('org.springframework.boot:spring-boot-starter-test')
    }     
 
 - Create `Greeting` class
    - add id and name fields
 - Create `GreetingController` class
    - add RequestMapping
 - Create `Application` class
    - add autowiring to run application 
    
 - Run application
    - `http://localhost:8080/greeting` 
        - should respond with `{"id":1,"content":"Hello, World!"}`
    - `http://localhost:8080/greeting?name=User`
        - should respond with `{"id":1,"content":"Hello, User!"}`
### Sources
- [building java applications](https://guides.gradle.org/building-java-applications/)  
- [building java projects with gradle](https://spring.io/guides/gs/gradle/)  
- [building a RESTful web service](https://spring.io/guides/gs/rest-service/)
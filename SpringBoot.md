### <b>what is the difference between spring/springmvc and springboot?</b>

Spring and Spring MVC (Model-View-Controller) are two separate frameworks that are often used together in Java web development. Spring is a lightweight, inversion of control (IoC) container that provides a way to manage objects and their dependencies. It can be used for a wide range of tasks, including dependency injection, aspect-oriented programming, and data access.

Spring MVC, on the other hand, is a web framework that is built on top of Spring. It provides a way to implement the Model-View-Controller pattern in a web application, and it includes features such as a DispatcherServlet, a web-based application context, and support for RESTful web services.

Spring Boot, is an evolution of Spring framework, it is a Spring-based framework that aims to simplify the bootstrapping and development of new Spring applications. Spring Boot provides an opinionated view of the Spring platform and third-party libraries so that developers can get started with minimal fuss. It provides a way to create stand-alone, production-grade Spring-based applications with minimal configuration. It also includes a set of pre-configured options for popular development tools, such as embedded web servers, security, and data access.

In summary, Spring is a general-purpose framework for Java development, Spring MVC is a web framework that's built on top of Spring, and Spring Boot is a way to create stand-alone, production-grade Spring-based applications with minimal configuration.

### <b>Quick start SpringBoot</b> <br>
1.Maven command -> package<br>
2.Terminal command -> java -jar springboot.jar<br>
Notice: jar command-line startup relies on maven plug-in
~~~
<build>
    <plugins>
        <plugin>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-maven-plugin</artifactId>
            </plugin>
    </plugins>
</build>
~~~

### <b>Advantages of Spring Boot</b> ?
Auto-configuration: Spring Boot automatically configures your application based on the dependencies that you have added. This means that you don’t have to manually configure components such as data sources, security, and web services.

Embedded servers: Spring Boot includes support for embedded web servers, such as Tomcat and Jetty, which makes it easy to deploy your application without the need for a separate application server.

Command-line Interface: Spring Boot provides a command-line interface (CLI) that you can use to quickly create and run Spring-based applications. The CLI relies on a Maven plugin, which makes it easy to create a new project and run it with minimal setup.
A Command-line Interface (CLI) is a type of user interface that allows users to interact with a computer by typing commands on a command line. Spring Boot provides a command-line interface (CLI) that you can use to quickly create and run Spring-based applications. The Spring Boot CLI is a command-line tool that you can use to quickly create a new Spring Boot project, run the project, and perform other common development tasks. The CLI uses a Maven plugin, which makes it easy to create a new project and run it with minimal setup.

Production-ready features: Spring Boot includes a number of production-ready features, such as health checks, metrics, and externalized configuration, which help you to build and deploy reliable applications.

Opinioned defaults: Spring Boot provides a set of opinionated defaults for building Spring applications. This allows developers to quickly get started with minimal configuration.

Easier testing: Spring Boot makes it easier to test your application with built-in support for JUnit, Hamcrest, and Mockito. It also provides a test-autoconfigure module that automatically configures your test context and provides useful test-related features, like an embedded web server for testing controllers.
### <b>what is parent Springboot</b>?
In Spring Boot, the term "parent" refers to the parent POM (Project Object Model) of a project. A parent POM is a POM file that is used to manage common dependencies and configuration for a group of related projects.

When you create a new Spring Boot project, it will typically include a parent POM that is specified in the project's pom.xml file. This parent POM will contain the dependencies and configuration needed to build a Spring Boot application. It also defines a set of default properties that can be used to configure the project, such as the default Java version, the default Spring Boot version, and so on.

The parent POM allows you to manage common dependencies and configuration for a group of related projects. This makes it easy to update the dependencies or configuration for multiple projects at once. For example, if you need to update the version of Spring Boot that your projects use, you can update the parent POM, and all of the projects that inherit from it will automatically use the updated version.

### <b>what is Springboot starters</b>?
Spring Boot starters are a set of convenient dependency descriptors that you can include in your application. They provide a quick way to add the dependencies that you need for a specific type of application.

For example, if you are building a web application, you can include the spring-boot-starter-web dependency in your pom.xml file. This will automatically include all of the dependencies that are required to build a web application, such as Spring MVC, Tomcat, and Jackson.

Spring Boot starters are designed to be easy to use and understand. They are typically named after the type of application that they are intended to be used with, such as "spring-boot-starter-web" for web applications, "spring-boot-starter-data-jpa" for applications that use JPA to access a database, "spring-boot-starter-security" for applications that need to secure their resources and so on.

Each starter POM provides a set of useful transitive dependencies, which are automatically included in your project. So when you include a starter, you don't need to worry about including all of its dependencies manually. This makes it easy to add new functionality to your application without having to manually manage the dependencies.

Notice !! when add dependencies in SpringBoot, do not write <b><font color = "red">version</font></b> of this dependency.

### <b>exchange from embeded tomcat to jetty</b>
~~~
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-web</artifactId>
        <exclusions>
            <exclusion>
                <groupId>org.springframework.boot</groupId>
                <artifactId>spring-boot-starter-tomcat</artifactId>
            </exclusion>
        </exclusions>
</dependency>
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-tomcat</artifactId>
</dependency>
~~~
springboot can configure server port in three different files: <br>
application.properties >application.yml >application.yaml<br>

### <b>what is yml configuration file</b>
YAML (YAML Ain't Markup Language) is a human-readable data serialization format that is often used as an alternative to XML or JSON. In Spring Boot, YAML is often used as a configuration file format.

A YAML configuration file is a plain text file that contains key-value pairs, similar to JSON or XML. However, YAML is designed to be more easily readable by humans, with a more relaxed syntax and fewer braces and brackets.

In Spring Boot, you can use YAML files to configure your application. Spring Boot automatically detects and loads YAML files from the classpath, and you can use the spring. prefix to configure various properties of your application, such as the server port, database connection, and so on.
### <b>what is development environment, production environment and test environment</b>
A development environment is a set of tools and resources that developers use to write, test, and debug software. This can include a variety of tools such as text editors, integrated development environments (IDEs), version control systems, and build and test automation tools. The development environment is typically set up on a developer's personal computer or a shared development server, and is used by developers to create and modify code.

A production environment is the environment in which the software is actually used by end-users. This can include servers, databases, and other resources that are used to host the software and make it available to users. The production environment is typically more tightly controlled than the development environment, and may have additional security and reliability requirements.

A test environment is a place where the software is deployed to test it's functionality and performance. The test environment is typically similar to the production environment, but it is used only for testing purposes. It is used to test the software before it is released to the production environment. Test environment includes different types of testing like unit testing, integration testing, system testing, acceptance testing, and performance testing.





# devinterview.io spring 100

# Spring Fundamentals

#### ✅ 1. What is the Spring Framework and what are its core features?
**Answer:**
Spring Framework is a comprehensive Java framework that simplifies Java development and promotes good design practices. Core features include:
- **Inversion of Control (IoC):** Allows objects to be created and managed by a container.
- **Dependency Injection (DI):** Injects dependencies into objects, reducing coupling.
- **Aspect-Oriented Programming (AOP):** Separates cross-cutting concerns.
- **Data Access:** Simplifies database access with JDBC and ORM frameworks.
- **Transaction Management:** Provides declarative transaction support.
- **Model-View-Controller (MVC):** Offers a flexible web application framework.

#### ✅ 2. How do you create a simple Spring application?
**Answer:**
A simple Spring application involves:
1. Creating a Java class representing the application.
2. Defining beans (components) in a Spring configuration file.
3. Configuring the application context to load the configuration file.
4. Retrieving beans from the context and using them in the application.

#### ✅ 3. What is Inversion of Control (IoC)? How does Spring facilitate IoC?
**Answer:**
Inversion of Control is a design principle where the control flow is inverted – the framework manages the flow instead of the application. In Spring, IoC is achieved through dependency injection. The Spring container manages the creation and lifecycle of objects, injecting dependencies when needed.

#### ✅ 4. What is the ApplicationContext in Spring?
**Answer:**
The ApplicationContext is the central interface in Spring for interacting with the Spring IoC container. It loads and manages beans, provides essential features like dependency injection, and supports aspects such as event propagation and AOP. It extends the BeanFactory interface with additional enterprise-specific functionality.

#### ✅ 5. Explain Dependency Injection and its types in the Spring context.
**Answer:**
Dependency Injection (DI) is a design pattern where objects receive their dependencies from an external source. In Spring, DI is achieved through:
- **Constructor Injection:** Dependencies are injected via the constructor.
- **Setter Injection:** Dependencies are injected via setter methods.
- **Method Injection:** Dependencies are injected via methods.

#### ✅ 6. What are Bean Scopes in Spring? Name them.
**Answer:**
Bean Scopes in Spring define the lifecycle and visibility of a bean. Common scopes include:
- **Singleton:** A single instance per Spring IoC container (default).
- **Prototype:** A new instance whenever requested.
- **Request:** A new instance for each HTTP request (in a web context).
- **Session:** A new instance for each HTTP session (in a web context).

#### ✅ 7. How do you configure a bean in Spring?
**Answer:**
Beans in Spring are configured using XML or Java-based configurations. In XML, a bean is defined using the `<bean>` element within a Spring configuration file. In Java-based configuration, the `@Bean` annotation is used to declare a method that produces a bean.

#### ✅ 8. Describe the role of the Spring Core container.
**Answer:**
The Spring Core container is responsible for creating, configuring, and managing beans. It includes the ApplicationContext and BeanFactory interfaces. The container reads bean definitions, instantiates beans, and manages their lifecycle. It supports various features like dependency injection, bean scopes, and aspect-oriented programming.

#### ✅ 9. What is a Spring configuration file?
**Answer:**
A Spring configuration file, often named `applicationContext.xml`, is an XML file that contains bean definitions and configuration metadata. It specifies how beans are created, wired, and managed by the Spring IoC container.

#### ✅ 10. How do you create an ApplicationContext in a Spring application?
**Answer:**
To create an ApplicationContext, you can use:
1. **ClassPathXmlApplicationContext:** Loads context definition from an XML file located in the classpath.
2. **FileSystemXmlApplicationContext:** Loads context definition from an XML file in the filesystem.
3. **AnnotationConfigApplicationContext:** Loads context definition from Java-based configuration classes.


# Spring AOP

#### ✅ 11. What is Aspect-Oriented Programming (AOP)?
**Answer:**
Aspect-Oriented Programming (AOP) is a programming paradigm that aims to increase modularity by allowing the separation of cross-cutting concerns. It achieves this by introducing aspects, which encapsulate cross-cutting concerns and can be applied to multiple parts of a system.

#### ✅ 12. How does Spring support AOP?
**Answer:**
Spring supports AOP by providing a framework that allows the definition and application of aspects. It uses runtime proxies or bytecode instrumentation to weave aspects into the codebase, separating concerns like logging, security, and transactions from the core business logic.

#### ✅ 13. Can you explain a Pointcut and an Advice in Spring AOP?
**Answer:**
- **Pointcut:** A pointcut is an expression that defines where an aspect should be applied. It specifies a set of join points, indicating where in the application's execution flow the aspect's code should be executed.
- **Advice:** An advice is the code that runs at a specified join point. It represents the action taken by the aspect at that point in the execution.

#### ✅ 14. What is a Join Point in Spring AOP?
**Answer:**
A join point is a point in the execution of a program, such as the execution of a method or the handling of an exception. In Spring AOP, join points are defined by pointcuts, and aspects are applied at these join points.

#### ✅ 15. What is the difference between a Concern and a Cross-cutting Concern in Spring AOP?
**Answer:**
- **Concern:** In AOP, a concern is a specific functionality that needs to be addressed, like logging, security, or transaction management.
- **Cross-cutting Concern:** Cross-cutting concerns are aspects of a program that affect multiple modules and are often intertwined with the core logic. AOP is designed to address cross-cutting concerns by separating them from the main business logic.

#### ✅ 16. Describe the different types of Advices in AOP.
**Answer:**
- **Before Advice:** Executed before the join point, typically used for setup actions.
- **After Returning Advice:** Executed after the join point completes successfully.
- **After Throwing Advice:** Executed if the join point throws an exception.
- **After (Finally) Advice:** Executed regardless of the outcome (success or exception).
- **Around Advice:** Wraps around the join point, providing full control over the behavior.

#### ✅ 17. How do you implement AOP in Spring?
**Answer:**
AOP in Spring is implemented by defining aspects, pointcuts, and advices in XML configuration or using annotations. Aspects are applied using proxies or weaving.

#### ✅ 18. What is the @Aspect annotation used for in Spring AOP?
**Answer:**
The `@Aspect` annotation is used to define a class as an aspect in Spring. It indicates that the class contains advice methods and pointcut expressions.

#### ✅ 19. How would you enable AOP in a Spring application?
**Answer:**
AOP is enabled in a Spring application by:
1. Including the AOP library in the project dependencies.
2. Configuring aspects, pointcuts, and advices in the Spring configuration.
3. Enabling proxy-based or aspectj-based weaving.


# Spring Data Access

#### ✅ 20. Describe how Spring interacts with databases.
**Answer:**
Spring interacts with databases using the Spring Data module, which provides abstractions for data access. It supports both JDBC and ORM frameworks and provides templates and abstractions to simplify database operations.

#### ✅ 21. What is the DataAccessException class in Spring?
**Answer:**
`DataAccessException` is a runtime exception in the Spring framework that serves as a base class for exceptions thrown during database-related operations. It provides a consistent exception hierarchy for various data access technologies, including JDBC and ORM.

#### ✅ 22. Explain the Template design pattern as used in Spring.
**Answer:**
The Template design pattern is a behavioral design pattern that defines the structure of an algorithm but allows its steps to be implemented by subclasses. In Spring, the Template design pattern is used in classes like `JdbcTemplate` and `HibernateTemplate`, where the template provides a skeleton algorithm for a common operation, and specific steps are implemented by callbacks or strategies.

#### ✅ 23. What is the Spring JDBC Template and how do you use it?
**Answer:**
`JdbcTemplate` is a part of the Spring JDBC module that simplifies the use of JDBC and helps manage resources. It provides methods for common database operations, such as query execution and update operations. It handles resource acquisition, release, and exception handling. Example usage:

```java
JdbcTemplate jdbcTemplate = new JdbcTemplate(dataSource);
List<String> results = jdbcTemplate.query("SELECT name FROM users", String.class);
```

#### ✅ 24. How does Spring support transaction management?
**Answer:**
Spring supports transaction management through its `Transaction Management Abstraction`, providing a consistent programming model across various transaction management technologies. It offers both declarative (using annotations or XML configuration) and programmatic (using `TransactionTemplate`) approaches to manage transactions. Spring supports local and global transactions, and it seamlessly integrates with JTA (Java Transaction API).

#### ✅ 25. Can you explain Spring's support for ORM frameworks?
**Answer:**
Spring provides seamless integration with Object-Relational Mapping (ORM) frameworks like Hibernate, JPA (Java Persistence API), and MyBatis. It simplifies database access and transaction management. Key features include:
- **Unified Data Access:** Consistent data access using JDBC or ORM.
- **Exception Translation:** Converts low-level database-related exceptions into Spring's DataAccessException.
- **Declarative Transaction Management:** Simplifies transaction management in ORM operations.

#### ✅ 26. What are the key interfaces used for JDBC operations in Spring?
**Answer:**
The key interfaces for JDBC operations in Spring include:
- **JdbcTemplate:** Provides methods for common JDBC operations.
- **RowMapper:** Converts a row of a `ResultSet` to an object.
- **DataSource:** Abstraction for acquiring a database connection.
- **PreparedStatementCreator:** Creates a `PreparedStatement`.
- **ResultSetExtractor:** Extracts results from a `ResultSet`.


# Spring MVC

#### ✅ 27. What is the Spring MVC framework?
**Answer:**
Spring MVC (Model-View-Controller) is a part of the Spring Framework that facilitates the development of web applications. It provides a robust and flexible model for building web-based applications, following the MVC design pattern.

#### ✅ 28. Describe the architecture of a Spring MVC application.
**Answer:**
The architecture of a Spring MVC application consists of:
- **DispatcherServlet:** Central entry point for handling web requests.
- **Controller:** Processes user requests, performs business logic, and returns a response.
- **Model:** Represents data and business logic.
- **View:** Renders the data to the user.

#### ✅ 29. What are the roles of the @Controller and @RequestMapping annotations?
**Answer:**
- **@Controller:** Marks a class as a Spring MVC controller.
- **@RequestMapping:** Maps web requests to methods in a controller. It defines the URL path that triggers the method.

#### ✅ 30. Explain the DispatcherServlet and its functions.
**Answer:**
The `DispatcherServlet` is the front controller in Spring MVC. Its functions include:
- Receiving and handling incoming HTTP requests.
- Routing requests to the appropriate controller.
- Managing the entire request-response lifecycle.

#### ✅ 31. How do you handle web requests in Spring MVC?
**Answer:**
Web requests in Spring MVC are handled by methods annotated with `@RequestMapping` in controller classes. The `@RequestMapping` annotation specifies the URL path to which the method responds.

#### ✅ 32. Can you discuss the Request-response lifecycle in a Spring MVC application?
**Answer:**
The Request-response lifecycle in Spring MVC involves:
- DispatcherServlet receiving the request.
- Identifying the appropriate controller using Handler Mapping.
- Executing the controller method.
- Processing the model and view.
- Rendering the response.

#### ✅ 33. How do you validate user input in Spring MVC?
**Answer:**
User input validation in Spring MVC is achieved using validation annotations like `@NotNull`, `@Size`, etc., on model attributes. Additionally, you can use the `@Valid` annotation to trigger validation on nested objects.

#### ✅ 34. What are the differences between @Controller and @RestController?
**Answer:**
- **@Controller:** Used for traditional MVC controllers, returning views.
- **@RestController:** Specialized version of `@Controller` for RESTful services. Assumes @ResponseBody on all methods, converting the return value directly to JSON or XML.


# Spring Boot

#### ✅ 35. What is Spring Boot and what are its advantages?
**Answer:**
Spring Boot is a framework built on top of the Spring framework, designed to simplify the development of production-ready applications with minimal configuration. Advantages include convention over configuration, automatic setup, and reduced development time.

#### ✅ 36. How do you create a Spring Boot application?
**Answer:**
To create a Spring Boot application, you can use Spring Initializr (https://start.spring.io/) to generate a project with the desired dependencies. Alternatively, you can add the necessary dependencies manually to a Maven or Gradle project.

#### ✅ 37. Explain Auto-Configuration in Spring Boot.
**Answer:**
Auto-Configuration in Spring Boot automatically configures beans based on the project's dependencies. It leverages the `@ConditionalOn...` annotations to conditionally enable configuration based on the presence of certain classes or properties.

#### ✅ 38. What is a Spring Boot Starter?
**Answer:**
A Spring Boot Starter is a pre-packaged set of dependencies that provides a certain functionality. Starters simplify the dependency management and configuration for common use cases like web applications, data access, or messaging.

#### ✅ 39. How does Spring Boot support data access?
**Answer:**
Spring Boot supports data access through the Spring Data project. It provides starter modules like `spring-boot-starter-data-jpa` for JPA-based data access and `spring-boot-starter-data-mongodb` for MongoDB, among others.

#### ✅ 40. What is the embedded server concept in Spring Boot?
**Answer:**
Spring Boot includes an embedded server (like Tomcat, Jetty, or Undertow) as part of the application. It allows you to run your application as a standalone JAR file without the need for an external server installation.

#### ✅ 41. Explain the role of the SpringApplication class.
**Answer:**
The `SpringApplication` class in Spring Boot provides a convenient way to bootstrap a Spring application. It helps set up the application context, handle command-line arguments, and launch the application.

#### ✅ 42. What properties file is used by default in Spring Boot?
**Answer:**
Spring Boot uses `application.properties` or `application.yml` as the default properties file. It allows you to configure various aspects of the application, such as data source settings, logging levels, and more.


# Spring Security

#### ✅ 43. What is Spring Security and why is it important?
**Answer:**
Spring Security is a powerful and customizable authentication and access control framework for Java applications. It is essential for securing applications by providing features like authentication, authorization, and protection against common security vulnerabilities.

#### ✅ 44. Explain how authentication and authorization work in Spring Security.
**Answer:**
Authentication in Spring Security verifies the identity of a user, while authorization determines the user's access rights. Authentication is done through authentication providers, and authorization involves roles and access control lists (ACLs) defined in the application.

#### ✅ 45. How do you configure Spring Security in an application?
**Answer:**
Spring Security can be configured using Java configuration or XML configuration. You extend the `WebSecurityConfigurerAdapter` class, override its methods to customize security settings, and use annotations like `@EnableWebSecurity` to enable Spring Security.

#### ✅ 46. What is a Principal in Spring Security?
**Answer:**
A `Principal` in Spring Security represents the authenticated user. It encapsulates information about the user, such as username and authorities, and is obtained during the authentication process.

#### ✅ 47. How do you secure Restful web services in Spring Security?
**Answer:**
Restful web services can be secured in Spring Security by configuring security settings to protect specific endpoints. This can include requiring authentication, specifying roles, and handling authorization based on user roles.

#### ✅ 48. Explain the importance of the @PreAuthorize annotation.
**Answer:**
The `@PreAuthorize` annotation in Spring Security is used for method-level security. It allows you to specify access control expressions directly in the code, enabling fine-grained control over who can access a particular method based on conditions.

#### ✅ 49. What is the role of the WebSecurityConfigurerAdapter class?
**Answer:**
The `WebSecurityConfigurerAdapter` class is a convenient way to customize the security settings of a Spring Security-enabled application. You extend this class and override its methods to configure authentication, authorization, and other security features.

#### ✅ 50. How do you handle CSRF protection in Spring Security?
**Answer:**
CSRF (Cross-Site Request Forgery) protection in Spring Security involves including a CSRF token in forms and validating it on the server side. This can be configured using the `csrf()` method in the `WebSecurityConfigurerAdapter` class.


# Spring with Microservices

#### ✅ 51. How is Spring used in building microservices?
**Answer:**
Spring provides a comprehensive ecosystem, including Spring Boot and Spring Cloud, which simplifies the development of microservices. Spring Boot facilitates the creation of standalone, production-grade Spring-based applications, while Spring Cloud provides tools for building and coordinating microservices.

#### ✅ 52. What is Spring Cloud?
**Answer:**
Spring Cloud is a set of tools and frameworks for building and managing cloud-ready microservices. It includes features for service discovery, distributed configuration, load balancing, circuit breakers, and more, making it easier to develop and deploy microservices-based applications.

#### ✅ 53. Explain the role of Eureka in Spring Cloud.
**Answer:**
Eureka is a service discovery framework in Spring Cloud. It allows microservices to register themselves and discover other services in the system. Eureka provides a central registry where microservices can publish their availability, and other services can look up and consume those services.

#### ✅ 54. How do you implement client-side load balancing with Spring Cloud?
**Answer:**
Client-side load balancing in Spring Cloud can be achieved using tools like Netflix Ribbon. Ribbon is a client-side load balancer that enables service consumers to distribute requests across multiple service instances. It integrates seamlessly with Eureka for service discovery.

#### ✅ 55. What are Spring Cloud Config and its use case?
**Answer:**
Spring Cloud Config is a module that provides centralized external configuration management for distributed systems. It allows you to store and manage configuration properties for microservices in a centralized configuration server. This helps in maintaining consistency and managing configurations across different environments.

#### ✅ 56. Can you explain the Circuit Breaker pattern in the context of Spring Cloud?
**Answer:**
The Circuit Breaker pattern in Spring Cloud is implemented using tools like Netflix Hystrix. It helps prevent a network or service failure from cascading to other services. When a fault is detected, the circuit breaker temporarily stops allowing requests to that service and directs calls to a fallback mechanism. This prevents the failure from affecting the entire system.

#### ✅ 57. What is a Spring Cloud Gateway?
**Answer:**
Spring Cloud Gateway is a dynamic, non-blocking, and reactive API gateway built on top of Spring WebFlux. It is designed to handle routing, filtering, and load balancing of requests coming into a microservices-based system. It provides a way to control and manage the traffic between clients and microservices.


# Spring Reactive Programming

58. What is Reactive Programming and how does Spring support it?
59. What the WebFlux framework Spring 5?
60. Explain the back-pressure concept in reactive streams.
61. How do you create a non-blocking REST API in Spring WebFlux?

# Spring Testing

62. How do you perform unit testing in a Spring application?
63. What role does Spring TestContext Framework play in testing?
64. What is the @SpringBootTest annotation used for?
65. How do you mock beans in a Spring context for testing?

# Advanced Spring

66. How does Spring support internationalization (i18n)?
67. Explain the concept of Spring Expression Language (SPEL).
68. How do you schedule tasks in Spring?
69. What is the difference between @Bean and @Component in Spring?
70. Explain the difference between @Inject and @Autowired in Spring.

# Spring Best Practices

71. What are some best practices for designing Spring applications?
72. How do you handle exceptions in a Spring application?
73. What are the practices for securing passwords in Spring?
74. How can you improve the performance of a Spring-based web application?
75. When should you use Aspect-Oriented Programming in Spring?

# Spring Integration and Batch Processing

76. What is Spring Integration and where is it best applied?
77. Explain the key components of Spring Batch and its use cases.
78. How does Spring Integration differ from Spring Batch?
79. What are endpoints in Spring Integration?
80. Explain the concept of Chunk processing in Spring Batch.

# Spring Cloud Data Flow

81. What is Spring Cloud Data Flow and its benefits for data-driven applications?
82. How do you create custom processors in Spring Cloud Data Flow?
83. Explain how Spring Cloud Data Flow handles stream processing.

# Spring and Messaging

84. How does Spring integrate with message brokers?
85. What is JMS (Java Message Service) and how does spring provide support for it?
86. Explain the role of the @KafkaListener annotation in Spring.
87. How can you send and receive messages using AMQP in Spring?

# Spring Kafka
88. What is Spring Kafka and how does it integrate with Apache Kafka?
89. How do you manage transactions in Kafka with Spring?
90. Explain the use of KafkaTemplate in Spring Kafka.

# Spring Caching

91. How do you implement caching in a Spring application?
92. What is the Cache Abstraction in Spring?
93. Explain the differences between @CachePut, @CacheEvict, and @Cacheable annotations.

# Spring GraphQL
94. How does Spring support building GraphQL APIs?
95. What are the advantages of using GraphQL over REST in Spring?

# Spring Actuator and Monitoring

96. What is the Spring Boot Actuator and its purposes?
97. How do you expose custom metrics using Spring Boot Actuator?
98. Describe how to secure Spring Boot Actuator endpoints.

# Spring Application Deployment and Management

99. What considerations should be made when deploying a Spring Boot application in a containerized environment?
100. How can you manage application profiles in a Spring Boot application?

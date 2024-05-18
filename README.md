# Spring_Interview_QA

Q. 1) What is Spring?  
Ans) Spring is a framework and it has combinations of different technologies.  
It is light-weight, loosely coupled, enterprise application.  
Light-weight means it occupies less memory.  
Loosely coupled means we can implement multiple modules parallelly and integrate.  
It also provides pre-defined API for Database Operations, Restful web services, microservices, and security.  
We can develop web applications and distributed applications by using Spring.

---

Q. 2) What are features of Spring Framework?  
Ans) Spring provides multiple features:  
1) **Pre-defined Templates**  
   It provides templates like JDBC templates, Hibernate templates, REST templates, etc. So templates are boilerplate code which reduces code.
2) **Loose Coupling**  
   It is implemented using layers mechanism.  
   Like Service layer, Data access layer, Presentation layer.  
   If one layer is modified that will not affect the other layer or modules that is called loose coupling.
3) **Light Weight**  
   It will occupy less memory, that's why it's lightweight.
4) **Easy To Test**  
   We can use JUnit or Mockito to write test cases to confirm whether our application is working fine or not.
5) **Fast Development**  
   We can develop our application fast because of its API.  
   It is also known as RAD (Rapid Application Development).

---

Q. 3) What is Dependency Injection (DI)?  
Ans) If we want to inject one class object to another class object then we use DI.  
In other words, we inject dependency class object to target class object.  
Eg: If we have A class and B class then we need to create object of B class and giving that B object to A is nothing but DI.

---

Q. 4) What are types of DI?  
Ans) There are mainly 3 types of DI:  
1) **Constructor Injection**  
   When one class object is injected into another class using constructor, then it is known as Constructor injection.  
   Object is created by using parameterized constructor and values are injected.
2) **Setter Injection**  
   When we inject one class object to another class using setter method, then we use Setter injection.
3) **Field Injection**  
   In this, we create reference and @Autowired is used.

---

Q. 5) What is IOC in Spring?  
Ans) IOC stands for Inversion Of Control.  
It is also called as spring container.  
Life cycle of object like creating and maintaining object is handled by spring container with the help of DI.  
Let's take an example: as a programmer, we are working on a big project in our organization and creating an object for us is an easy task, we can easily create an object like `Demo x = new Demo`.  
But when it comes to maintaining it, it's not an easy task. So what if there is someone who takes care of creating and maintaining object for us so that we can focus on development and business logic.  
So IOC container takes care of that creation with the help of DI.  
IOC is a principle which uses DI design pattern.

---

Q. 6) What is Configuration File?  
Ans) It is an XML file.  
In that file, it has information of classes and how those classes are configured and linked with each other.  
Eg:  
```xml
<bean id="ob1" class="com.app.EmployeeService">
<property name="empType">
<value>export</value>
</property>
</bean>

```

---

Q. 7) What is Spring Bean?  
Ans) In simple words, Object.  
This object is created, linked with other objects, and destroyed, and all this is done by IOC Container.  
In simple words, an object which is completely controlled by IOC Container is called a bean.

---

Q. 8) Difference between Constructor and Setter Injection?  
Ans) If a class has 4 variables and if we use constructor injection then at the time of object creation we need to pass all 4 variables.  
But in setter injection case, it is not compulsory to pass all 4 variables; you can pass even 2 variables.  
Which means that in constructor injection partial injection is not possible but in setter injection partial injection is possible.  
Whenever we do modify, then constructor injection always creates a new object but in setter injection existing object is modified.

---

Q. 9) What are the Bean Scopes Spring Provides?  
Ans) Spring provides 4 scopes:  
1) **Singleton**  
   In this scope, container will create only one object for our configurations.
2) **Prototype**  
   In this scope, container will create a new object when we access them.
3) **Request**  
   It is for our web application only.  
   So request says that when client/UI makes any request then object is created in container and when response is sent back to Client/UI then object is destroyed.
4) **Session**  
   We can also call this as an HTTP Session.  
   In simple words, we can say login or logout.  
   When login, then container will create its related objects.  
   When logout, then container will destroy its related objects.

---

Q. 10) What is Bean Wiring?  
Ans) Wiring simply means linking of two objects.  
If we want to link then we can achieve that by writing `ref` tag in case of XML.

---
Q. 11) What is Autowiring in Spring and what are its different modes?

Ans) In XML case, to do autowiring we need to add `ref` tag so that it is automated, which is called autowiring. There are 4 modes in case of XML:

- **No:** It will say to container that there is no need to do any autowiring; I will do it manually.
- **byName:** It comes under setter.
- **byType:** It comes under setter.
- **constructor:** It comes under constructor.

---

Q. 12) What is different between @Autowired and @Inject?  
Ans) Both are used for the same purpose.  
@Autowire annotation is used in Spring framework.  
@Inject annotation is given by JavaEE framework.  
Both are used for dependency injection purpose.  
Spring supports both.  
In case of other frameworks, @Inject annotation is used.

---

Q. 13) What is different between @Component and @Bean?  
Ans) Both indicate object creation.  
But the point is, do you have source code.  
If a class is programmer-defined (i.e., we created the class) then we can define @Component at the top of the class.  
But if the class is predefined then we cannot modify the existing code, then we write Java-based configuration @Bean.

---

Q. 14) How many types of IOC container are there in Spring?  
Ans) There are 2 types of IOC Container:  
1) **BeanFactory**  
   BeanFactory is nothing but object creation, destroying object, and all.  
   It will take only XML configurations.
2) **ApplicationContext**  
   It is an interface, it internally extends BeanFactory interface.  
   It also has a few additional features like Annotation support, Reactive Programming, etc.

---

Q. 15) What is the use of @Required Annotation in spring framework?  
Ans) Generally, this annotation is annotated at the top of setter methods.  
Consider there is a variable which needs to be set in setter methods.  
The default will be null if we don't set the value.  
So Spring will never ask to provide value; therefore, we use @Required annotation so the container will say injecting value is mandatory.  
Internally @Autowired follows @Required annotation.

---

Q. 16) What is use of @Autowired annotation in spring?  
Ans) It is used to link two beans.  
Basically, there are different layers like repository layer, service layer, controller layer; one layer we need to link with another layer then we use @Autowired.  
It is recommended for Field Injections.

Ex:
```java
Class ServiceLayer {
    @Autowired
    RepositoryLayer repoLayer;
}

```

---

Q. 17) What is the use of @Qualifier annotation in Spring framework?  
Ans) Generally, Autowire will search for an implementation object.  
If multiple objects are found, then we can use one object of the child type using @Qualifier.

---

Q. 18) What is @Primary Annotation in Spring?  
Ans) It is similar to Qualifier, but @Qualifier we write at the time of @Autowired, whereas @Primary we will write at the bean creation.

---

Q. 19) What are lifecycle methods in Spring?  
Ans) There are 2 methods:  
1) `init`  
2) `destroy`  
These methods are executed by the Spring container.

---

Q. 20) What are different ways of writing Lifecycle methods in Spring?  
Ans) There are 3 ways:  
1) **Using XML**  
   Also known as Declaration Approach.  
   ```xml
   <bean ... init-method="" destroy-method=""></bean>
   ```
2) **Using Spring Interfaces**  
   Also known as Programmatic Approach.  
   - InitializingBean
   - DisposableBean

3) **Using Annotations**  
   - @PostConstruct
   - @PreDestroy

---

Q. 21) What are the Stereotype Annotations?  
Ans) Stereotype annotations are used to represent Java classes as Spring beans.  
There are 5 types of stereotype annotations:  
1) **@Component**  
   To represent any class as a Spring bean, we use the @Component annotation.  

2) **@Service**  
   To represent any class as a Spring bean and also that contains business logic, we use the @Service annotation.  

3) **@Repository**  
   To represent any class as a Spring bean and also that contains persistence logic, we use the @Repository annotation.  

4) **@Controller**  
   In web applications, when we want to handle incoming requests from the client, we use the @Controller annotation.  
   By using that annotation, that class will become a Spring controller class.  
   This is a Spring bean.  

5) **@RestController**  
   To develop distributed applications, we use the @RestController annotation.  
   To represent a Java class as a REST controller, we use the @RestController.  
   This is a Spring bean.

---

Q. 22) What are different modules in Spring?  
Ans) Spring framework contains lots of modules.  
They are also well-organized.  
These modules are grouped together:  
- Core Container  
- Data Access  
- Web  
- AOP (Aspect-Oriented Programming)  
- Instrumentation  
- Test

---

Q. 23) What are profiles in Spring?  
Ans) In Spring, profiles are a way to define different configurations for different environments such as development, testing, and production. When working on projects in organizations, there are often multiple environments with different configurations, such as database connections, mailing configurations, etc.

Instead of changing these configurations manually for each environment, profiles allow us to activate different sets of configurations based on the environment we are working in. 

For example, by specifying `spring.profiles.active=test` at runtime, we can activate the "test" profile, which would use configurations specified in files like `application-test.properties`.

Profiles enable better management of environment-specific configurations and help streamline the deployment process by ensuring that the application behaves consistently across different environments.

---



# Spring Ecosystem
### Spring Ecosystem
- Spring core : - Spring context, enables spring to manage instances of your app. 
	- Spring aspects, helps spring intercept and manipulate methods you define your app.
	- Spring expression language, allow to specifies configuration using specific language.
#### Foundation of spring
- Spring works based on principle of inversion of control(IoC) , instead of allowing app to control execution we give control to some other piece of software - in our case, the spring framework. Through configuration we instruct the framework on how to manage the code we write, which defines he logic of the app.
- Controls refers to action like create an instance , or calling a method
- IoC container glues spring components and components of your application to the framework together. core component that is responsible for instantiating, configuring, and managing the lifecycle of Spring beans.
#### Spring boot
- Spring boot is a project part of the spring ecosystem that introduces the concept of "convention over configuration"

# Spring Context: Defining beans
#### Intro
- Context (also know as the application context in spring app) . it is like a place in the memory of your app in which we add all the object instances that we want the framework to manage.
- Spring uses instances in context to connect your app to various functionalities it provides.
- We will name these object instances "beans".

#### Maven Project Structure
![](../../statics/Pasted%20image%2020241115113148.png)

#### Adding new beans to spring context
- Ways to add bean in context
	- Using @bean annotation
	- Using stereotype annotation
	- Programmatically

**Creating basic project**
- After adding spring-context dependency 
- creating main class , creating instance of spring context
```java
public class Main{
	public static void main(String[] args){
		var context = new AnnotationConfigApplicationContext();
		Parrot p = new Parrot();
	}
}
```

##### Using @Bean annotation
- Steps:
	1. Defining a configuration class:- spring config class is specified by fact it is annotated with @Configuration . all spring related config are done like this.
	2. Create method that return Bean, and annotate method with @Bean:- method name become bean name
	3. Make spring initialize its context using config class
```java
@Configuration
class beanConfig{

	@Bean
	Parrot parrot(){
		var p = new Parrot();
		p.setName("mik");
		return p;
	}
}
```

```java
public class Main{

	public static void main(String[] arg){
		var context = new AnnotationConfigApplicationContext(beanConfig.class);

		Parrot p = context.getBean(Parrot.class);
		String n = p.getName();
	}
}
```

**Adding bean of same type**

```java
@Configuration
public class ProjectConfig {
	@Bean
	Parrot parrot1() {
		var p = new Parrot();
		p.setName("Koko");
		return p;
	}
	@Bean
	Parrot parrot2() {
		var p = new Parrot();
		p.setName("Miki");
		return p;
	}
	@Bean
	Parrot parrot3() {
		var p = new Parrot();
		p.setName("Riki");
		return p;
	}
}
```
we cannot get bean only by specifying the type, it will give exception. hence need to use bean name which is method name by default or can be specified.
```java
public class Main {
	public static void main(String[] args) {
		var context = new
		AnnotationConfigApplicationContext(ProjectConfig.class);
		Parrot p = context.getBean("parrot2", Parrot.class);
		System.out.println(p.getName());
	}
}
```

specifying name:
- `@Bean(name="ri")`
Defining a bean primary
- having multiple bean of same type , we can mark a bean you want to be primary using `@Primary` so if no name is given , exception will not occur.
```java
@Bean
@Primary
Parrot parrot(){
	return new Parrot();
}
```

##### Using Stereotype annotations
- Steps 
	1. Using `@Component` annotation , mark the classes for which you want Spring to add instance
	2. Using `@ComponentScan` annotation over config class , instruct spring where to find the classes you marked.

![](../../statics/Pasted%20image%2020241119064917.png)
in componentscan we list packages where we defined classes with stereotype annotation.

_Although it looks that stereotype approach is more easy due to less code , but bean approach is useful when you want to create bean of classes which you do not own (like class of a library , String , Integer class)_

![](../../statics/Pasted%20image%2020241119065201.png)

**Using @PostConstruct**
- We can add this annotation on a stereotype class method and it will get executed after creation of instance by spring in context. Instructs Spring to call that method after the constructor finishes its execution.

there is also `@PreDestroy` with this annotation , you define a method that spring class immediately before closing and clearing the context. but it is not safe because sometimes spring can also fail to clear context.

##### Creating bean programmatically
- What if one need to register bean in spring depending on specific config of application.
- we need to call registerBean() of ApplicationContext instance. it has four paramentrs
	1. Use the first parameter beanName to define a name for the bean you add in the Spring context. If you don’t need to give a name to the bean you’re adding, you can use null as a value when you call the method.
	2. The second parameter is the class that defines the bean you add to the context. Say you want to add an instance of the class Parrot; the value you give to this parameter is Parrot.class.
	3. The third parameter is an instance of Supplier. The implementation of this Supplier needs to return the value of the instance you add to the context. Remember, Supplier is a functional interface you find in the java.util .function package. The purpose of a supplier implementation is to return a value you define without taking parameters.
	4. The fourth and last parameter is a varargs of BeanDefinitionCustomizer. (If this doesn’t sound familiar, that’s okay; the BeanDefinitionCustomizer is just an interface you implement to configure different characteristics of the bean; e.g., making it primary.) Being defined as a varargs type, you can omit this parameter entirely, or you can give it more values of type BeanDefinitionCustomizer.
![](../../statics/Pasted%20image%2020241119070435.png)

## Depenedency injection and inversion of control

**Inversion of Control (IoC):**

Inversion of Control (IoC) is a design principle where the control flow of a program is inverted, meaning that instead of the application code controlling the flow of execution, the control is handed over to an external container or framework. In a traditional program, the main function or method controls the flow and calls various functions to perform tasks. With IoC, the control is inverted, and a framework or container takes charge of managing the flow and execution of the application.

The primary benefit of IoC is that it promotes a more modular and loosely coupled architecture. Components in the application are decoupled from each other, making it easier to replace or modify individual components without affecting the entire system. IoC is often implemented using a container or framework, such as the Spring IoC container, which manages the lifecycle of objects and their dependencies.

**Dependency Injection (DI):**

Dependency Injection (DI) is a specific implementation of the IoC principle. In a software system, objects often depend on other objects or services to perform their tasks. Traditionally, these dependencies are created within the class that requires them. With dependency injection, dependencies are "injected" into a class from the outside, rather than the class creating them internally.

There are three common types of dependency injection:

1. **Constructor Injection:** Dependencies are provided through the class constructor. This is the most common form of DI.

    ```java
    public class MyClass {
        private MyDependency myDependency;

        public MyClass(MyDependency myDependency) {
            this.myDependency = myDependency;
        }

        // rest of the class...
    }
    ```

2. **Setter Injection:** Dependencies are set through setter methods.

    ```java
    public class MyClass {
        private MyDependency myDependency;

        public void setMyDependency(MyDependency myDependency) {
            this.myDependency = myDependency;
        }

        // rest of the class...
    }
    ```

3. **Method Injection:** Dependencies are injected through methods.

    ```java
    public class MyClass {
        public void doSomething(MyDependency myDependency) {
            // use myDependency to do something
        }

        // rest of the class...
    }
    ```

Dependency injection makes the code more modular, testable, and flexible. It allows for easier substitution of components, as the dependencies can be changed without modifying the class that uses them. The Spring Framework, for example, utilizes dependency injection as a core concept, and it's often referred to as an Inversion of Control container due to its IoC capabilities.

## IOC Container

![](../../statics/Pasted%20image%2020240115080241.png)

In software development, an Inversion of Control (IoC) container is a software component responsible for managing the instantiation and lifecycle of objects within an application. IoC is a design principle that inverts the flow of control in a system, transferring the control of object instantiation and dependencies from the application code to an external container.

The IoC container is often used in conjunction with Dependency Injection (DI). Dependency Injection is a specific form of IoC where the dependencies of a class (i.e., the objects it relies on) are injected into the class from the outside, rather than being created within the class. The IoC container facilitates this process by managing the creation and resolution of these dependencies.

Key features of an IoC container include:

1. **Object instantiation:** The IoC container is responsible for creating instances of classes or objects as needed by the application.

2. **Dependency resolution:** It manages the dependencies of the objects, injecting them into the dependent objects during their creation.

3. **Lifecycle management:** IoC containers often manage the lifecycle of objects, controlling when they are created, used, and eventually disposed of.

4. **Configuration:** The container is typically configured with information about how objects should be created, wired together, and managed.

Popular IoC containers in the Java world include Spring Framework's IoC container, Google Guice, and Apache Dagger. In the .NET ecosystem, the built-in dependency injection system is widely used, and there are also third-party containers like Autofac and Unity.

Using IoC containers and Dependency Injection can lead to more modular, maintainable, and testable code, as it promotes loose coupling between components and allows for easier substitution of dependencies.

### In context of Spring
In the context of the Spring Framework, the Inversion of Control (IoC) container is a key component responsible for managing the lifecycle of Java objects and their dependencies. The IoC container is often referred to as the "Spring container," and it is crucial for achieving loose coupling, modularity, and easier maintenance of applications.

There are two types of IoC containers in the Spring Framework:

1. **BeanFactory:**
   - This is the simplest container and provides the fundamental features of the Spring IoC container.
   - It is responsible for instantiating, configuring, and managing the lifecycle of beans (objects) defined in the Spring application context.
   - BeanFactory supports lazy loading of beans, meaning it only creates beans when they are requested.

2. **ApplicationContext:**
   - ApplicationContext is an extension of the BeanFactory and provides additional features and functionalities.
   - It is more feature-rich and is suitable for most applications.
   - ApplicationContext eagerly loads and initializes beans when the container starts up, providing a more efficient and responsive application.

**Key Features of the Spring IoC Container:**

1. **Bean Definition:**
   - The IoC container relies on bean definitions to understand how to create and configure objects. Bean definitions specify the properties and dependencies of beans.

2. **Bean Lifecycle Management:**
   - The IoC container manages the complete lifecycle of beans, including their instantiation, initialization, use, and eventual disposal (if necessary).

3. **Dependency Injection:**
   - The container injects dependencies into beans during the bean's creation, thus achieving dependency injection. This can be done through constructor injection, setter injection, or method injection.

4. **Aspect-Oriented Programming (AOP):**
   - The Spring IoC container supports AOP, allowing developers to apply cross-cutting concerns (such as logging, security, and transactions) to multiple parts of an application.

5. **Integration with Other Spring Modules:**
   - The IoC container seamlessly integrates with other Spring modules, such as Spring MVC (for web applications), Spring Data (for data access), and Spring Security (for security concerns).

**Configuration in the Spring IoC Container:**

Spring provides two main ways to configure the IoC container:

1. **XML Configuration:**
   - Configuration is done using XML files where beans are defined along with their dependencies and properties.

   ```xml
   <beans>
      <bean id="myBean" class="com.example.MyBean">
         <property name="dependency" ref="dependencyBean" />
      </bean>

      <bean id="dependencyBean" class="com.example.DependencyBean" />
   </beans>
   ```

2. **Annotation-Based Configuration:**
   - Configuration is done using annotations directly in the source code, reducing the need for XML configuration.

   ```java
   @Component
   public class MyBean {
      @Autowired
      private DependencyBean dependency;
   }

   @Component
   public class DependencyBean {
      // ...
   }
   ```

Overall, the IoC container in the Spring Framework plays a crucial role in managing the components of an application, promoting modularity, and facilitating the development of scalable and maintainable software.
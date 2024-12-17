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

# Wiring Beans
## Intro
- we establish relationships among the beans (one bean will have a reference to another to delegate calls when it needs).
- Two ways
	- Link the beans by directly calling the methods that create them (which we’ll call wiring). 
	- Enable Spring to provide us a value using a method parameter (which we’ll call auto-wiring)
- third approach, which is a technique supported by the IoC principle: dependency injection (DI).

## Implementing relationship among beans defined in config file
- for each of the two approaches (wiring and auto-wiring), we have two steps : 
	- Add the person and parrot beans to the Spring context. 
	- Establish a relationship between the person and the parrot.
### Wiring beans using a direct method call b/w the @Bean methods
- first way (wiring) to achieve this is to call one method from another in the configuration class.
```java
@Configuration
public class ProjectConfig {

	@Bean
	public Parrot parrot() {
		Parrot p = new Parrot();
		p.setName("Koko");
		return p;
	}
	
	@Bean
	public Person person() {
		Person p = new Person();
		p.setName("Ella");
		p.setParrot(parrot());
		return p;
	}
}
```
*Disclaimer: If instance of object is already in context then no second instance is created meaning no second instance of parrot is created when method is called if the instance of parrot is already in context*.

### Wiring beans using @Bean annotated method's parameters
- Instead of directly calling the method that defines the bean we wish to refer to, we add a parameter to the method of the corresponding type of object, and we rely on Spring to provide us a value through that parameter
- In this method it does not matter if bean is defined using @Bean or stereotype annotation like @component
```java
@Configuration
public class ProjectConfig {
	@Bean
	public Parrot parrot() {
		Parrot p = new Parrot();
		p.setName("Koko");
		return p;
	}
	
	@Bean
	public Person person(Parrot parrot) {
		Person p = new Person();
		p.setName("Ella");
		p.setParrot(parrot);
		return p;
	}
}
```

## Using @Autowired annotation to inject beans
-  You’ll often encounter this technique, which refers to an annotation named @Autowired.
- Injecting the value in the field of the class, which you usually find in examples and proofs of concept
- Injecting the value through the constructor parameters of the class approach that you’ll use most often in real-world scenarios
- Injecting the value through the setter, which you’ll rarely use in production ready code

### Using @Autowired to inject values through the class fields
- Using annotation over the field.
- We use the stereotype annotation as an alternative to creating the bean using the configuration class.
```java
@Component
public class Person {
	private String name = "Ella";
	@Autowired
	private Parrot parrot;
	
	// Omitted getters and setters
}
```
- Issues
	- you don’t have the option to make the field final (see next code snippet), and this way, make sure no one can change its value after initialization
	- It is more difficult to manage the value yourself at initialization.

### Using @Autowired to inject the values through the constructor
- injecting values into the object’s attributes when Spring creates a bean is using the class’s constructor defining the instance. This approach is the one used most often in production code
- It enables you to define the fields as final ensuring to set values when calling the constructor also helps you when writing specific unit tests where you dont want to rely on spring making the field injection for you
```java
@Component
public class Person {

	private String name = "Ella";
	private final Parrot parrot;
	
	@Autowired
	public Person(Parrot parrot) {
		this.parrot = parrot;
	}
	// Omitted getters and setters
}
```

### Using dependency injection through the setter 
- It does not allow you to make the field final and doesn't help you in making testing easier.

```java
@Component
public class Person {

	private String name = "Ella";
	private Parrot parrot;
	// Omitted getters and setters
	@Autowired
	public void setParrot(Parrot parrot) {
		this.parrot = parrot;
	}
}
```

## Dealing with circular dependencies
- A circular dependency is a situation in which, to create a bean (let’s name it Bean A), Spring needs to inject another bean that doesn’t exist yet (Bean B). But Bean B also requests a dependency to Bean A. So, to create Bean B, Spring needs first to have Bean A. Spring is now in a deadlock. It cannot create Bean A because it needs Bean B, and it cannot create Bean B because it needs Bean A.
- A circular dependency is easy to avoid. You just need to make sure you don’t define objects whose creation depends on the other.

## Choosing from multiple beans in spring context
- scenario in which Spring needs to inject a value into a parameter or class field but has multiple beans of the same type to choose from.
- The identifier of the parameter matches the name of one of the beans from the context (which, remember, is the same as the name of the method annotated with @Bean that returns its value). In this case, Spring will choose the bean for which the name is the same as the parameter.
- The identifier of the parameter doesn’t match any of the bean names from the context. Then you have the following options:
	- You marked one of the beans as primary (as we discussed in chapter 2, using the @Primary annotation). In this case, Spring will select the primary bean for injection.
	- You can explicitly select a specific bean using the @Qualifier annotation,
	- If none of the beans is primary and you don’t use @Qualifier, the app will fail with an exception, complaining that the context contains more beans of the same type and Spring doesn’t know which one to choose.


```java
@Bean
public Person person(@Qualifier("parrot2") Parrot parrot) {
	Person p = new Person();
	p.setName("Ella");
	p.setParrot(parrot);
	return p;
}
```

# Using Abstractions
## Using interface to define contract
- In Java, the interface is an abstract structure you use to declare a specific responsibility. An object implementing the interface has to define this responsibility.
- We can say that the interface specifies the “what needs to happen,” while every object implementing the interface specifies the “how it should happen.”

### Using interface for decoupling responsibility
- When changing an object’s responsibility, we want to avoid the need to change other objects using the changed responsibility. This design’s problem occurs because the DeliveryDetailsPrinter object specifies both what it needs and how it needs.  an object only needs to specify what it needs and stay completely unaware of how the what is implemented
- ![](../../statics/Pasted%20image%2020241217075458.png)

### Implementing the requirement without using framework
- In standard real-world applications, we usually refer to the objects implementing uses cases as services,
- When we have an object working directly with a database, we generally name such an object repository. Sometimes you also find such objects referred to as data access objects (DAO).
- objects whose responsibility is to establish communication with something outside the app, we name these objects proxies,
- We start the implementation of the use case with writing this POJO(A POJO is a simple object without dependencies, only described by its attributes and methods. In our case, the Comment class defines a POJO describing the details of a comment by its two attributes: author and text.) class. The responsibility of this type of object is simply to model the data the app uses, and we call it model
## Using dependency injection with abstraction
### Deciding which object should be part of spring context
- When you add an object to the Spring context, you allow the framework to manage it with some specific functionality the framework provides. If you add the object to be managed by Spring without getting any benefit from the framework, you just over-engineer your implementation
- We use stereotype annotations for the classes that Spring needs to create instances and add these instances to its context. It doesn’t make sense to add stereotype annotations on interfaces or abstract classes because these cannot be instantiated. Syntactically, you can do this, but it is not useful.
- Spring sees the attributes are defined with interface types and is smart enough to search in its context for beans created with classes that implement these interfaces. As we discussed in chapter 2, because we have only one constructor in the class, the @Autowired annotation is optional.
- We only need to tell Spring where to find the classes annotated with stereotype anno- tations and test the app. The next listing presents the project’s configuration class where we use the @ComponentScan annotation to tell Spring where to find the classes annotated with @Component.
- ![](../../statics/Pasted%20image%2020241217080232.png)
- ![](../../statics/Pasted%20image%2020241217080300.png)

### Chossing what to autowire from multiple implementation of an abstraction
- what happens if the Spring context contains more instances that match a requested abstraction
- Using the @Primary annotation to mark one of the beans for implementation as the default
- Using the @Qualifier annotation to name a bean and then refer to it by its name for DI
- The question I usually hear at this moment is, “Now we have two implementations, but Spring will always inject only one of them? Why have both classes in this case?”
- It’s possible that, at some point, you use a dependency that provides an implementation for a specific interface (figure 4.10), but the provided implementation is not suitable for your app, and you choose to define your custom implementation. Then @Primary is your simplest solution.
- ![](../../statics/Pasted%20image%2020241217080614.png)
- ![](../../statics/Pasted%20image%2020241217080627.png)
- ![](../../statics/Pasted%20image%2020241217080646.png)


## Spring context: Bean scopes and life cycle
Spring has multiple different approaches for creating beans and managing their
life cycle, and in the Spring world we name these approaches scopes. In this chapter, we
discuss two scopes you’ll often find in Spring apps: singleton and prototype.

### Using singleton bean scope

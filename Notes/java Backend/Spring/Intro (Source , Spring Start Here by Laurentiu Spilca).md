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

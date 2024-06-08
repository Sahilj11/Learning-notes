## One to One
In Hibernate, a popular Object-Relational Mapping (ORM) framework for Java, a one-to-one mapping represents a relationship where a single entity instance is associated with a single instance of another entity. Here's a comprehensive guide to one-to-one mappings in Hibernate:

### **Concepts in One-to-One Mapping**

1. **Unidirectional One-to-One Mapping**:
   - **Entity A** has a reference to **Entity B**, but **Entity B** does not have a reference back to **Entity A**.
   - Example: A `User` entity having a `Profile` entity associated with it, but `Profile` does not have a reference to `User`.

2. **Bidirectional One-to-One Mapping**:
   - Both **Entity A** and **Entity B** have references to each other.
   - Example: A `User` entity having a `Profile` entity, and the `Profile` entity also has a reference back to `User`.

### **Mapping Strategies**

#### **Primary Key (PK) Association**
- The primary key of the dependent entity (Entity B) is also the foreign key pointing to the primary key of the principal entity (Entity A).
- This makes the relationship tightly coupled.

**Example**:
```java
@Entity
public class User {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    @OneToOne(cascade = CascadeType.ALL)
    @PrimaryKeyJoinColumn
    private Profile profile;

    // getters and setters
}

@Entity
public class Profile {
    @Id
    private Long id;

    @OneToOne(mappedBy = "profile")
    private User user;

    // getters and setters
}
```

#### **Foreign Key (FK) Association**
- A foreign key column is used in the dependent entity to establish the relationship.
- Can be set on either side in unidirectional or bidirectional relationships.

**Example** (Unidirectional):
```java
@Entity
public class User {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    @OneToOne(cascade = CascadeType.ALL)
    @JoinColumn(name = "profile_id")
    private Profile profile;

    // getters and setters
}

@Entity
public class Profile {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    // getters and setters
}
```

**Example** (Bidirectional):
```java
@Entity
public class User {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    @OneToOne(cascade = CascadeType.ALL)
    @JoinColumn(name = "profile_id")
    private Profile profile;

    // getters and setters
}

@Entity
public class Profile {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    @OneToOne(mappedBy = "profile")
    private User user;

    // getters and setters
}
```

### **Annotations in Hibernate for One-to-One Mapping**

- **`@OneToOne`**: Specifies the one-to-one relationship.
- **`@JoinColumn`**: Specifies the foreign key column.
- **`@PrimaryKeyJoinColumn`**: Used when the primary key of the dependent entity is also the foreign key.
- **`mappedBy`**: Used to define the inverse (non-owning) side of the relationship in bidirectional associations.

### **Cascading Options**
- **`CascadeType.ALL`**: Applies all cascading options.
- **`CascadeType.PERSIST`**: Applies only when the parent is persisted.
- **`CascadeType.MERGE`**: Applies when the parent is merged.
- **`CascadeType.REMOVE`**: Applies when the parent is removed.
- **`CascadeType.DETACH`**: Applies when the parent is detached.
- **`CascadeType.REFRESH`**: Applies when the parent is refreshed.

### **Fetching Strategies**

- **Eager Fetching (`FetchType.EAGER`)**: The associated entity is fetched immediately.
- **Lazy Fetching (`FetchType.LAZY`)**: The associated entity is fetched on demand (proxy).

**Example**:
```java
@OneToOne(fetch = FetchType.LAZY)
@JoinColumn(name = "profile_id")
private Profile profile;
```

### **Handling Bidirectional Relationships**

In bidirectional relationships, you must maintain the consistency of the relationship on both sides. If you set one side, you should ensure the other side reflects the change.

**Example**:
```java
public void setProfile(Profile profile) {
    this.profile = profile;
    profile.setUser(this);
}
```

### **Common Use Cases and Best Practices**

1. **Use PK association for tightly coupled entities** where the lifetime of one entity depends on the other.
2. **Use FK association for more flexible relationships**.
3. **Ensure consistency in bidirectional mappings** by updating both sides of the relationship.
4. **Consider lazy loading** to improve performance when the related entity isn't always required.

## One to many
In Hibernate, a one-to-many mapping represents a relationship where a single entity instance (the "one" side) is associated with multiple instances of another entity (the "many" side). This mapping is crucial in scenarios where you need to model real-world relationships, such as a `Customer` having multiple `Orders`.

### **Key Concepts in One-to-Many Mapping**

1. **Unidirectional One-to-Many Mapping**:
   - **Entity A** has a collection of **Entity B** instances, but **Entity B** does not reference back to **Entity A**.
   - Example: A `Department` containing a list of `Employees`.

2. **Bidirectional One-to-Many Mapping**:
   - **Entity A** has a collection of **Entity B** instances, and **Entity B** has a reference back to **Entity A**.
   - Example: A `Department` containing a list of `Employees`, and each `Employee` references back to their `Department`.

### **Mapping Strategies**

#### **Foreign Key (FK) Association**
- **Entity B** contains a foreign key column referencing **Entity A**.
- This is the most common and straightforward mapping strategy.

**Example** (Unidirectional):
```java
@Entity
public class Department {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    @OneToMany(cascade = CascadeType.ALL, fetch = FetchType.LAZY)
    @JoinColumn(name = "department_id")
    private List<Employee> employees;

    // getters and setters
}

@Entity
public class Employee {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    // getters and setters
}
```

**Example** (Bidirectional):
```java
@Entity
public class Department {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    @OneToMany(mappedBy = "department", cascade = CascadeType.ALL, fetch = FetchType.LAZY)
    private List<Employee> employees;

    // getters and setters
}

@Entity
public class Employee {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    @ManyToOne
    @JoinColumn(name = "department_id")
    private Department department;

    // getters and setters
}
```

### **Annotations in Hibernate for One-to-Many Mapping**

- **`@OneToMany`**: Specifies the one-to-many relationship.
- **`@ManyToOne`**: Used in the entity on the many side of the relationship to establish the connection back to the one side.
- **`@JoinColumn`**: Specifies the foreign key column in the target entity.
- **`mappedBy`**: Used to define the inverse (non-owning) side of the relationship in bidirectional associations.

### **Collection Types**

- **`java.util.List`**: Maintains the order of elements.
- **`java.util.Set`**: Ensures no duplicate elements but does not maintain order.
- **`java.util.Map`**: Provides key-value association.

**Example**:
```java
@OneToMany(cascade = CascadeType.ALL, fetch = FetchType.LAZY)
@JoinColumn(name = "department_id")
private Set<Employee> employees;
```

### **Cascading Options**

- **`CascadeType.ALL`**: Applies all cascading options.
- **`CascadeType.PERSIST`**: Propagates persist operation.
- **`CascadeType.MERGE`**: Propagates merge operation.
- **`CascadeType.REMOVE`**: Propagates remove operation.
- **`CascadeType.DETACH`**: Propagates detach operation.
- **`CascadeType.REFRESH`**: Propagates refresh operation.

### **Fetching Strategies**

- **Eager Fetching (`FetchType.EAGER`)**: Fetches associated entities immediately.
- **Lazy Fetching (`FetchType.LAZY`)**: Fetches associated entities on demand.

**Example**:
```java
@OneToMany(fetch = FetchType.LAZY)
@JoinColumn(name = "department_id")
private List<Employee> employees;
```

### **Handling Bidirectional Relationships**

In bidirectional relationships, maintaining the consistency of the association on both sides is crucial. 

**Example**:
```java
public void addEmployee(Employee employee) {
    employees.add(employee);
    employee.setDepartment(this);
}
```

### **Orphan Removal**

- **`orphanRemoval = true`**: Automatically deletes child entities when they are removed from the collection on the parent side.

**Example**:
```java
@OneToMany(mappedBy = "department", cascade = CascadeType.ALL, orphanRemoval = true)
private List<Employee> employees;
```

### **Example Use Case: Department and Employee**

#### Department Entity
```java
@Entity
public class Department {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    @OneToMany(mappedBy = "department", cascade = CascadeType.ALL, fetch = FetchType.LAZY)
    private List<Employee> employees = new ArrayList<>();

    // Getter and setter

    public void addEmployee(Employee employee) {
        employees.add(employee);
        employee.setDepartment(this);
    }

    public void removeEmployee(Employee employee) {
        employees.remove(employee);
        employee.setDepartment(null);
    }
}
```

#### Employee Entity
```java
@Entity
public class Employee {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    @ManyToOne(fetch = FetchType.LAZY)
    @JoinColumn(name = "department_id")
    private Department department;

    // Getter and setter
}
```

## Many to Many
In Hibernate, a many-to-many mapping represents a relationship where multiple instances of one entity are associated with multiple instances of another entity. This is common in scenarios such as students enrolled in multiple courses, or authors writing multiple books. Here’s a comprehensive guide to understanding and implementing many-to-many mappings in Hibernate:

### **Key Concepts in Many-to-Many Mapping**

1. **Bidirectional Many-to-Many Mapping**:
   - **Entity A** has a collection of **Entity B** instances and **Entity B** has a collection of **Entity A** instances.
   - Example: `Student` entities having multiple `Course` entities, and `Course` entities having multiple `Student` entities.

2. **Unidirectional Many-to-Many Mapping**:
   - **Entity A** has a collection of **Entity B** instances, but **Entity B** does not reference **Entity A**.
   - Example: A `User` having multiple `Role`s but `Role` not referencing back to `User`.

### **Mapping Strategies**

#### **Join Table Association**
- A join table is used to map the association between the two entities.
- The join table contains foreign keys referencing the primary keys of both associated entities.

**Example** (Bidirectional):
```java
@Entity
public class Student {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    @ManyToMany(cascade = CascadeType.ALL, fetch = FetchType.LAZY)
    @JoinTable(
        name = "student_course",
        joinColumns = @JoinColumn(name = "student_id"),
        inverseJoinColumns = @JoinColumn(name = "course_id")
    )
    private Set<Course> courses = new HashSet<>();

    // getters and setters
}

@Entity
public class Course {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    @ManyToMany(mappedBy = "courses")
    private Set<Student> students = new HashSet<>();

    // getters and setters
}
```

**Example** (Unidirectional):
```java
@Entity
public class User {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    @ManyToMany(cascade = CascadeType.ALL, fetch = FetchType.LAZY)
    @JoinTable(
        name = "user_role",
        joinColumns = @JoinColumn(name = "user_id"),
        inverseJoinColumns = @JoinColumn(name = "role_id")
    )
    private Set<Role> roles = new HashSet<>();

    // getters and setters
}

@Entity
public class Role {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    // no reference to User
}
```

### **Annotations in Hibernate for Many-to-Many Mapping**

- **`@ManyToMany`**: Specifies the many-to-many relationship.
- **`@JoinTable`**: Specifies the join table and join columns.
- **`@JoinColumn`**: Specifies the foreign key column in the join table.
- **`mappedBy`**: Used to define the inverse (non-owning) side of the relationship in bidirectional associations.

### **Handling Collections**

- **`java.util.Set`**: Preferred for avoiding duplicates and maintaining a cleaner relationship.
- **`java.util.List`**: Can be used if the order of elements is important.

**Example**:
```java
@ManyToMany(cascade = CascadeType.ALL, fetch = FetchType.LAZY)
@JoinTable(
    name = "student_course",
    joinColumns = @JoinColumn(name = "student_id"),
    inverseJoinColumns = @JoinColumn(name = "course_id")
)
private List<Course> courses = new ArrayList<>();
```

### **Cascading Options**

- **`CascadeType.ALL`**: Applies all cascading options.
- **`CascadeType.PERSIST`**: Propagates persist operation.
- **`CascadeType.MERGE`**: Propagates merge operation.
- **`CascadeType.REMOVE`**: Propagates remove operation.
- **`CascadeType.DETACH`**: Propagates detach operation.
- **`CascadeType.REFRESH`**: Propagates refresh operation.

### **Fetching Strategies**

- **Eager Fetching (`FetchType.EAGER`)**: Fetches associated entities immediately.
- **Lazy Fetching (`FetchType.LAZY`)**: Fetches associated entities on demand.

**Example**:
```java
@ManyToMany(fetch = FetchType.LAZY)
@JoinTable(
    name = "student_course",
    joinColumns = @JoinColumn(name = "student_id"),
    inverseJoinColumns = @JoinColumn(name = "course_id")
)
private Set<Course> courses;
```

### **Managing the Join Table**

- The join table should be explicitly defined with appropriate column names to avoid naming conflicts and ensure clarity.
- Indexes can be added to the join table for performance optimization.

**Example**:
```sql
CREATE TABLE student_course (
    student_id BIGINT NOT NULL,
    course_id BIGINT NOT NULL,
    PRIMARY KEY (student_id, course_id),
    FOREIGN KEY (student_id) REFERENCES student(id),
    FOREIGN KEY (course_id) REFERENCES course(id)
);
```

### **Example Use Case: Student and Course**

#### Student Entity
```java
@Entity
public class Student {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    @ManyToMany(cascade = CascadeType.ALL, fetch = FetchType.LAZY)
    @JoinTable(
        name = "student_course",
        joinColumns = @JoinColumn(name = "student_id"),
        inverseJoinColumns = @JoinColumn(name = "course_id")
    )
    private Set<Course> courses = new HashSet<>();

    // getters and setters

    public void addCourse(Course course) {
        courses.add(course);
        course.getStudents().add(this);
    }

    public void removeCourse(Course course) {
        courses.remove(course);
        course.getStudents().remove(this);
    }
}
```

#### Course Entity
```java
@Entity
public class Course {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    @ManyToMany(mappedBy = "courses")
    private Set<Student> students = new HashSet<>();

    // getters and setters
}
```

### **Advanced Topics**

#### **Additional Columns in Join Table**
Sometimes you need to add extra columns to the join table, such as a timestamp or additional metadata.

**Example**:
```java
@Entity
public class Enrollment {
    @EmbeddedId
    private EnrollmentId id;

    @ManyToOne
    @MapsId("studentId")
    private Student student;

    @ManyToOne
    @MapsId("courseId")
    private Course course;

    private LocalDate enrollmentDate;

    // getters and setters
}

@Embeddable
public class EnrollmentId implements Serializable {
    private Long studentId;
    private Long courseId;

    // equals and hashCode
}
```

#### **Orphan Removal**
- **`orphanRemoval = true`**: Automatically deletes orphaned entities in bidirectional relationships.

**Example**:
```java
@Entity
public class Student {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    @ManyToMany(cascade = CascadeType.ALL, fetch = FetchType.LAZY, orphanRemoval = true)
    @JoinTable(
        name = "student_course",
        joinColumns = @JoinColumn(name = "student_id"),
        inverseJoinColumns = @JoinColumn(name = "course_id")
    )
    private Set<Course> courses;

    // getters and setters
}
```

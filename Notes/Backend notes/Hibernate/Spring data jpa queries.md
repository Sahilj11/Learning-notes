In Spring Data JPA, the naming convention for query methods is designed to simplify the creation of queries by using method names to derive the query logic. These methods allow you to construct database queries directly from method names without writing explicit JPQL or SQL. Here’s a comprehensive guide to naming conventions for query methods in Spring Data JPA:

---

### **Basic Query Method Naming**

#### **Syntax**

- **Format**: `findBy` | `readBy` | `queryBy` | `getBy` | `countBy` | `existsBy` + **PropertyName** + **Condition**

#### **Examples**

- `findByLastName(String lastName)`
- `getByEmail(String email)`
- `countByAge(int age)`
- `existsByUsername(String username)`

### **Compound Query Method Naming**

#### **Combining Conditions**

- **Format**: **Base** + `And` | `Or` + **PropertyName**

#### **Examples**

- `findByFirstNameAndLastName(String firstName, String lastName)`
- `getByCityOrCountry(String city, String country)`
- `countByAgeAndStatus(int age, String status)`

### **Special Keywords for Query Methods**

#### **Supported Keywords**

- **Comparisons**: `Is`, `Equals`, `Between`, `LessThan`, `LessThanEqual`, `GreaterThan`, `GreaterThanEqual`
- **Nullability**: `IsNull`, `IsNotNull`, `NotNull`
- **Collections**: `In`, `NotIn`
- **Boolean**: `True`, `False`
- **String Operations**: `Like`, `NotLike`, `StartingWith`, `EndingWith`, `Containing`, `NotContaining`

#### **Examples**

- `findByAgeLessThan(int age)`
- `findByJoinDateBetween(Date startDate, Date endDate)`
- `findByUsernameIn(Collection<String> usernames)`
- `findByActiveTrue()`
- `findByEmailContaining(String email)`

### **Sorting and Pagination**

#### **Sorting**

- **Format**: `findBy` + **PropertyName** + `OrderBy` + **PropertyName** + `Asc` | `Desc`

#### **Examples**

- `findByLastNameOrderByFirstNameAsc(String lastName)`
- `findByAgeOrderByJoinDateDesc(int age)`

#### **Pagination**

- Use `Pageable` and `Sort` parameters for pagination and sorting.

```java
Page<User> findByLastName(String lastName, Pageable pageable);
List<User> findByFirstName(String firstName, Sort sort);
```

### **Derived Query Methods**

#### **Is / Equals**

- **Format**: `findBy` + **PropertyName**

#### **Examples**

- `findByUsername(String username)`: Equivalent to `SELECT u FROM User u WHERE u.username = ?1`

#### **Like / NotLike**

- **Format**: `findBy` + **PropertyName** + `Like` | `NotLike`

#### **Examples**

- `findByUsernameLike(String username)`: Equivalent to `SELECT u FROM User u WHERE u.username LIKE ?1`

#### **In / NotIn**

- **Format**: `findBy` + **PropertyName** + `In` | `NotIn`

#### **Examples**

- `findByStatusIn(Collection<String> statuses)`: Equivalent to `SELECT u FROM User u WHERE u.status IN (?1)`

#### **IsNull / IsNotNull**

- **Format**: `findBy` + **PropertyName** + `IsNull` | `IsNotNull`

#### **Examples**

- `findByLastNameIsNull()`: Equivalent to `SELECT u FROM User u WHERE u.lastName IS NULL`

### **Special Conditions**

#### **Containing / NotContaining**

- **Format**: `findBy` + **PropertyName** + `Containing` | `NotContaining`

#### **Examples**

- `findByDescriptionContaining(String description)`: Equivalent to `SELECT u FROM User u WHERE u.description LIKE %?1%`

#### **StartingWith / EndingWith**

- **Format**: `findBy` + **PropertyName** + `StartingWith` | `EndingWith`

#### **Examples**

- `findByTitleStartingWith(String title)`: Equivalent to `SELECT u FROM User u WHERE u.title LIKE ?1%`

### **Boolean Checks**

#### **True / False**

- **Format**: `findBy` + **PropertyName** + `True` | `False`

#### **Examples**

- `findByActiveTrue()`: Equivalent to `SELECT u FROM User u WHERE u.active = TRUE`

### **Date and Time Queries**

#### **Before / After**

- **Format**: `findBy` + **PropertyName** + `Before` | `After`

#### **Examples**

- `findByCreatedDateBefore(Date date)`: Equivalent to `SELECT u FROM User u WHERE u.createdDate < ?1`

#### **Between**

- **Format**: `findBy` + **PropertyName** + `Between`

#### **Examples**

- `findByJoinDateBetween(Date startDate, Date endDate)`: Equivalent to `SELECT u FROM User u WHERE u.joinDate BETWEEN ?1 AND ?2`

### **Exists Queries**

#### **Existence Check**

- **Format**: `existsBy` + **PropertyName**

#### **Examples**

- `existsByEmail(String email)`: Equivalent to `SELECT COUNT(u) > 0 FROM User u WHERE u.email = ?1`

### **Count Queries**

#### **Counting Records**

- **Format**: `countBy` + **PropertyName**

#### **Examples**

- `countByStatus(String status)`: Equivalent to `SELECT COUNT(u) FROM User u WHERE u.status = ?1`

### **Advanced Query Examples**

#### **Combining Multiple Criteria**

```java
List<User> findByFirstNameAndLastNameAndAgeBetween(String firstName, String lastName, int startAge, int endAge);
```

#### **Sorting with Multiple Fields**

```java
List<User> findByLastNameAndFirstNameOrderByAgeDesc(String lastName, String firstName);
```

### **Practical Examples**

#### **Entity Class**

```java
@Entity
public class User {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;
    private String firstName;
    private String lastName;
    private String email;
    private boolean active;
    private Date createdDate;
    // Getters and setters
}
```

#### **Repository Interface**

```java
public interface UserRepository extends JpaRepository<User, Long> {

    // Simple find
    List<User> findByLastName(String lastName);

    // Compound condition
    List<User> findByFirstNameAndLastName(String firstName, String lastName);

    // Find with Like
    List<User> findByEmailContaining(String email);

    // Find with boolean
    List<User> findByActiveTrue();

    // Find with sorting
    List<User> findByLastNameOrderByFirstNameAsc(String lastName);

    // Find with date range
    List<User> findByCreatedDateBetween(Date startDate, Date endDate);

    // Exists
    boolean existsByEmail(String email);

    // Count
    long countByActive(boolean active);

    // Find with pagination
    Page<User> findByLastName(String lastName, Pageable pageable);
}
```

### **Summary**

1. **Basic Queries**: Use `findBy`, `readBy`, `queryBy`, `getBy` with property names.
2. **Compound Conditions**: Combine with `And`, `Or`.
3. **Special Keywords**: Use keywords like `LessThan`, `Between`, `Like`.
4. **Sorting and Pagination**: Include `OrderBy` for sorting, and `Pageable` for pagination.
5. **Boolean, Date, and Time**: Use `True`, `False`, `Before`, `After`.
6. **Existence and Count**: Use `existsBy` and `countBy`.

Following these conventions helps maintain clarity and consistency in your Spring Data JPA repositories, making them easier to read, maintain, and extend.
## Java Object-Oriented Programming (OOP) and Core Concepts

### Structured vs Object-Oriented Programming
- **Structured Programming**: Focuses on functions and procedures. Data and functions are separate.
  - A procedural approach where the program is divided into small functions.
  - Example languages: C, Pascal.
- **Object-Oriented Programming (OOP)**:
  - Focuses on objects rather than procedures.
  - Objects combine data (state) and methods (behavior).
  - Encapsulation, inheritance, polymorphism, and abstraction make code reusable and modular.
  - Example languages: Java, C++, Python.

#### Key Differences 
| Aspect           | Structured Programming          | Object-Oriented Programming (OOP)            |
|------------------|---------------------------------|----------------------------------------------|
| Focus            | Functions and procedures        | Objects (data + methods)                     |
| Data Handling    | Data and functions are separate | Data and methods are encapsulated in objects |
| Code Reusability | Code is reused via functions    | Code is reused via classes and objects       |
| Scalability      | Harder to scale for large apps  | Easy to extend and maintain                  |
| Examples         | C, Pascal                       | Java, C++, Python                            |

### Class vs Object vs State vs Behavior
- **Class**: A blueprint or template for creating objects. It defines properties (attributes) and behaviors (methods).
  - Example: `class Car { String color; void drive() {} }`
- **Object**: An instance of a class. It has its own state and can perform behaviors defined by the class.
  - Example: `Car myCar = new Car();`
- **State**: The data or attributes of an object at a given time. It represents the object's properties.
  - Example: `myCar.color = "Red";`
- **Behavior**: The methods or functions that an object can perform. It defines what the object can do.
  - Example: `myCar.drive();`

### Object lifecycle
1. **Creation**: An object is created using the `new` keyword, which allocates memory for it.
   - Example: `Car myCar = new Car();`
2. **Initialization**: The object's constructor is called to initialize its state.
   - Example: `Car myCar = new Car("Red");`
3. **Usage**: The object is used by calling its methods and accessing its properties.
   - Example: `myCar.drive();`
4. **Destruction**: The object is no longer referenced and becomes eligible for garbage collection.
   - Example: `myCar = null; // Now eligible for GC`
5. **Garbage Collection**: The Java Virtual Machine (JVM) automatically reclaims memory from objects that are no longer reachable.
6. **Finalization**: Before an object is garbage collected, its `finalize()` method (if overridden) is called to perform cleanup operations.
   - Note: The `finalize()` method is deprecated in Java 9 and later.

### Java is not 100% OOP
- Java is considered an object-oriented programming language, but it is not 100% OOP because:
  - It supports primitive data types (int, char, etc.) that are not objects.
  - It allows static methods and variables, which belong to the class rather than an instance.
  - Operators like `+`, `-`, etc., are not methods of objects.
  - It has features like arrays and enums that are not fully object-oriented.
  - It does not support multiple inheritance of classes (only through interfaces).
  - Default methods in interfaces allow adding new methods without breaking existing implementations.
  - Java provides procedural programming features alongside OOP principles.
  - Example: `public static void main(String[] args) {}` is a static method

### Inheritance vs Abstract class vs Interface
- **Inheritance**: Allows a class (subclass/child class) to inherit properties and methods from another class (superclass/parent class). It promotes code reusability.
  - What: Allows a subclass to reuse code from a parent class. 
  - Why: Reduces duplication and models real-world relationships.
  - How: Using the `extends` keyword.
  - Limitations: Tight coupling - changes in the parent class can affect child classes.
  - Example: `class Dog extends Animal {}`
- **Abstract Class**: Defines a common template with both implemented and unimplemented (abstract) methods.
  - What: A partially implemented class that contains both abstract and concrete methods. 
  - Why: Provides a common template for related classes while allowing specific implementations in subclasses.
  - How: Using the `abstract` keyword and defines abstract methods for subclasses to implement.
  - Example: `abstract class Animal { abstract void makeSound(); }`
- **Interface**: Defines a contract (an interface) that multiple classes can implement. It can contain abstract methods, default methods, and static methods.
  - What: A contract that multiple classes can implement without sharing implementation details.
  - Why: Allows multiple classes (even unrelated) to share common behavior.
  - How: Using the `interface` keyword and requires implementing classes to define all methods.
  - Example: `interface Flyable { void fly(); }`

#### When to use what?
- Use **inheritance** when there is a parent child relationship and you want to reuse code from a parent class. (e.g., `Dog` is an `Animal`).
- Use an **abstract class** when you want to provide a common base with shared code and some methods that must be implemented by subclasses. (e.g., `Animal` with `makeSound()` method).
- Use an **interface** when you want to define a contract that multiple classes can implement, especially when they are not related by inheritance. (e.g., `Flyable` for `Bird` and `Airplane`).

| Aspect                         | Inheritance                                                   | Abstract Class                                                                                         | Interface                                                               |
|--------------------------------|---------------------------------------------------------------|--------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------|
| Definition                     | A subclass inherits methods from a parent class               | A class with abstract and concrete methods                                                             | A blueprint with only method signatures                                 |
| Supports multiple inheritance? | No                                                            | No                                                                                                     | Yes                                                                     |
| Contains abstract methods?     | No                                                            | Yes                                                                                                    | Yes                                                                     |
| Contains concrete methods?     | Yes                                                           | Yes                                                                                                    | Yes (From Java 8: default methods)                                      |
| Can have instance variables?   | Yes                                                           | Yes                                                                                                    | No                                                                      |
| Can have constructors          | Yes                                                           | Yes                                                                                                    | No                                                                      |
| Best use case                  | When a class is a specialized version (IS-A) of another class | When multiple subclasses share common behavior but need some customization in specific implementations | When multiple classes (even unrelated) need to follow the same contract |

#### Design choices in Java Collections Framework
- **Why use interfaces like List, Set, Map?**
  - To define a contract for different types of collections.
  - To allow multiple implementations (e.g., ArrayList, LinkedList for List).
  - To enable polymorphism (e.g., using List reference for different List implementations).
- **Why use abstract classes like AbstractList, AbstractSet?**
  - To provide a skeletal implementation of the collection interfaces.
  - To reduce code duplication among different implementations.
  - To allow developers to create custom collections by extending these abstract classes.
- **Why use concrete classes like ArrayList, HashSet, HashMap?**
  - To provide specific implementations of the collection interfaces.
  - To optimize performance for specific use cases (e.g., fast access in ArrayList, uniqueness in HashSet).
  - To offer ready-to-use data structures for common programming tasks.


### Design Patterns in Java
- What are Design Patterns?
  - Reusable solutions for common coding problems.
- Why use Design Patterns?
  - Make code easier to understand, change, and reuse.
- Where to use Design Patterns?
  - Used in big projects, frameworks, and everyday coding.
- How to use Design Patterns?
  - By applying proven patterns like Singleton, Strategy, Observer, Factory, etc.

#### Singleton Pattern
- Ensures a class has only one instance and provides a global point of access to it.
- When to use:
  - When exactly one instance of a class is needed.
  - When you want to control access to a shared resource.
  - Examples: Logger, Configuration Manager, Database Connection Pool.
- How to implement:
  - Private constructor to prevent instantiation from outside.
  - Private static variable to hold the single instance.
  - Lazy initialization to create the instance when needed.
  - Static method to provide access to the instance.
- Benefits:
  - Controlled access to the single instance.
  - Reduced memory footprint.
  - Consistent behavior across the application.
- Drawbacks:
  - Can be difficult to test (hard to mock).
- Example:
  ```java
  public class Singleton {
      private static Singleton instance;
      private Singleton() {}
      public static Singleton getInstance() {
          if (instance == null) {
              instance = new Singleton();
          }
          return instance;
      }
  }
  ```

#### Strategy Pattern
- Swap different algorithms or strategies at runtime.
- When to use:
  - When you have multiple algorithms for a specific task.
  - When you want to switch algorithms at runtime.
  - Examples: Sorting algorithms, Payment methods.
- How to implement:
  - Create a Strategy interface with a method for the algorithm.
  - Implement concrete strategy classes for each algorithm.
  - Use a context class to hold a reference to a strategy and delegate the algorithm execution.
- Benefits:
  - Promotes code reusability and flexibility.
  - Simplifies code by separating algorithms from the context.
- Drawbacks:
  - Can lead to many small classes.
- Example:
  ```java
  interface PaymentStrategy {
      void pay(int amount);
  }
  class CreditCardPayment implements PaymentStrategy {
      private String cardNumber;
      public CreditCardPayment(String cardNumber) {
          this.cardNumber = cardNumber;
      }
      public void pay(int amount) {
          System.out.println("Paid " + amount + " using Credit Card: " + cardNumber);
      }
  }
  class PayPalPayment implements PaymentStrategy {
      private String email;
      public PayPalPayment(String email) {
          this.email = email;
      }
      public void pay(int amount) {
          System.out.println("Paid " + amount + " using PayPal: " + email);
      }
  }
  class PaymentContext {
      private PaymentStrategy strategy;
      public PaymentContext(PaymentStrategy strategy) {
          this.strategy = strategy;
      }
      public void executePayment(int amount) {
          strategy.pay(amount);
      }
  }
  // Usage
  PaymentContext context = new PaymentContext(new CreditCardPayment("1234-5678-9012-3456"));
  context.executePayment(100); // Paid 100 using Credit Card: 1234-5678-9012-3456
  context = new PaymentContext(new PayPalPayment("user@example.com"));
  context.executePayment(200); // Paid 200 using PayPal: user@example.com
  ```

#### Factory Pattern
- Central place to create objects without exposing the instantiation logic.
- When to use:
  - You want control over the object creation process.
  - Examples: Document creation (Word, PDF), Payment method selection (CreditCard, PayPal).
- How to implement:
  - Factory method decides what object to return based on input parameters.
- Benefits:
  - Decouples object creation from usage.
- Drawbacks:
  - Can lead to complex factory classes.
- Example (Payment scenario):
  ```java
  interface PaymentService {
      void pay(int amount);
  }
  class CreditCardPaymentService implements PaymentService {
      private String cardNumber;
      public CreditCardPaymentService(String cardNumber) {
          this.cardNumber = cardNumber;
      }
      public void pay(int amount) {
          System.out.println("Paid " + amount + " using Credit Card: " + cardNumber);
      }
  }
  class PayPalPaymentService implements PaymentService {
      private String email;
      public PayPalPaymentService(String email) {
          this.email = email;
      }
      public void pay(int amount) {
          System.out.println("Paid " + amount + " using PayPal: " + email);
      }
  }
  class PaymentFactory {
      public PaymentService getPaymentService(String type, String detail) {
          if (type == null) {
              return null;
          }
          if (type.equalsIgnoreCase("CREDITCARD")) {
              return new CreditCardPaymentService(detail);
          } else if (type.equalsIgnoreCase("PAYPAL")) {
              return new PayPalPaymentService(detail);
          }
          return null;
      }
  }
  // Usage
  PaymentFactory paymentFactory = new PaymentFactory();
  PaymentService payment1 = paymentFactory.getPaymentService("CREDITCARD", "1234-5678-9012-3456");
  payment1.pay(100); // Paid 100 using Credit Card: 1234-5678-9012-3456
  PaymentService payment2 = paymentFactory.getPaymentService("PAYPAL", "user@example.com");
  payment2.pay(200); // Paid 200 using PayPal: user@example.com

  // This is an example of the Strategy + Factory Pattern: the factory creates the correct payment service based on the input type
  // Step 1: Define the PaymentService interface and its implementations (Strategy Pattern)
  // Step 2: Choosing Strategy with Factory Pattern

  // Enhanced version using Map to store PaymentService by paymentType

  class PaymentServiceRegistry {
      private Map<String, PaymentService> serviceMap = new HashMap<>();
      
      static {
            // Register default services
          serviceMap.put("CREDITCARD", new CreditCardPaymentService("default-card"));
          serviceMap.put("PAYPAL", new PayPalPaymentService("default-email"));
      }

      public PaymentService getService(String type) {
          return serviceMap.get(type.toUpperCase());
      }
  }

  // Usage
  PaymentServiceRegistry registry = new PaymentServiceRegistry();

  PaymentService payment1 = registry.getService("CREDITCARD");
  payment1.pay(100); // Paid 100 using Credit Card: 1234-5678-9012-3456

  PaymentService payment2 = registry.getService("PAYPAL");
  payment2.pay(200); // Paid 200 using PayPal: user@example.com

  // This enhanced version uses a Map to store and retrieve PaymentService implementations by paymentType, making it easy to add new types and improving scalability.
  ```
  
#### Factory Pattern in Spring Boot with Map
- Implementing the Factory pattern in Spring Boot, particularly with a Map for managing different implementations, offers a clean and extensible way to create objects without exposing the instantiation logic.
- The central idea is to have a factory class that holds a Map where keys represent identifiers (e.g., String, Enum) and values are instances of different concrete implementations of a common interface or abstract class. When a client requests an object, the factory uses the provided identifier to retrieve the corresponding instance from the map.
- Steps for Implementation:
  - Define a Common Interface/Abstract Class: Create an interface or abstract class that all concrete implementations will adhere to. This defines the contract for the objects being created.
  - Example:
    ```java
    public interface PaymentProvider {
        void processPayment(double amount);
        String getType(); // To identify the specific provider
    }
    ```
  - Create Concrete Implementations: Implement the common interface/abstract class with specific logic for each type of object.
  - Example:
    ```java
        @Service("creditCardPayment") // Spring bean name
    public class CreditCardPaymentProvider implements PaymentProvider {
        @Override
        public void processPayment(double amount) {
            System.out.println("Processing credit card payment of " + amount);
        }
        @Override
        public String getType() {
            return "CREDIT_CARD";
        }
    }

    @Service("paypalPayment") // Spring bean name
    public class PaypalPaymentProvider implements PaymentProvider {
        @Override
        public void processPayment(double amount) {
            System.out.println("Processing PayPal payment of " + amount);
        }
        @Override
        public String getType() {
            return "PAYPAL";
        }
    }
    ```
    - Create the Factory Class:
      - Inject a Map where the keys are the identifiers (e.g., String or Enum) and the values are instances of the common interface. Spring can automatically populate this map with all beans implementing the specified interface.
      - Provide a method to retrieve the correct implementation based on the identifier.
    - Example:
    ```java
    @Service
    public class PaymentProviderFactory {

        private final Map<String, PaymentProvider> paymentProviderMap;

        // Spring automatically injects all PaymentProvider beans into this map
        public PaymentProviderFactory(Map<String, PaymentProvider> paymentProviderMap) {
            this.paymentProviderMap = paymentProviderMap;
        }

        public PaymentProvider getPaymentProvider(String type) {
            PaymentProvider provider = paymentProviderMap.get(type);
            if (provider == null) {
                throw new IllegalArgumentException("Unknown payment provider type: " + type);
            }
            return provider;
        }
    }
    ```
    - Note: If you need to map by a custom property like getType() instead of the bean name, you might need to manually populate the map in a @PostConstruct method or use a custom FactoryBean.
    - Client Usage: Autowire the factory and use it to obtain the desired object.
    - Example:
    ```java
    @Service
    public class PaymentService {

        private final PaymentProviderFactory paymentProviderFactory;

        public PaymentService(PaymentProviderFactory paymentProviderFactory) {
            this.paymentProviderFactory = paymentProviderFactory;
        }

        public void initiatePayment(String paymentType, double amount) {
            PaymentProvider provider = paymentProviderFactory.getPaymentProvider(paymentType);
            provider.processPayment(amount);
        }
    }
    ```
    
- Benefits of Using Factory Pattern with Map in Spring Boot:
  - Loose Coupling: The client code is decoupled from the concrete implementations.
  - Extensibility: Adding new payment providers (or other object types) only requires creating a new implementation class and registering it as a Spring bean; no changes to the factory or client code are needed.
  - Centralized Object Creation: The factory manages the creation and retrieval of objects, promoting consistency.

#### Observer Pattern
- One-to-many notification system.
- When to use:
  - Need listeners for state changes.
  - Examples: Button click events, data change notifications.
- How to implement:
  - Register listeners (observers) to a subject.
  - Notify all observers when the subject's state changes.
- Benefits:
  - Promotes loose coupling between subject and observers.
  - Supports dynamic relationships between objects.
- Drawbacks:
  - Can lead to performance issues if many observers are notified frequently.
  - Example:
    ```java
    interface Listener {
        void onClick();
    }
    
    class Button {
        private Listener listener;
    
        public void setListener(Listener listener) {
            this.listener = listener;
        }
    
        public void click() {
            if (listener != null) {
                listener.onClick();
            }
        }
    }
    
    // Usage
    public class ObserverPattern {
        public static void main(String[] args) {
            Button button = new Button();
    
            Listener listener = () -> System.out.println("Button clicked!");
            button.setListener(listener);
            
            button.click(); // Output: Button clicked!
        }
    }
    ```

    

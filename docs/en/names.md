### Names

#### Table of content

 - [Classes, interfaces and enumerators](names.md#class)
 - [Packages](names.md#package)
 - [Methods, variables and constants](names.md#vars)

#### <a name="class" /> Classes, interfaces and enumerators

Classes, interfaces and enumerators names **must** follow the [CamelCase](http://en.wikipedia.org/wiki/CamelCase) using letters from `a` to `Z` and numbers from `0` to `9`

```java
public class Person {
    // something
}

public class PersonService {
    // something
}

public enum URLs {
    // something
}

public interface Service {
    // something
}

public class ServiceV2 implements Service {
    // something
}
```

#### <a name="package" /> Packages

Package names **must** be in lower case using only letters from `a` to `z`

```java
com.luizalabs.project.core
com.luizalabs.project.utils
```

#### <a name="vars" /> Methods, variables and constants

Methods and variables names, in general, **must** use only letters from `a` to `Z` in [lowerCamelCase](http://en.wikipedia.org/wiki/CamelCase#Variations_and_synonyms). In the case of `static final` constants you **must** use upper case letters separated by underscore (`_`).

```java
public class MyClass {
    private static final int DEFAULT_LIMIT = 16;
    private String fullName;
    private String description;
}

public enum OrderStatus {
    NEW,
    PENDING_PAYMENT,
    DELIVERED,
    CANCELLED;
}
```

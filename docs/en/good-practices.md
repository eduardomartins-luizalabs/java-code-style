### Programming Practices

#### Table of content
  
  - [Imports](good-practices.md#import)
  - [Override notation](good-practices.md#override)
  - [Exception treatment](good-practices.md#exception)
  - [Static classes and methods](good-practices.md#static)
  - [Avoid redundancy](good-practices.md#redundancy)

#### <a name="import" /> Imports

  - **Never** use

```java
import com.luizalabs.*;
```

  - **Avoid** using static imports

```java
import static com.luizalabs.Class.method;
```

  - Try to keep the imports on the following order

```java
import com.luizalabs;
import com.thirdpart; // apache, google, spring
import java.lang;
import javax;
```

#### <a name="override" /> Override notation

Every time a method is overrided from a extended `Class` or an `Interface` you **must** use the `@Override` notation

```java
public MyClass extends SomeClass implements SomeInterface {
    @Override
    void interfaceMethod() {
        // ...
    }

    @Override
    protected void extendedClassMethod() {
        // ...   
    }
}
```

#### <a name="exception" /> Exception treatment

As a general recommendation, try to avoid treating exceptions by writting something like `catch (Exception exception)`, you may try to give some context to this exception when possible<br><br>
  
  - If some exception is caught only to continue the workflow and nothing will be done with it, you must name it with `ignored`, so it will justify why nothing is done with it

```java
try {
    doSomething(param1, param2);
} catch (Exception ignored) {
    // do nothing, but do not stop the workflow
}

// some code doing something
```

  - If your unit test must verify if an exception is thrown, you **must** use `@Test(expected = Exception.class)`, if the framework you are using does not allow this, make it clear on the code that the exception was expected

```java
@Test
public void shouldThrowIllegalArgumentException() {
    try {
        doSomething(x);
        Assert.fail();
    } catch (IllegalArgumentException expected) {
        // If don't catch this exception, test should fail
    }
}

@Test(expected = IllegalArgumentException.class)
public void shouldThrowIllegalArgumentException() {
    doSomething(x);
}
```

#### <a name="static" /> Static classes and methods

  - **Never** creates intances to call static methods

```java
//Correct
Foo.bar();

//Wrong
Foo foo = new Foo();
foo.bar();
```

  - If your class has only static methods, its constructor must be private, then you can prevent developers to make the mistake above

```java
public class Foo {
    private Foo() { }

    public static void bar() {
        // do something
    }
}
```

#### <a name="redundancy" /> Avoid redundancy

  - Try to avoid doing things such as

```java
public interface SomeInterface {
    // Every constant on an interface, by definition
    // is public static final
    public static final int SOME_CONSTANT = 16;

    // All methods, by default, are public inside an interface
    public void someMethod();
}
```

  - Instead you **should** do something like

```java
public interface SomeInterface {
    // Every constant on an interface, by definition
    // is public static final
    int SOME_CONSTANT = 16;

    // All methods, by default, are public inside an interface
    void someMethod();
}
```
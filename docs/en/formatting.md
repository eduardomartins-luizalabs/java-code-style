### Code Formatting

#### Table of content

 - [Indentation](formatting.md#indentation)
 - [Code layout](formatting.md#layout)
 - [Class variable definitions](formatting.md#class-order)
 - [Line length](formatting.md#line-length)

#### <a name="indentation" /> Indentation

  - You **must** use 4 spaces to indent, **never** use tabs (`\t`)
  - You **must** use braces on the same line when declaring a method
  - You **must** leave a space after finishing method declaration

```java
//Correct
public void method() {
    // do something
}

//Wrong
public void method()
{
    // do something
}

//Wrong
public void method(){
    // do something
}
```

  - `if`, `else if`, `else`, `for` and `while` statements **must** use braces even when the body is empty or contains only a single statement

```java
//Correct
for (int i = 0; i < 100; i++) {
    System.out.println(i);
}

//Wrong
for (int i = 0; i < 100; i++)
    System.out.println(i);

//Correct
if (x > 2) {
    System.out.println(x);
}

//Wrong
if (x > 2)
    System.out.println(x);
```

  - You **must not** use more than one blank line to separate code

```java
//Correct
public void method() {
    if (x > 10) {
        // do something
    }
\n
    anotherMethod();
}

//Wrong
public void method() {
    if (x > 10) {
        // do something
    }
\n
\n
    anotherMethod();
}
```

  - You **must** leave an empty line after the end brace of methods ans constructors
  - You **must not** leave an empty line on the beginning of methods ans constructors
  - On `if - else`, `for`, `while` and `try - catch - finally` statements you **must** leave an empty line after that if there is more code on the method, otherwise, you **must not** have an empty line

```java
//Correct
public void correct() {
    if (x > y) {
        // do something
    } else if (y > x * x) {
        // do something
    } else {
        // do something
    }
}

private void anotherCorrectMethod() {
    for (int i = 0; i < 100; i++) {
        // do something
    }

    int x = 0;
}

//Wrong
public void wrong() {

    if (x > y) {
    // something
    } else if (y > x * x) {
        // do another thing
    } else {
        // do something
    }

}
private void anotherWrongMethod() {

    for(int i = 0; i < 100; i++) {
        // do something
    }
    try {
        // do something
    } catch(Exception e) {
        // do something
    }

}
```

  - On `enum`'s you **must** always declare one value by line and in case of complex constructors, **always** declare one parameter by line
  - It **is not required** to follow alphabetical order
  - After all values declared, you **must** insert `;`

```java
//Correct
public enum OrderStatus {
    NEW(
        "New order",
        1122334
    ),
    PAYMENT_NOT_AUTHORIZED(
        "Payment not authorized",
        1122334
    );

    // ...
}

//Wrong
public enum OrderStatus {
    NEW("New order", 1122334 ),
    PAYMENT_NOT_AUTHORIZED("Payment not authorized", 1122334);

    // ...
}

//Wrong
public enum OrderStatus {
    NEW,PAYMENT_NOT_AUTHORIZED;
}
```

#### <a name="layout" /> Code layout

  - All methods calls **must** be followed by parentheses, without spaces between the method name and the parentheses

```java
public void method() {
    //Correct
    callingMethod(a, b);
    //Wrong
    callingMethod (a, b);
}
```

  - After declaring statements (`if`, `else`, `for`, ...) you **must** enter a blank space before `{` (braces) and `(` (parentheses)

```java
//Correct
if (x > y) {
    return true;
} else {
    return false;
}

try {
    // do something
} catch (Exception e) {
    // Exception tratement
} finally {
    // do something
}

//Wrong
if(x > y){
    return true;
}else{
    return false;
}

try{
    // do something
}catch(Exception e) {
    // Exception tratement
} finally {
    // do something
}
```

  - Commas (`,`) **must** have a blank space after it
  - Semicolons (`;`) inside a `for` statement **must** also have a blank space after it

```java
//Correct
for (i = 0; i < 100; i++) {
    i += 1;
}

doSomething(a, b, c)

//Wrong
for (i = 0;i < 100;i++) {
    i += 1;
}

doSomething(a,b,c)
```

  - Binary operators (`+`, `-`, ...) **must** have a blank space on both sides

```java
//Correct
int x = a + 1;
int y = (2 * x) + (3 * z);
//Wrong
int x = a+1;
int x = a +1;
int x = a+ 1;
int z = 2*x + 3*y;
int z = (2*x) + (3*y);
```

  - Unary operators **must** be immediately preceded or followed by their operand

```java
//Correct
i++;
++i;

//Wrong
i ++;
-- i;
```

  - When casting a class, you **must** separate by spaces

```java
//Correct
(Example) x.get(3);
//Wrong
( Example )x.get(3);
(Example)x.get(3);
```

#### <a name="class-order" /> Class variable definitions

When building your class, you **must** follow the order:

  - `public` attributes
  - `private` attributes
  - constructors
  - methods

When declaring the attributes, you **must** have in mind this order:

  - `static final`
  - `static`
  - `final`

When declaring methods, you **must** follow a logic order of declaritions, **avoid** declaring new methods at the end of the file unless there is a logic explanation for that<br>

If you have methods with the same name, keep them together

```java
public class MyClass {
    public static final Random random = new Random();
    public static Math math;
    public final String name = "Labs"
    public String a;
    private static final String ID = "ABC";
    private static String attribute;
    private final String ANOTHER_ID = "DEF";
    private String b;

    public Example(String a, String b) {
        this.a = a;
        this.b = b;
    }

    public void doNothing() {

    }

    private void doNothing(int x) {

    }
}
```

#### <a name="line-length" /> Line length

**Avoid** writting lines with more than 120 characters, this limit helps you when reading the code on [GitHub](https://github.com) and monitors with low screen resolution

```java
String correct = "Mussum ipsum cacilds, vidis litro abertis. Consetis " 
            + "adipiscings elitis. Pra lá , depois divoltis porris, paradis. " 
            + "Paisis, filhis, espiritis santis. Mé faiz elementum girarzis, " 
            + "nisi eros vermeio, in elementis mé pra quem é amistosis quis leo.";

String wrong = "Mussum ipsum cacilds, vidis litro abertis. Consetis adipiscings elitis. Pra lá , depois divoltis porris, paradis. Paisis, filhis, espiritis santis. Mé faiz elementum girarzis, nisi eros vermeio, in elementis mé pra quem é amistosis quis leo.";
```
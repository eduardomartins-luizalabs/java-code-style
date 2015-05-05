### Javadoc Style

The javadoc style is described in this section

-------------------------------

- The javadoc line **must not** be higher than 120 characters:

```java
//Correct

/**
 * Less than 120 characters on the whole line description
 *
 * @param var Variable of the method, used for something
 */
public void doSomething(final String var) {...}

//Wrong

/**
 * This is the wrong way of doing it, this method contains more than 120 characters on the whole line, which makes it incorret and because of this documento, not right, so it would be better to split those lines, like we will see below
 *
 * @param var Variable of the method, used for something
 */
public void doSomething(final String var) {...}

//Correct

/**
 * This is the wrong way of doing it, this method contains more than 120 
 * characters on the whole line, which makes it incorret and because of this
 * document, not right, so it would be better to split those lines, like we
 * can see here.
 *
 * @param var Variable of the method, used for something
 */
public void doSomething(final String var) {...}
```

- Separate the description and the tags with a blank line

```java
// Correct

/**
 * This method sum two numbers
 *
 * @param a First number of the equation
 * @param b Second number of the equation
 * @return Returns a sum of the parameters
 */
public void sum(int a, int b) {
    return a + b;
}

//Wrong

/**
 * This method sum two numbers
 * @param a First number of the equation
 * @param b Second number of the equation
 * @return Returns a sum of the parameters
 */
public void sum(int a, int b) {
    return a + b;
}
```

- The `@author` **must** always come after the description of the class

```java
/**
 * This is a class.
 *
 * @author author (author at luizalabs.com).
 */
public class Class {...}
```

- The javadoc should be directly above what he is describing, blank lines **must not** exist

```java
//Correct

/**
 * This method sum two numbers
 *
 * @param a First number of the equation
 * @param b Second number of the equation
 * @return Returns a sum of the parameters
 */
public void sum(int a, int b) {
    return a + b;
}

//Wrong

/**
 * This method sum two numbers
 *
 * @param a First number of the equation
 * @param b Second number of the equation
 * @return Returns a sum of the parameters
 */

public void sum(int a, int b) {
    return a + b;
}
```

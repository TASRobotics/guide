# Javadoc

Javadoc comments are a way to document Java code.

```java
/**
 * Adds two numbers.
 * @param a the first number
 * @param b the second number
 * @return the sum of the two numbers
 */
public int add(int a, int b) {
    return a + b;
}
```

To start a Javadoc comment, just put your cursor on the line above a method, or whatever you want to document, then type `/**` and press enter. Eclipse will insert the rest of the comment automatically, including any necessary tags.

# Where to use

Javadoc comments should be present for the following things:

- Top-level classes, interfaces, and enums
- Public methods
    - Except if the method overrides or implements another method
- Public constructors
- Public variables, constants, and inner classes/interfaces/enums of a class

Exception: You can omit Javadoc comments if the thing you are documenting has a self-explanatory name, and there is not much to say in the comment.

The list above is just where Javadoc comments are required. You are welcome to add Javadoc comments for other things, such as private methods, if you want to.

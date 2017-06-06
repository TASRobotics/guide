# Formatting

Note: The example code in this document is to demonstrate the formatting. The code itself makes no sense.

# Indentation

## Indenting blocks

Use **4 spaces** for indenting blocks.

Note: **This does NOT mean that you have to press the space bar 4 times to indent!**

Eclipse by default inserts a "hard tab" character (ASCII code 9) when you press the tab key on your keyboard. But it can be configured to insert 4 spaces instead when you press it.

If we use project-specific configuration in Eclipse it can be configured to insert spaces and pushed to the git repo so people on the team don't all have to change their Eclipse settings.

```java
if (example) {
    println("I am indented with 4 spaces");
}
```

## Indenting continuation lines

Use **8 spaces** for indenting continuation lines. Continuation lines are new lines created from line wrapping.

See also [Line length limit](#line-length-limit).

# Line length limit

If you have a line with more than **100 characters** in it, you should break it up into multiple lines. This is called line wrapping.

Exceptions:
- Package declaration
- Imports
- Things that cannot be split like long URLs

Note: Feel free to break up statements into multiple lines even if they don't exceed 100 characters. It often increases readability.

When wrapping lines, don't just break at the point closest to the limit. You should break the line in a way that it is easy to read.

# Braces (`{}`)

## Places where braces are optional

**Use braces even when they are optional**, such as in `if` and `for` statements where there is only one statement in the body.

Omitting braces when they are optional is a possible source of bugs, and also leads to the [dangling else problem](https://en.wikipedia.org/wiki/Dangling_else).

```java
// GOOD

if (condition) {
    doSomething();
} else {
    doSomethingElse();
}

while (true) {
    println("This will loop forever");
}

// BAD

if (condition)
    doSomething();
else
    doSomethingElse();

while (true)
    println("This will loop forever");
```

## Positioning of braces

This is best described with examples.

```java
public class someClass { // opening brace on the same line

    public void someMethod() { // same for methods

        for (int i = 0; i < 100; i++) { // same for control structures
            println(i);
        } // closing brace on its own line

        if (condition) {
            doSomething();
        } else { // closing brace combined with else
            doSomethingElse();
        }

    }

}
```

For a more formal definition, this is from [Google's style guide](https://google.github.io/styleguide/javaguide.html):

> - No line break before the opening brace.
> - Line break after the opening brace.
> - Line break before the closing brace.
> - Line break after the closing brace, only if that brace terminates a statement or terminates the body of a method, constructor, or named class. For example, there is no line break after the brace if it is followed by `else` or a comma.

## Array initializers and enums

If you have a short array initializer you can format it like this:

```java
int[] x = { 1, 2, 3 };
```

But if you have a long array initializer you can also format it like a block.

```java
int[] x = {
    calculateFirstElement(),
    calculateSecondElement(),
    calculateThirdElement()
};
```

The same thing applies to enum declarations.

# Spacing

## Blank lines

You can add blank lines in between statements to group them logically. This is useful for long methods or if a class has many instance variables.

Also, there should be one blank line between constructors/methods as well as before the first thing in a class and after the last thing.

See also [Structure](structure.md) for more rules about blank lines.

## Spaces

There should be no extra spaces at the end of a line.

For inside the line, put one space:

- Between any keyword and opening parenthesis (`(`), e.g. `if`, `for`
- Before any opening brace (`{`)
    - Except if it is preceded by another opening brace (like when you are initializing a matrix)
- Inside both braces of an array initializer
- Between any closing brace (`}`) and keyword, e.g. `else` (see also [Positioning of braces](#positioning-of-braces))
- Before and after binary or ternary operators
    - Except the `.` operator
- After `,` or `;`
- After `//` that starts a comment
- Before `//` if there is code before it

```java
public void someMethod(int x, int y) {
    if (x == y) { // this is a comment
        someObject.methodCall(1, 2, 3);
    } else {
        int z = 0;
        for (int i = 0; i < x; i++) {
            z += y * i + 1;
        }
    }
}
```

# Decimals

Always put a `0` in front of the `.` if it is optional.

```java
0.1
-0.1
```
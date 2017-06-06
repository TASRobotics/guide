# Design

# Constants

Constants are values that do not change while the program is running. They should be `static` and `final` in a class. See also [Naming of constants](naming.md#constants).

- `static` because they are always the same so there is no reason to make a copy for each instance.
- `final` because they do not change.

There are often values that are inserted into the code and might need to be adjusted later. For instance:

```java
turnLeft();
wait(1.5);
moveForward();
```

```java
if (distance >= 5 && distance <= 10) {
    // ...
}
```

The numbers can be moved to [the top of the class](structure.md#order-of-declarations) and declared as constants, since they should not be changed when the program is running.

```java
public class SomeClass {

    private static final double DELAY_AFTER_TURN = 1.5;
    private static final int MIN_DISTANCE = 5;
    private static final int MAX_DISTANCE = 10;
```

```java
turnLeft();
wait(DELAY_AFTER_TURN);
moveForward();
```

```java
if (distance >= MIN_DISTANCE && distance <= MAX_DISTANCE) {
    // ...
}
```

This way they can be easily modified later. This is especially useful if the value is used in multiple places as you only have to change it in one place in the code.

This doesn't mean that all literals should be declared as constants. For example:

```java
for (int i = 0; i < array.length; i++) {

}
```

The `0` in the loop isn't something that is likely to be changed, so it should stay there.

# Enums

An enum is a set of fixed values. For example:

```java
enum AutoMode {
    PlaceGear,
    ShootBalls,
    CrossLine
}
```

To check which one a variable is, you can use a switch statement.

```java
switch (mode) {
    case PlaceGear:
        // place a gear
        break;
    case ShootBalls:
        // shoot some balls
        break;
    case CrossLine:
        // cross the line
        break;
}
```

You should use enums when you would otherwise use a certain set of integers or strings. For example, instead of doing this:

```java
private int climbState; // -1 = down, 0 = stopped, 1 = up
```

You can do this:

```java
private enum ClimbState { Down, Stopped, Up }
private ClimbState climbState;
```

Enum values must be prefixed with the enum name everywhere except in `case` labels, so it's okay if they have generic names.

```java
climbState = ClimbState.Down;
```

Enums are useful because:
- They are more clear/descriptive than numbers.
- They can be verified by the computer.
    - Eclipse will warn you when some enum value is missing in a switch statement.
    - If you have a method that takes an enum value, it is impossible to pass an invalid value to it.
- They have a `toString` method, so if you want to show a string representation of some enum value, you can just call `toString` on it.

Enums can either be placed inside a class, if they logically belong to a class, or they can be in their own files like classes.

# Access modifiers

Variables that do not need to be accessed outside of the class should be `private`.

Variables that do need to be accessed outside of the class should usually be `private` and have a getter. If it also needs to be modified outside of the class, then it should also have a setter. See also [Naming of getters and setters](naming.md#getters).

```java
class SomeClass {

    private int someVariable;

    // getter
    public int getSomeVariable() {
        return someVariable;
    }

    // setter
    public void setSomeVariable(int someVariable) {
        this.someVariable = someVariable;
    }

}
```

Methods that do not need to be called outside of the class should be `private`.

Methods that do need to be called outside of the class should be `public`.

The same applies for other things that can be in a class (constructors, constants, etc.)
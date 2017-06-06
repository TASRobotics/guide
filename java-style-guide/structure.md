# Structure

# Order of top-level declarations in a file

Each file should have declarations in the following order, with one blank line separating each one:

1. Package statement
2. [Import statements](#import-statements)
3. Class/interface/enum

```java
package org.usfirst.frc.team4253.robot;

import edu.wpi.first.wpilibj.SampleRobot;
import edu.wpi.first.wpilibj.SmartDashboard;

public class Robot extends SampleRobot {
    // ...
}
```

# Import statements

You don't really have to worry about import statements since **Eclipse organizes them for you**. Just click Source > Organize Imports or press Ctrl+Shift+O to let Eclipse organize the imports. You should do this when:

- You edit the imports manually.
- You stop using some class, so the import of that class is not needed anymore.
    - Make sure you do this so you don't end up with unused imports.

# Order of declarations in classes

Declarations in classes should generally have the following order, with one blank line separating each section:

1. Constants
2. Static variables
3. Instance variables
4. Constructors
5. Methods
6. Nested classes/interfaces

The methods should be ordered in some logical way. Don't just always add new methods to the bottom of the class. Also, overloads of a method should always be next to each other.

The order specified here is just a general rule. If there is a good reason to put something somewhere else, then do it.

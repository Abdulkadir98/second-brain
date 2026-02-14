## Problem:
You have a class that uses a lot of conditionals to change behavior based on the fields of the class. For e.g. lot of `if-else` or `switch-case` statements that change the behavior based on the current value or set of values in the `private` fields of the `class`
## Solution:
Encapsulate all the behavior related to the "state" (private fields) into its own `class`

### Components
1. Context class - Class the varies it behavior based on the State
2. State interface - Defines the behavior of each individual state
3. Concrete State - Defines the concrete implementation of each State

Similar to Strategy pattern but the key difference is that, Concrete states may be aware of each other (required to transition between different states) but the Strategies in Strategy pattern almost never know anything about each other


Reference: https://refactoring.guru/design-patterns/state


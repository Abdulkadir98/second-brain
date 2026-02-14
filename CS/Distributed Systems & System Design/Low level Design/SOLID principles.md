Depency Inversion Principle - It states that High level modules should not depend on low-level modules, both should depend on abstractions.

Benefits:
Lesser coupling - the high level module does not depend on concrete implementations of lower level modules, it depends on `interface` types that fulfill a contract, making it flexible and easier to test.

Violation of this principle leads to code that is not flexible, not easily testable, and may lead to violation of other principles such as Open-Closed principle when time comes to add new functionality.
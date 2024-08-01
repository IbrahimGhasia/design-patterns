# State

State is a behavioral design pattern that allows an object to change the behavior when its internal state changes.

The pattern extracts state-related behaviors into separate state classes and forces the original object to delegate the work to an instance of these classes, instead of acting on its own.

**Usage examples:** The State pattern is commonly used to convert massive switch-base state machines into objects.

## Code Example Explanation

### Key components in the code:

-   **Context Class:** This class maintains an instance of a State subclass that defines the current state. It provides a method to transition to a different state and delegates requests to the current state.

-   **State Class (Abstract):** This is an abstract class that declares methods for handling requests. Subclasses will implement these methods to handle the requests in a state-specific way.

-   **ConcreteStateA and ConcreteStateB Classes:** These are subclasses of the State class. Each class implements the methods declared in the State class and defines specific behavior for each state.

### Detailed Explanation

**Context Class**

-   **Properties**

    -   private state!: State: This holds the current state of the context.

-   **Constructor**

    -   constructor(state: State): Initializes the context with an initial state and transitions to it.

-   **Methods:**

    -   transitionTo(state: State): Changes the state of the context to the new state and sets the context for the new state.
    -   request1(): Delegates the request to the current state’s handle1 method.
    -   request2(): Delegates the request to the current state’s handle2 method.

**State Class (abstract)**

-   **Properties**

    -   protected context!: Context: This holds a reference to the context.

-   **Methods:**

    -   setContext(context: Context): Sets the context for the state.
    -   handle1() and handle2(): Abstract methods that must be implemented by concrete states.

**ConcreteStateA Class**

-   **Methods:**

    -   handle1(): Implements the behavior for request1 in ConcreteStateA and transitions to ConcreteStateB.
    -   handle2(): Implements the behavior for request2 in ConcreteStateA.

**ConcreteStateB Class**

-   **Methods:**

    -   handle1(): Implements the behavior for request1 in ConcreteStateB.
    -   handle2(): Implements the behavior for request2 in ConcreteStateB and transitions to ConcreteStateA.

## How to run the code

Follow these steps to set up and run the TypeScript code:

1. **Install Dependencies:**
   Open your terminal and run the following command to install the necessary dependencies:

    ```
    npm install
    ```

2. **Navigate to the Project Directory:**
   Change to the BehavioralPattern directory:

    ```
    cd BehavioralPattern
    ```

3. **Navigate to the State Pattern Directory:**
   Change to the State directory:

    ```
    cd State
    ```

4. **Run the TypeScript Code:**
   Use ts-node to run the TypeScript file (assuming you have ts-node installed as a local dependency):

    ```
    npx ts-node index.ts
    ```

## References

For more information on the State Design Pattern, you can visit the following resource:

-   [Refactoring Guru - State Design Pattern](https://refactoring.guru/design-patterns/state)
-   [Code Example](https://refactoring.guru/design-patterns/state/typescript/example)

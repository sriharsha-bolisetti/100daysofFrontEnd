- The top-level React component managed the primary state.
- In this type of data architecture, data flows downward to child components.
- To make changes to state, child components propagate events up to their parent components by calling prop-functions.
- Any state mutations took place at the top and then flowed downward again.
- Managing application state with React components works fine for a wide variety of applications. However, as apps grow in size and complexity, managing state inside of React components (or the component-state paradigm) can become cumbersome.
- A common pain point is the `tight coupling between user interactions and state changes`
- For complex web applications, oftentimes a single user interaction can affect many different, discrete parts of the state.
- Action -> Dispatcher -> Store -> View
- The `View` dispatches actions that describe what happened.
- The `Store` receives these actions and determines what state changes should occur.
- After the state updates, the new state is pushed to the `View`

Example:

- Email example in flux -> we no longer have a single function handling email clicks that describe all of the state changes. Instead, React notifies the store (through an action) that the user clicked on an email. We can organize the store such that each discrete part of the state has its own logic for handling updates.
- In addition to decoupling interaction handling and state changes, Flux also provides the following benefits:

1. Breaking up state management logic
2. React components are simpler.
3. Mis-match between the state tree and the DOM tree

### Redux's Key Ideas

1. All of your application's data is in a single data structure called the `state` which is held in the `store`
2. Your app reads the `state` from this `store`
3. The `state` is never mutated directly outside the `store`
4. The `views` emit `actions` that describe what happened
5. A `new state` is created by combining the `old state` and the `action` by a function called the `reducer`

- Redux library provides a function for creating stores, `createStore()`
- This function returns a store object that keeps an internal variable, `state`. In addition, it provides a few methods for interacting with the store.

#### Factory Pattern

- Ubiquitous pattern in Javascript for creating complex objects like redux store object.
- The factory pattern provides a `closure for variables declared inside the factory function`
- At the top of createStore(), we declare the variable state:

```
function createStore(reducer) { let state = 0;
// ...
```

- state is a private variable. Only the functions declared inside of createStore() have access to it.
- Furthermore, because `state` is inside of this closure, the variables "lives on" between function calls.
- Example factory function

```
function createAdder() {
    let value = 0;
    const add = (amount) => (value = value + amount);
    const getValue = () => (value);
    return { add,
    getValue,
    }
}
```

- We first call the factory to instantiate our adder object.
- The private variable value is initialized to 0:
  `const adder = createAdder();`
- While createAdder() has returned our new object and exited, the variable value lives on in memory as 0.
- Whenever we call add(), we are modifying this same value:

```
adder.add(1);
adder.getValue(); // => 1
adder.add(1);
adder.getValue(); // => 2
adder.add(5);
adder.getValue(); // => 7
```

- Importantly, `value` is only accessible to the functions inside the factory. This prevents unintended reads or writes.

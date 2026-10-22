# React — Queueing State Updates

## 1. State updates are queued

Calling a state setter does **not immediately change the state variable in the current render**.

```jsx
const [number, setNumber] = useState(0);

setNumber(number + 1);
```

The current `number` remains the value from the current render. React **requests another render**.

---

## 2. React batches state updates

When multiple state updates happen inside one event handler, React waits until the handler finishes before processing them.

```jsx
setNumber(number + 1);
setNumber(number + 1);
setNumber(number + 1);
```

React doesn't immediately re-render after every `setNumber()`.

Instead:

```text
Event handler starts
      ↓
setState()
setState()
setState()
      ↓
Event handler finishes
      ↓
React processes updates
      ↓
Re-render
```

This is called **batching**.

### Why batching?

It:

- reduces unnecessary re-renders
- improves performance
- prevents partially updated UI

---

# 3. Why `setNumber(number + 1)` three times gives only +1

Consider:

```jsx
const [number, setNumber] = useState(0);

setNumber(number + 1);
setNumber(number + 1);
setNumber(number + 1);
```

You might expect:

```text
0 → 1 → 2 → 3
```

But you get:

```text
0 → 1
```

### Why?

Because **state is a snapshot of the current render**.

Inside this particular event handler:

```jsx
number === 0;
```

So React effectively receives:

```jsx
setNumber(0 + 1);
setNumber(0 + 1);
setNumber(0 + 1);
```

or:

```jsx
setNumber(1);
setNumber(1);
setNumber(1);
```

The three updates don't see the results of one another.

---

# 4. Updater functions solve this

When you want to update the **same state multiple times**, use an updater function:

```jsx
setNumber((n) => n + 1);
setNumber((n) => n + 1);
setNumber((n) => n + 1);
```

Now React can process them sequentially.

```text
initial state = 0

0 → n + 1 → 1
1 → n + 1 → 2
2 → n + 1 → 3
```

Result:

```text
3
```

---

# 5. What is an updater function?

This:

```jsx
(n) => n + 1;
```

is an **updater function**.

It means:

> "React, take the previous state and calculate the next state from it."

So:

```jsx
setNumber((n) => n + 1);
```

means:

```text
previous state → calculate next state
```

rather than:

```text
replace state with this already-calculated value
```

---

# 6. How React processes updater functions

Suppose:

```jsx
number = 0;

setNumber((n) => n + 1);
setNumber((n) => n + 1);
setNumber((n) => n + 1);
```

React creates a queue:

```text
┌─────────────────┐
│ n => n + 1      │
├─────────────────┤
│ n => n + 1      │
├─────────────────┤
│ n => n + 1      │
└─────────────────┘
```

Then processes it:

```text
0 → 1
1 → 2
2 → 3
```

Final state:

```text
3
```

The output of one updater becomes the input of the next.

---

# 7. Two types of values passed to a setter

This is the **most important part** of the section.

When you call:

```jsx
setNumber(...)
```

you can give React either:

### A. A value

```jsx
setNumber(5);
```

This means:

> **Replace the state with 5.**

### B. An updater function

```jsx
setNumber((n) => n + 1);
```

This means:

> **Calculate the next state using the previous state.**

---

# 8. Mixing replacement and updater functions

Consider:

```jsx
setNumber(number + 5);
setNumber((n) => n + 1);
```

Initial:

```text
number = 0
```

### Step 1

```jsx
setNumber(number + 5);
```

Since `number` is `0`:

```jsx
setNumber(5);
```

Queue:

```text
replace with 5
```

### Step 2

```jsx
setNumber((n) => n + 1);
```

Queue becomes:

```text
replace with 5
n => n + 1
```

React processes it:

```text
0 → 5
5 → 6
```

Final:

```text
6
```

---

# 9. Replacement after an updater overrides it

Consider:

```jsx
setNumber(number + 5);
setNumber((n) => n + 1);
setNumber(42);
```

Initial:

```text
number = 0
```

Queue:

```text
replace with 5
n => n + 1
replace with 42
```

Processing:

```text
0 → 5
5 → 6
6 → 42
```

Final:

```text
42
```

The final replacement wins.

### Mental model

Think of the queue as instructions:

```text
VALUE       → "replace the current state"
FUNCTION    → "calculate from the current queued state"
```

So:

```jsx
setNumber(5);
setNumber((n) => n + 1);
```

means:

```text
replace → 5
calculate → 5 + 1 = 6
```

But:

```jsx
setNumber((n) => n + 1);
setNumber(42);
```

means:

```text
calculate → ...
replace → 42
```

Final result = **42**.

---

# 10. Updater functions must be pure

Updater functions:

```jsx
setNumber((n) => n + 1);
```

must only **calculate and return the next state**.

Good:

```jsx
setNumber((n) => n + 1);
```

Bad:

```jsx
setNumber((n) => {
  console.log("something");
  doSomething();
  return n + 1;
});
```

Don't perform side effects inside updater functions.

React may run updater functions more than once in **Strict Mode** to help detect mistakes.

---

# 11. Naming updater parameters

You can name the parameter whatever you want:

```jsx
setEnabled((e) => !e);
```

or:

```jsx
setEnabled((enabled) => !enabled);
```

or commonly:

```jsx
setEnabled((prevEnabled) => !prevEnabled);
```

For example:

```jsx
setCount((prevCount) => prevCount + 1);
```

All mean the same basic thing.

---

# 12. When should you use an updater function?

### Normal update

If you only need to update state once:

```jsx
setCount(count + 1);
```

is perfectly fine.

### Multiple updates based on previous state

Use:

```jsx
setCount((c) => c + 1);
```

For example:

```jsx
function handleClick() {
  setCount((c) => c + 1);
  setCount((c) => c + 1);
  setCount((c) => c + 1);
}
```

Result:

```text
count + 3
```

---

# Cheat Sheet

```text
┌──────────────────────────────────────────┐
│        React State Update Queue          │
├──────────────────────────────────────────┤
│ setState(value)                          │
│ → replace state with that value          │
│                                          │
│ setState(prev => next)                   │
│ → calculate next state from previous     │
│                                          │
│ Multiple updates in one event             │
│ → React batches them                     │
│                                          │
│ State variable in current render          │
│ → doesn't change immediately             │
│                                          │
│ Multiple updates based on previous state │
│ → use updater function                   │
└──────────────────────────────────────────┘
```

### The one mental model to remember

```jsx
setNumber(number + 1);
```

means:

> **"Replace the state with this value."**

while:

```jsx
setNumber((n) => n + 1);
```

means:

> **"Take whatever state is currently in the queue and calculate the next value from it."**

That's the core idea behind **queueing a series of state updates**.

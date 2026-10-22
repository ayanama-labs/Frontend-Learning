> **Treat objects stored in React state as immutable. Don't mutate them directly. Create a new object and pass it to the state setter.**

# React — Updating Objects in State

## 1. State can contain objects

You can store an object in state normally:

```jsx
const [position, setPosition] = useState({
  x: 0,
  y: 0,
});
```

React doesn't prohibit objects in state. The important part is **how you update them**.

---

# 2. Mutation vs replacement

### ❌ Mutation

```jsx
position.x = 5;
```

This directly changes the existing object.

That's called **mutation**.

The problem is that React doesn't know you've changed the object because you didn't call the state setter:

```jsx
setPosition(...)
```

So React doesn't get the signal to render again.

### ✅ Correct approach

Create a new object:

```jsx
setPosition({
  x: 5,
  y: position.y,
});
```

Now React receives a **new object reference** and knows it needs to render again.

### Mental model

```text
❌ mutate existing object
state object
    ↓
change property
    ↓
React doesn't know


✅ create new object
old object
    ↓
new object
    ↓
setState(newObject)
    ↓
React re-renders
```

---

# 3. Why React wants immutability

React state should be treated as **read-only**.

Even though JavaScript objects are technically mutable:

```jsx
const person = { name: "Ayan" };

person.name = "John"; // JavaScript allows this
```

if the object is in React state, don't do this:

```jsx
person.name = "John";
```

Instead:

```jsx
setPerson({
  ...person,
  name: "John",
});
```

React's documentation specifically recommends treating state objects as immutable.

---

# 4. The object spread operator

Suppose:

```jsx
const [person, setPerson] = useState({
  firstName: "Barbara",
  lastName: "Hepworth",
  email: "bhepworth@sculpture.com",
});
```

You only want to change `firstName`.

### ❌ Don't do this

```jsx
person.firstName = "Ayan";
```

### ❌ This would also be dangerous

```jsx
setPerson({
  firstName: "Ayan",
});
```

Why?

Because you've thrown away:

```text
lastName
email
```

### ✅ Use spread

```jsx
setPerson({
  ...person,
  firstName: "Ayan",
});
```

This means:

```text
copy all old properties
        +
replace firstName
```

---

# 5. How spread works

Given:

```jsx
const person = {
  firstName: "Barbara",
  lastName: "Hepworth",
  email: "hello@example.com",
};
```

This:

```jsx
{
  ...person,
  firstName: "Ayan"
}
```

produces:

```jsx
{
  firstName: "Ayan",
  lastName: "Hepworth",
  email: "hello@example.com"
}
```

The order matters.

```jsx
{
  ...person,
  firstName: "Ayan"
}
```

The later `firstName` overrides the copied value.

---

# 6. Updating form state

This pattern is very common:

```jsx
function handleFirstNameChange(e) {
  setPerson({
    ...person,
    firstName: e.target.value,
  });
}
```

Similarly:

```jsx
function handleLastNameChange(e) {
  setPerson({
    ...person,
    lastName: e.target.value,
  });
}
```

And:

```jsx
function handleEmailChange(e) {
  setPerson({
    ...person,
    email: e.target.value,
  });
}
```

This allows you to keep an entire form in **one object** rather than creating separate state variables for every field.

---

# 7. Spread is shallow

This is extremely important.

Consider:

```jsx
const person = {
  name: "Niki",
  artwork: {
    title: "Blue Nana",
    city: "Hamburg",
  },
};
```

If you do:

```jsx
const newPerson = {
  ...person,
};
```

you've copied only the **top level**.

The nested `artwork` object is still the same reference.

Conceptually:

```text
newPerson
   │
   ├── name → copied
   │
   └── artwork ──────┐
                     │
                same object
```

That's why spread is called **shallow copy**.

---

# 8. Updating a nested object

Suppose:

```jsx
const [person, setPerson] = useState({
  name: "Niki",
  artwork: {
    title: "Blue Nana",
    city: "Hamburg",
    image: "...",
  },
});
```

You want to change:

```jsx
person.artwork.city;
```

### ❌ Don't mutate

```jsx
person.artwork.city = "New Delhi";
```

### ✅ Copy every level that you're changing

```jsx
setPerson({
  ...person,
  artwork: {
    ...person.artwork,
    city: "New Delhi",
  },
});
```

Think from the inside outward:

```text
1. Copy artwork
   ↓
{ ...person.artwork, city: "New Delhi" }

2. Copy person
   ↓
{ ...person, artwork: newArtwork }

3. Set new person
   ↓
setPerson(...)
```

---

# 9. The "copy all the way up" rule

This is probably the **most important rule** for nested objects.

If you want to change:

```jsx
person.artwork.city;
```

you need a new:

```text
city
  ↓
artwork
  ↓
person
```

In code:

```jsx
setPerson({
  ...person,
  artwork: {
    ...person.artwork,
    city: "New Delhi",
  },
});
```

### General pattern

If state looks like:

```jsx
state = {
  a: {
    b: {
      c: value,
    },
  },
};
```

and you want to change `c`:

```jsx
setState({
  ...state,
  a: {
    ...state.a,
    b: {
      ...state.a.b,
      c: newValue,
    },
  },
});
```

You create new copies from the changed property **all the way up to the state object**.

---

# 10. Why not mutate nested objects?

Because objects can share references.

For example:

```jsx
const artwork = {
  city: "Hamburg",
};

const person = {
  artwork,
};

const otherPerson = {
  artwork,
};
```

Both objects point to the same `artwork`.

```text
person ──────┐
             ↓
          artwork
             ↑
             │
otherPerson ─┘
```

If you mutate:

```jsx
artwork.city = "Delhi";
```

you have changed what **both** objects see.

This is one reason immutable updates make state easier to reason about. The source explains that objects in state can be shared and that mutation can affect previous render snapshots.

---

# 11. Immer: a shortcut for nested updates

Nested object updates can become repetitive:

```jsx
setPerson({
  ...person,
  artwork: {
    ...person.artwork,
    city: "Lagos",
  },
});
```

**Immer** lets you write code that looks like mutation:

```jsx
updatePerson((draft) => {
  draft.artwork.city = "Lagos";
});
```

But Immer internally creates the necessary copies while preserving the previous state.

You can use:

```jsx
import { useImmer } from "use-immer";
```

instead of:

```jsx
import { useState } from "react";
```

and install it with:

```bash
npm install use-immer
```

---

# 12. When should you use Immer?

Immer is particularly useful when:

- state is deeply nested
- you have many nested updates
- spread syntax becomes repetitive
- you don't want to flatten your state structure

For simple objects, regular spread syntax is usually straightforward:

```jsx
setPerson({
  ...person,
  name: "John",
});
```

The source also notes that deeply nested state may be worth **flattening** rather than continually copying many levels.

---

# The complete mental model

### Primitive state

```jsx
setCount(10);
```

Replace the value.

### Object state

```jsx
setPerson({
  ...person,
  name: "John",
});
```

Create a new object and replace the old one.

### Nested object state

```jsx
setPerson({
  ...person,
  artwork: {
    ...person.artwork,
    city: "Delhi",
  },
});
```

Create new copies **all the way up**.

### Deeply nested state

Consider:

```text
1. Flatten the state
       OR
2. Use Immer
```

---

# Cheat Sheet

```text
React Object State
│
├── ❌ Never mutate state directly
│      person.name = "John"
│
├── ✅ Create a new object
│      setPerson({
│        ...person,
│        name: "John"
│      })
│
├── Spread is shallow
│      { ...person }
│
├── Nested update
│      copy every level
│
│      setPerson({
│        ...person,
│        artwork: {
│          ...person.artwork,
│          city: "Delhi"
│        }
│      })
│
└── Deep nesting
       ├── Flatten state
       └── or use Immer
```

## One rule to memorize

> **Don't change an object that React gave you from state. Create a new object, copy the old data with `...`, change what you need, and pass the new object to the setter.**

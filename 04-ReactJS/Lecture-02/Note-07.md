> **Treat arrays in React state as immutable. Don't modify the existing array. Create a new array and give it to the state setter.**

# React — Updating Arrays in State

## 1. Arrays in state are read-only

JavaScript arrays are mutable:

```js
const arr = [1, 2, 3];

arr.push(4); // JavaScript allows this
```

But when an array is in React state:

```jsx
const [artists, setArtists] = useState([]);
```

don't mutate it directly:

```jsx
artists.push(newArtist); // ❌
artists.pop(); // ❌
artists[0] = newArtist; // ❌
```

Instead, create a **new array** and pass it to the setter.

---

# 2. Array operation cheat sheet

This table is worth memorizing:

| Goal    | ❌ Mutates state               | ✅ Use instead        |
| ------- | ------------------------------ | --------------------- |
| Add     | `push()`, `unshift()`          | spread, `concat()`    |
| Remove  | `pop()`, `shift()`, `splice()` | `filter()`, `slice()` |
| Replace | `arr[i] = ...`, `splice()`     | `map()`               |
| Sort    | `sort()`                       | copy first            |
| Reverse | `reverse()`                    | copy first            |

---

# 3. `slice()` vs `splice()` — VERY IMPORTANT

These names look almost identical but behave completely differently.

### `slice()` → doesn't mutate

```js
const result = arr.slice(1, 3);
```

It creates a copy/portion of the array.

### `splice()` → mutates

```js
arr.splice(1, 1);
```

It modifies the original array.

So remember:

```text
slice  → safe
splice → mutates
```

---

# 4. Adding an item

Suppose:

```jsx
const [artists, setArtists] = useState([]);
```

### ❌ Don't use `push()`

```jsx
artists.push(newArtist);
```

You're modifying the existing state array.

### ✅ Use spread

```jsx
setArtists([...artists, newArtist]);
```

This means:

```text
old items + new item
```

For example:

```jsx
setArtists([...artists, { id: nextId++, name: name }]);
```

---

# 5. Add to the beginning

You can also prepend an item:

```jsx
setArtists([newArtist, ...artists]);
```

Compare:

### Add to end

```jsx
[...artists, newArtist];
```

### Add to beginning

```jsx
[newArtist, ...artists];
```

So spread replaces the need for:

```text
push()    → add at end
unshift() → add at beginning
```

---

# 6. Removing an item → `filter()`

This is one of the most useful React patterns.

Suppose:

```js
artists = [
  { id: 1, name: "A" },
  { id: 2, name: "B" },
  { id: 3, name: "C" },
];
```

You want to remove ID `2`.

Use:

```jsx
setArtists(artists.filter((artist) => artist.id !== 2));
```

`filter()` creates a **new array** containing only elements that pass the condition.

Result:

```text
A
C
```

The original array isn't modified.

### Mental model

```js
filter(condition);
```

means:

> "Keep the items for which this condition is true."

So:

```js
artist.id !== 2;
```

means:

> Keep everything whose ID isn't 2.

---

# 7. Changing items → `map()`

Use `map()` when you want to transform or replace items.

Example:

```jsx
const nextShapes = shapes.map((shape) => {
  if (shape.type === "circle") {
    return {
      ...shape,
      y: shape.y + 50,
    };
  }

  return shape;
});

setShapes(nextShapes);
```

The important pattern is:

```text
map
 ↓
check item
 ↓
changed? → return NEW item
unchanged? → return original item
```

---

# 8. Replacing one array item

Suppose:

```js
counters = [0, 0, 0];
```

You click index `1` and want:

```text
[0, 1, 0]
```

Don't do:

```js
counters[1] = counters[1] + 1; // ❌
```

Instead:

```jsx
setCounters(
  counters.map((counter, i) => {
    if (i === index) {
      return counter + 1;
    }

    return counter;
  }),
);
```

`map()` creates the new array.

---

# 9. Inserting at a specific position

Suppose you want to insert an item at index `1`.

Use:

```jsx
const nextArtists = [
  ...artists.slice(0, insertAt),
  newArtist,
  ...artists.slice(insertAt),
];

setArtists(nextArtists);
```

Think of it as:

```text
items before
     +
new item
     +
items after
```

For example:

```text
[A, B, C, D]

insert X at index 2

[A, B] + [X] + [C, D]

→ [A, B, X, C, D]
```

---

# 10. Sorting and reversing

Methods like:

```js
sort();
reverse();
```

**mutate the array**.

So don't do:

```jsx
list.reverse(); // ❌
```

Instead, copy first:

```jsx
const nextList = [...list];

nextList.reverse();

setList(nextList);
```

Or:

```jsx
const nextList = [...list];

nextList.sort();

setList(nextList);
```

### General pattern

```jsx
const copy = [...array];

copy.someMutatingMethod();

setArray(copy);
```

---

# 11. ⚠️ Copying the array isn't enough

This is probably the **most important subtle point** in this section.

Suppose:

```js
const list = [
  { id: 1, seen: false },
  { id: 2, seen: false },
];
```

You do:

```js
const nextList = [...list];
```

You have created a new **array**, but the objects inside are still the same objects.

Conceptually:

```text
list ────────┐
             ↓
          object A
             ↑
             │
nextList ────┘
```

So this is still wrong:

```js
const nextList = [...list];

nextList[0].seen = true; // ❌
```

Because:

```text
nextList[0] === list[0]
```

Both point to the **same object**.

Therefore you've actually mutated the original state.

---

# 12. Updating an object inside an array

This is where **array + object immutability** come together.

Suppose:

```js
const list = [
  { id: 1, name: "A", seen: false },
  { id: 2, name: "B", seen: false },
];
```

You want to change `seen` for ID `1`.

Use:

```jsx
setList(
  list.map((item) => {
    if (item.id === 1) {
      return {
        ...item,
        seen: true,
      };
    }

    return item;
  }),
);
```

What happens?

```text
old array
   ↓
map()
   ↓
ID 1? ── yes → create NEW object
   │
   └──────────→ no → keep existing object
   ↓
new array
   ↓
setState()
```

---

# 13. Why `map()` is perfect for this

The pattern is:

```jsx
array.map((item) => {
  if (item.id === targetId) {
    return {
      ...item,
      property: newValue,
    };
  }

  return item;
});
```

This gives you:

- a **new array**
- a **new object only for the item that changed**
- unchanged items can keep their existing references

That's exactly what you want for immutable state updates.

---

# 14. A powerful mental model

Imagine this state:

```jsx
const [todos, setTodos] = useState([
  { id: 1, text: "Learn React", done: false },
  { id: 2, text: "Learn Docker", done: false },
]);
```

### Add

```jsx
setTodos([...todos, newTodo]);
```

### Remove

```jsx
setTodos(todos.filter((todo) => todo.id !== id));
```

### Update

```jsx
setTodos(
  todos.map((todo) => (todo.id === id ? { ...todo, done: true } : todo)),
);
```

These three patterns cover a **huge amount of real React code**.

---

# 15. Immer

If these immutable updates become too repetitive, you can use **Immer**.

Without Immer:

```jsx
setMyList(
  myList.map((artwork) => {
    if (artwork.id === artworkId) {
      return {
        ...artwork,
        seen: nextSeen,
      };
    }

    return artwork;
  }),
);
```

With Immer:

```jsx
updateMyTodos((draft) => {
  const artwork = draft.find((a) => a.id === artworkId);

  artwork.seen = nextSeen;
});
```

This looks like mutation, but you're modifying an Immer **draft**, not the original state. Immer generates the next immutable state for you.

---

# The React Array Cheat Sheet

| Operation                  | Use                                          |
| -------------------------- | -------------------------------------------- |
| Add at end                 | `[...arr, item]`                             |
| Add at beginning           | `[item, ...arr]`                             |
| Remove                     | `arr.filter(...)`                            |
| Replace/update             | `arr.map(...)`                               |
| Insert                     | `[...arr.slice(0,i), item, ...arr.slice(i)]` |
| Reverse                    | `[...arr].reverse()`                         |
| Sort                       | `[...arr].sort(...)`                         |
| Update object inside array | `map()` + object spread                      |
| Complex nested updates     | Immer                                        |

---

# The 3 patterns you should memorize

### Add

```jsx
setItems([...items, newItem]);
```

### Delete

```jsx
setItems(items.filter((item) => item.id !== id));
```

### Update

```jsx
setItems(
  items.map((item) => (item.id === id ? { ...item, name: newName } : item)),
);
```

These three patterns are the **core of updating arrays in React state**.

### Final mental model

```text
React state array
       │
       ├── Add       → spread
       │
       ├── Remove    → filter
       │
       ├── Update    → map
       │
       ├── Insert    → slice + spread
       │
       ├── Sort      → copy first
       │
       └── Nested object
             ↓
        copy array
             +
        copy object
```

The fundamental rule is:

> **Never mutate an existing array or an existing object inside that array. Create new copies along the path of the change, then set the new state.**

# React — 10 Focused Exercises

## 1. Build a Component-Based Profile ✅

**Topics:** Components, JSX, component composition

Build:

```text
App
└── ProfileCard
    ├── Avatar
    ├── ProfileInfo
    │   ├── Name
    │   └── Bio
    └── FollowButton
```

Requirements:

- Every major UI section should be a separate component.
- `App` should compose the components.
- Use JSX.
- Don't put the entire UI inside `App`.

**Before coding:**

Draw the component tree.

**Think about:**

> What does each component's responsibility actually mean?

---

# 2. Build a Reusable Product Card

**Topics:** Props, reusable components, data flow

Create:

```jsx
<ProductCard
  name="Mechanical Keyboard"
  price={2499}
  category="Electronics"
  image="..."
/>
```

Render **3 different products** using the same component.

Requirements:

- `ProductCard` must receive all product-specific data through props.
- Don't hardcode product information inside the component.
- Display name, price, category, and image.

Example data:

```js
const products = [
  {
    id: 1,
    name: "Mechanical Keyboard",
    price: 2499,
    category: "Electronics",
    image: "...",
  },
  {
    id: 2,
    name: "Wireless Mouse",
    price: 1499,
    category: "Electronics",
    image: "...",
  },
  {
    id: 3,
    name: "USB-C Hub",
    price: 999,
    category: "Accessories",
    image: "...",
  },
];
```

**Challenge:**

Explain:

```text
Where does the data originate?
        ↓
Which component receives it?
        ↓
Which component displays it?
```

---

# 3. Build a Dynamic User List

**Topics:** `map()`, props, keys, component identity

Given:

```js
const users = [
  { id: 1, name: "Ayan", age: 23 },
  { id: 2, name: "Rahul", age: 25 },
  { id: 3, name: "Sara", age: 21 },
];
```

Build:

```text
App
└── UserList
    └── UserCard × 3
```

Requirements:

```jsx
<UserList users={users} />
```

Inside `UserList`:

```jsx
users.map(...)
```

Each `UserCard` should receive one user.

Use:

```jsx
key={user.id}
```

**Challenge:**

Deliberately use:

```jsx
key = { index };
```

and explain why stable identity is generally preferable.

---

# 4. Build a Smart Status Component

**Topics:** Conditional rendering, ternary, `&&`, boolean props

Create:

```jsx
<UserStatus isLoggedIn={true} hasNotifications={true} />
```

The UI should behave differently depending on the values.

### Logged in

```text
Welcome back!

You have notifications.
[Logout]
```

### Logged out

```text
You are not logged in.
[Login]
```

Use:

- `if/else` for one version
- ternary for another
- `&&` where appropriate

Don't force `&&` everywhere.

**Challenge:**

Identify which conditional expression is most readable for each piece of UI and explain why.

---

# 5. Build a Reusable Layout with `children`

**Topics:** `children`, composition, abstraction

Create:

```jsx
<Card>
  <h2>React</h2>
  <p>Learn component composition.</p>
</Card>
```

Your component:

```jsx
function Card({ children }) {
  // ...
}
```

Now use the same `Card` component for:

```text
Profile
Product
Notification
```

For example:

```jsx
<Card>
  <h2>New Message</h2>
  <p>You received a new message.</p>
</Card>
```

**Important constraint:**

`Card` must know nothing about whether its content is:

- a profile
- product
- notification
- anything else

**Challenge:**

Explain why `children` is more flexible than creating:

```jsx
<ProfileCard />
<ProductCard />
<NotificationCard />
```

when the only difference is the content inside the container.

---

# 6. Build a Navigation System

**Topics:** Props + lists + keys + component composition

Given:

```js
const links = [
  { id: 1, text: "Home", url: "/" },
  { id: 2, text: "About", url: "/about" },
  { id: 3, text: "Contact", url: "/contact" },
];
```

Build:

```text
App
└── Navbar
    └── NavLink × 3
```

Usage:

```jsx
<Navbar links={links} />
```

`Navbar` should create `NavLink` components using `.map()`.

Each `NavLink` receives:

```jsx
text;
url;
```

The key should be attached to the element created by `map()`:

```jsx
links.map((link) => <NavLink key={link.id} text={link.text} url={link.url} />);
```

**Challenge:**

Explain why this:

```jsx
key={link.id}
```

belongs on `NavLink`, rather than inside `NavLink`.

---

# 7. Build a Todo List with Empty State

**Topics:** Lists, conditional rendering, avoiding accidental rendering

Given:

```js
const todos = [
  { id: 1, text: "Learn React" },
  { id: 2, text: "Practice JSX" },
  { id: 3, text: "Build a project" },
];
```

Build:

```text
TodoList
    ↓
Your Tasks

• Learn React
• Practice JSX
• Build a project
```

When:

```js
const todos = [];
```

show:

```text
No tasks available.
```

Use `.map()` for the list.

### Important

Don't write:

```jsx
{
  todos.length && <TodoItems />;
}
```

Instead, make sure an empty list doesn't render:

```text
0
```

**Challenge:**

Implement the empty state using:

1. `if`
2. ternary

Then decide which is clearer.

---

# 8. Find and Fix Impure Components

**Topics:** Purity, side effects, props immutability

Determine whether each component is pure.

### A

```jsx
function Greeting({ name }) {
  return <h1>Hello {name}</h1>;
}
```

### B

```jsx
let count = 0;

function Counter() {
  count++;

  return <p>{count}</p>;
}
```

### C

```jsx
function Price({ price }) {
  return <p>{price * 1.18}</p>;
}
```

### D

```jsx
const users = [];

function User({ name }) {
  users.push(name);

  return <p>{name}</p>;
}
```

For each:

- Is it pure?
- What value is being changed?
- Is that value inside or outside the component?
- How could you rewrite it?

### Additional challenge

Consider:

```jsx
function Product({ product }) {
  product.name = "Something else";

  return <h1>{product.name}</h1>;
}
```

Explain why modifying a prop directly is problematic.

---

# 9. Build a Dashboard Architecture

**Topics:** Component architecture, data ownership, props, nested composition

Build:

```text
App
├── Header
│   ├── Logo
│   └── UserMenu
├── Sidebar
│   └── NavItem × 4
└── Dashboard
    ├── WelcomeMessage
    ├── Stats
    │   └── StatCard × 3
    └── RecentActivity
```

Given:

```js
const user = {
  name: "Ayan",
};

const stats = [
  { id: 1, title: "Users", value: 1200 },
  { id: 2, title: "Orders", value: 350 },
  { id: 3, title: "Revenue", value: 45000 },
];

const navItems = [
  { id: 1, text: "Dashboard" },
  { id: 2, text: "Users" },
  { id: 3, text: "Orders" },
  { id: 4, text: "Settings" },
];
```

Requirements:

- Pass data through props.
- Use `.map()` for repeated UI.
- Use stable keys.
- Don't duplicate data inside child components.

### Architecture challenge

Before coding, answer:

```text
Where does user.name originate?

Where does stats originate?

Who renders StatCard?

Who owns the stats data?

Which component needs which props?
```

This is more important than the visual design.

---

# 10. 🔥 Mini Project — E-commerce Product Page

**Topics:** Components + props + lists + keys + conditional rendering + composition + purity

Build:

```text
App
├── Header
├── ProductPage
│   ├── ProductImage
│   ├── ProductInfo
│   │   ├── ProductTitle
│   │   ├── Price
│   │   ├── Description
│   │   └── StockStatus
│   └── ProductFeatures
└── Footer
```

Data:

```js
const product = {
  id: 101,
  name: "Mechanical Keyboard",
  price: 2499,
  description: "A compact mechanical keyboard.",
  image: "...",
  inStock: true,
  features: ["RGB lighting", "Hot-swappable switches", "Compact layout"],
};
```

Pass the product:

```jsx
<ProductPage product={product} />
```

### Product information

Display:

```text
Mechanical Keyboard
₹2499

A compact mechanical keyboard.
```

### Stock status

If:

```js
inStock === true;
```

show:

```text
In Stock
[Add to Cart]
```

Otherwise:

```text
Out of Stock
```

### Features

Render dynamically:

```text
Features

✓ RGB lighting
✓ Hot-swappable switches
✓ Compact layout
```

Use:

```jsx
key = { feature };
```

### Requirements

Your implementation should demonstrate:

- Component decomposition
- Props
- `children` where appropriate
- `.map()`
- Keys
- Conditional rendering
- Data flowing from parent → child
- Pure rendering
- No mutation of `product`

---

# Final Challenge — Break Your Own Code

After Exercise 10, deliberately introduce these bugs.

### 1. Remove the key

Change:

```jsx
features.map((feature) => <li key={feature}>{feature}</li>);
```

to:

```jsx
features.map((feature) => <li>{feature}</li>);
```

**Question:** Why does React warn about this?

---

### 2. Empty-array bug

Try:

```jsx
{
  features.length && <FeatureList />;
}
```

Then make:

```js
features = [];
```

**Question:** What gets rendered?

How would you fix it?

---

### 3. Mutate props

Try:

```jsx
function Product({ product }) {
  product.name = "Something else";

  return <h1>{product.name}</h1>;
}
```

**Question:** What principle are you violating?

---

### 4. Destroy reusability

Start with:

```jsx
function ProductCard() {
  return (
    <div>
      <h2>Keyboard</h2>
      <p>₹2499</p>
    </div>
  );
}
```

Convert it into:

```jsx
<ProductCard name="Keyboard" price={2499} />
```

Then render:

```jsx
<ProductCard name="Mouse" price={1499} />
<ProductCard name="Monitor" price={12999} />
```

---

### 5. Bad keys

Compare:

```jsx
products.map((product, index) => <ProductCard key={index} product={product} />);
```

with:

```jsx
products.map((product) => <ProductCard key={product.id} product={product} />);
```

Explain why the second gives React a more stable identity when list items are inserted, removed, or reordered.

---

# The progression

The new set has a cleaner learning progression:

```text
1. Components
      ↓
2. Props + Reusability
      ↓
3. Lists + Keys
      ↓
4. Conditional Rendering
      ↓
5. children + Composition
      ↓
6. Combining Props + Lists
      ↓
7. Lists + Conditions
      ↓
8. Purity + Immutability
      ↓
9. Component Architecture + Data Flow
      ↓
10. Complete Mini Project
```

I deliberately **removed the repetitive exercises** rather than simply reducing their number.

The most important conceptual progression is:

> **How do I split UI?**
> ↓
> **How do I pass data?**
> ↓
> **How do I render variable amounts of UI?**
> ↓
> **How do I render different UI based on data?**
> ↓
> **How do components compose?**
> ↓
> **How do I design the architecture?**
> ↓
> **Can I put all of it together without creating a mess?**

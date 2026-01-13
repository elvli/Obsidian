# What is React?

- A JavaScript framework for **front-end web development**
- Similar goal to jQuery, but **more structured**
- Built and maintained by **Facebook**
- Designed around the **Virtual DOM** (efficient UI updates)

---

# Timeline of Key Frameworks

- jQuery – 2006
- AngularJS – 2010
- **React – 2013**
- Vue – 2014
- Angular – 2014

---

# Common Front-End Tasks

- **App state** – organize/store data
- **User actions** – respond to clicks/typing
- **Templates** – render HTML visually
- **Routing** – handle pages & URLs
- **Data fetching** – use APIs/AJAX to get data from servers

---

# React Fundamentals

### 1. JavaScript + HTML Together (JSX)
- Write **markup and logic in one place**
- Replaces splitting HTML, CSS, and JS into separate files
### 2. Functional Programming Mindset
- Functions are **first-class citizens**
- Prefer **immutable variables**
- Avoid **side effects** in code
### 3. Components Everywhere
- UIs are built from **reusable components**
- Components behave like functions that return HTML

---

# JSX

- React syntax that mixes **JavaScript + HTML**
- Can embed expressions with `{ }`

`const name = <span>{first} {last}</span>;`

- Wrap multiple elements in `<>...</>`

---

# Functional Programming Concepts

### First-Class Functions
- Functions can be **stored, passed, and returned** like values
### Immutability
- Avoid modifying variables directly
    `let b = [1,2,3]; let c = [...b,4]; // preferred`

### No Side Effects
- Functions should not change things outside their scope

---

# Components
- Components are **functions that output UI**

`export default function MyComponent(props) {   return <div>Hello {props.name}</div>; }`

- Called like HTML tags  
    `<MyComponent name="Elven" />`
    
### Rendering
- A component **re-runs (re-renders)** whenever needed
- Must always compute the **correct output each render**
    

---

# Creating a React App

1. Install Node.js
2. Run:
    `npx create-react-app my-app`
3. Your project appears in `./my-app`

---

# Anatomy of a New App

- `App.js` – main component
- `index.js` – attaches React to the DOM
- `public/` – static HTML + assets
- `package.json` – library configuration

---

# Component Hierarchy

- Apps break into small reusable components
    
``` markdown
App
 ├─ Title
 ├─ TodoForm
 └─ TodoList
     ├─ Todo
     ├─ Todo
     └─ Todo

```

---

# List Keys

- Required when rendering dynamic lists
- Each item must have a **unique `key`**
- Helps React efficiently update the DOM

---

# What Are Hooks?

- Special functions that let components use:
    - **State**
    - **Lifecycle events**
- Common hooks:
    - useState
    - useEffect
    - useReducer
    - useMemo
    - useRef
    - useCallback

---

# Hook: useState

### Purpose
- Remember values between renders
- Trigger re-render when updated
### Syntax

`const [value, setValue] = useState(100);`

---

# When Components Re-Render

A component re-renders when:
1. **Props change**, or
2. A **useState setter** is called

---

# Hook: useEffect

### Purpose
- Run code **in response to changes**
- Listen to value updates
### Syntax

`useEffect(() => {   console.log(myValue); }, [myValue]);`

---

# Building for Production

- Run:
    
    `npm run build`
    
- Creates optimized HTML/CSS/JS in `build/`
    
- Can deploy anywhere (S3, Netlify, etc.)
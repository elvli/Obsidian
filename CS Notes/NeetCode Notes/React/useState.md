# Hook: **useState**

### What it Does

- Allows a component to **store values internally**
- Keeps those values **between re-renders**
- Tells React **to re-render the component** when the value changes

---

### Why We Need It

React **re-runs components constantly**.

`function Component() {   let num = 0;   // resets every time! }`

Without useState, values reset because functions are pure.  
useState gives components **memory across renders**.

---

### Syntax Breakdown

`const [value, setValue] = useState(100);`

#### `value`
- The **current state**
- React remembers it across renders
- Always read state using this variable (never mutate manually)

#### `setValue`
- A **setter function**
- Used to update state
- Calling this:

    `setValue(200);`
    
    tells React:
    > “State changed — re-render the component!”

#### `100`
- The **initial value**
- Only used on the **first render**
- After that, React replaces it with the remembered value

---

### Updating State

Unlike normal variables:

`value = 5; // ❌ does NOT work`

You must use the setter:

`setValue(5); // ✔ triggers a re-render`

Setter can take a **new value**:

`setValue("hello");`

Or a **function** of the old value:

`setValue(prev => prev + 1);`

Functional updates are recommended when working with the current value.

---

### Example

```
export default function Counter() {
  const [count, setCount] = useState(0);

  return (
    <button onClick={() => setCount(count + 1)}>
      Count: {count}
    </button>
  );
}
```

**What happens:**
1. User clicks → `setCount(count + 1)`
2. React stores new value (e.g., `1`)
3. Component re-renders
4. UI updates to “Count: 1”

---

### Rules of useState
- Must be used **inside a component or custom hook**
- Must be **at the top level** of the function
    - No `if`, `for`, or nested blocks
- Each useState call creates **independent state storage**

---

### Multiple States
You can call useState more than once:

`const [count, setCount] = useState(0); const [name, setName] = useState("Elven");`

React keeps track of state **by order**, not variable name.

---

### Common Mistakes

#### Mutating state directly

`count++; // ❌ no re-render`

You must use the setter function


#### Forgetting setter is async-ish
```
setCount(count + 1);
console.log(count);   // ❌ still prints old value`
```

React batches state updates, so your console log runs **before** state is updated.

**✔️ Correct**  
Use `useEffect` to observe changes:
```
setCount(count + 1);

useEffect(() => {
  console.log(count);   // ✔ logs AFTER update
}, [count]);
```

Or use the callback form if you just need the new value:
```
setCount(prev => {
  const next = prev + 1;
  console.log(next);   // ✔ correct value
  return next;
});
```

#### Depending on the old value
Always use functional updates:
`setCount(count + 1);  // ❌ can use stale value`

```
setCount(prev => prev + 1);
setCount(prev => prev + 1);   // ✔ increments twice
```

---

### When State Causes Re-Renders

A re-render happens when:

- The **same component** calls a **setter**
- OR receives **new props**

Updating state anywhere else does **not** affect other components.
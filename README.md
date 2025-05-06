# deque-visualizer-js
Here’s a **step-by-step detailed explanation** of your provided HTML, CSS, and JavaScript code for **Double Ended Queue (Deque) Visualization**:

---

## 🔹 **1. HTML Structure Overview**

The page is structured into three main parts:

### 🧾 a. **Header**

```html
<header> ... </header>
```

* Contains a title and a subheading describing the purpose.
* An "About Us" link on the right.

### 🖼️ b. **Main Content**

```html
<div class="main-content">
    <section class="visualization">...</section>
    <section class="controls">...</section>
</div>
```

* **Visualization Section**: Shows the deque and algorithm.
* **Controls Section**: Provides buttons to perform operations on the deque.

### 📜 c. **Footer**

```html
<footer> ... </footer>
```

* A simple footer with copyright.

---

## 🎨 **2. CSS Styling**

You use custom CSS with CSS variables and `@keyframes` for animation.

### a. **Colors & Variables**

```css
:root {
    --primary: #4361ee;
    --secondary: #3f37c9;
    ...
}
```

* These are reused for consistency and easy theme changes.

### b. **Page Layout & Styling**

* `.container`: Centers content and sets max width.
* `.main-content`: Uses Flexbox to align sections side by side.
* `.visualization`, `.controls`: Card-like containers with shadows.

### c. **Deque Styling**

```css
#deque-container { display: flex; justify-content: center; }
.deque { display: flex; gap: 5px; ... }
.deque-item { animated, color-coded, with hover tooltip }
```

* The items are visually distinct, showing front and rear with animation.

### d. **Responsive Design**

```css
@media (max-width: 768px) { ... }
```

* Ensures vertical layout on small screens.

---

## 🧠 **3. JavaScript Logic**

You use JavaScript to **manipulate the deque** and update the UI dynamically.

### a. **Variables**

```js
let deque = [];
let frontIndex = -1;
let rearIndex = -1;
```

### b. **Utility Functions**

#### ✅ `showStatus()`

Displays a temporary message:

```js
showStatus("Deque is empty", "danger")
```

#### ✅ `updateDequeInfo()`

Updates the info panel:

```js
frontIndex = 0;
rearIndex = deque.length - 1;
```

#### ✅ `updateAnimation()`

Rebuilds the deque visualization:

* Clears old elements
* Adds `div`s for each item
* Highlights front and rear

---

### c. **Operation Functions**

#### 1. **Enqueue Front**

```js
function enqueueFront() {
    let value = prompt(...);
    deque.unshift(value);
}
```

* Adds to beginning using `unshift()`

#### 2. **Enqueue Rear**

```js
function enqueueRear() {
    let value = prompt(...);
    deque.push(value);
}
```

* Adds to end using `push()`

#### 3. **Dequeue Front**

```js
function dequeueFront() {
    let value = deque.shift();
}
```

* Removes from front using `shift()`

#### 4. **Dequeue Rear**

```js
function dequeueRear() {
    let value = deque.pop();
}
```

* Removes from rear using `pop()`

#### 5. **Is Empty**

```js
function isEmpty() {
    return deque.length === 0;
}
```

* Checks if the deque is empty

---

## 🧮 **4. Algorithm Display**

Each operation updates an algorithm box:

```js
generateAlgorithmCode("enqueueFront", value);
```

Shows pseudocode like:

```js
if (isEmpty()) {
    front = rear = 0;
} else {
    front = (front - 1 + size) % size;
}
deque[front] = value;
```

This mimics how circular deque would behave in array implementation.

---

## 🖼️ **5. Background Image ()**

In your external or added CSS:

```css
body {
    
}
```

* Adds a **faded car image** as background with gradient overlay for readability.

---

## 🔚 Summary

| Feature         | Function                   |
| --------------- | -------------------------- |
| Deque           | Interactive with buttons   |
| UI              | Stylish, responsive layout |
| Animations      | Fade-in and pop-in         |
| Status Updates  | Shows real-time feedback   |
| Algorithm Panel | Shows operation logic      |
| Background      |   |

---

# Emergency-Service-Directory

### 1. What is the difference between getElementById, getElementsByClassName, and querySelector / querySelectorAll?

- **getElementById**: Returns a single element object with the specified `id`. It is the fastest and most direct way to select an element by its unique id. Example: `document.getElementById('myId')`.
- **getElementsByClassName**: Returns a live HTMLCollection of all elements with the given class name. You can access elements by index, but it is not an array. Example: `document.getElementsByClassName('myClass')`.
- **querySelector**: Returns the first element that matches a CSS selector. You can use any valid CSS selector (id, class, attribute, etc.). Example: `document.querySelector('.myClass')`.
- **querySelectorAll**: Returns a static NodeList of all elements matching a CSS selector. Example: `document.querySelectorAll('div.myClass')`.

### 2. How do you create and insert a new element into the DOM?

You can create a new element using `document.createElement`, set its properties or content, and then insert it into the DOM using methods like `appendChild`, `insertBefore`, or `append`.

Example:
```js
const newDiv = document.createElement('div');
newDiv.textContent = 'Hello, World!';
document.body.appendChild(newDiv);
```

### 3. What is Event Bubbling and how does it work?

Event bubbling is the process where an event starts from the deepest (most specific) element that triggered it and then propagates up through its ancestors in the DOM tree. For example, if you click a button inside a div, the click event first fires on the button, then on the parent div, then on higher ancestors, up to the document.

### 4. What is Event Delegation in JavaScript? Why is it useful?

Event delegation is a technique where you attach a single event listener to a parent element instead of multiple listeners to individual child elements. When an event bubbles up, you check the event target to handle events for specific children. This is useful for performance and for handling dynamically added elements.

Example:
```js
document.getElementById('parent').addEventListener('click', function(event) {
  if (event.target.matches('.child')) {
    // Handle click on .child elements
  }
});
```

### 5. What is the difference between preventDefault() and stopPropagation() methods?

- **preventDefault()**: Prevents the default action associated with the event (like following a link or submitting a form).
- **stopPropagation()**: Stops the event from bubbling up (or capturing down) the DOM tree, so parent elements do not receive the event.

Example:
```js
element.addEventListener('click', function(event) {
  event.preventDefault(); // Stops default action
  event.stopPropagation(); //
### CSS Transforms

#### What does a CSS transform allow the developer to do to an element?

CSS transforms enable developers to manipulate elements in two-dimensional or three-dimensional space. This includes operations such as rotating, scaling, skewing, or translating elements without affecting the document flow.

#### Example of a transform and its use on a website:

css


`.element {
  transform: rotate(45deg);
}` 

_Use Case_: A "rotated" or "tilted" card could be used on a portfolio website to make design elements visually engaging. For example, rotating icons slightly to emphasize interactivity.

----------

### CSS Transitions & Animations

#### What does a CSS transition allow the developer to do to an element?

CSS transitions enable developers to create smooth changes between two states of an element over a specified duration. This makes visual changes like color, size, or position appear more fluid.

Example:


`.button {
  transition: background-color 0.3s ease;
}

.button:hover {
  background-color: #3498db;
}` 

_Use Case_: On hover, buttons change color smoothly to give feedback to users interacting with the website.

#### How does a CSS animation differ from a CSS transition?

-   **CSS Transitions**: Require a state change (e.g., hover or active) to trigger the effect and run only once.
-   **CSS Animations**: Use `@keyframes` to define continuous or complex animations that can loop indefinitely or run automatically when the page loads.

Example:

`@keyframes bounce {
  0%, 100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-20px);
  }
}

.element {
  animation: bounce 1s infinite;
}`

----------

### Benefits of CSS Transitions on Websites

1.  **Enhanced User Experience**: Smooth animations provide feedback, making interactions intuitive and engaging.
2.  **Improved Aesthetics**: Transitions give a polished, professional feel to a website.
3.  **Lightweight Performance**: CSS transitions are efficient and less resource-intensive than JavaScript-based animations.
## Event bubbling 
Event bubbling is a concept in JavaScript where an event triggered on a nested element will also trigger the same event on its parent elements, propagating up the DOM tree until it reaches the root element. This bubbling effect allows you to handle events at different levels of the DOM hierarchy.

Here's an example to demonstrate event bubbling in JavaScript:

```html
<!DOCTYPE html>
<html>
<head>
  <title>Event Bubbling Example</title>
</head>
<body>
  <div id="outer">
    <div id="inner">
      <button id="button">Click Me</button>
    </div>
  </div>

  <script>
    var outerDiv = document.getElementById("outer");
    var innerDiv = document.getElementById("inner");
    var button = document.getElementById("button");

    outerDiv.addEventListener("click", function(event) {
      console.log("Outer Div Clicked");
    });

    innerDiv.addEventListener("click", function(event) {
      console.log("Inner Div Clicked");
    });

    button.addEventListener("click", function(event) {
      console.log("Button Clicked");
    });
  </script>
</body>
</html>
```

In this example, we have three nested elements: an outer div, an inner div, and a button. Each of them has a click event listener attached to it.

When you click the button, the event will bubble up from the button to the inner div, and then to the outer div. As a result, the console output will be:

```
Button Clicked
Inner Div Clicked
Outer Div Clicked
```

This demonstrates the bubbling effect, where the event propagates from the innermost element to its parent elements. It allows you to handle events at different levels of the DOM hierarchy, making event delegation and handling more convenient.

## Event capturing 
Event capturing is the opposite of event bubbling. It is another phase of the event propagation process in JavaScript, where an event triggered on a parent element will be captured and handled by its child elements first before reaching the target element.

To understand event capturing, you need to be familiar with the three phases of event propagation:

1. Capturing Phase: The event is captured by the parent elements starting from the top-level element down to the target element.
2. Target Phase: The event reaches the target element.
3. Bubbling Phase: The event bubbles up from the target element back to the top-level element.

To enable event capturing, you can use the `addEventListener` method with the `capture` option set to `true`. Here's an example:

```html
<!DOCTYPE html>
<html>
<head>
  <title>Event Capturing Example</title>
</head>
<body>
  <div id="outer">
    <div id="inner">
      <button id="button">Click Me</button>
    </div>
  </div>

  <script>
    var outerDiv = document.getElementById("outer");
    var innerDiv = document.getElementById("inner");
    var button = document.getElementById("button");

    outerDiv.addEventListener("click", function(event) {
      console.log("Outer Div Clicked (Capturing Phase)");
    }, true);

    innerDiv.addEventListener("click", function(event) {
      console.log("Inner Div Clicked (Capturing Phase)");
    }, true);

    button.addEventListener("click", function(event) {
      console.log("Button Clicked (Capturing Phase)");
    }, true);
  </script>
</body>
</html>
```

In this example, the event listeners are set with the `capture` parameter set to `true` for event capturing.

When you click the button, the event will be captured in the capturing phase. The console output will be:

```
Outer Div Clicked (Capturing Phase)
Inner Div Clicked (Capturing Phase)
Button Clicked (Capturing Phase)
```

The event is captured by the parent elements in the reverse order of the DOM hierarchy, starting from the top-level element (outer div) down to the target element (button).

It's important to note that event capturing is not supported in some older versions of Internet Explorer, but it is widely supported in modern browsers. In most cases, event bubbling is more commonly used than event capturing.

## UseCapture
The `capture` parameter in the `addEventListener` method is used to specify whether the event should be handled in the capturing phase (`true`) or the bubbling phase (`false`, which is the default behavior if `capture` is not specified).

To use `capture` for event bubbling or event capturing, you need to set the parameter accordingly. Here's an example:

```javascript
var element = document.getElementById("myElement");

// Event Bubbling (Default behavior)
element.addEventListener("click", function(event) {
  console.log("Event Bubbling");
});

// Event Capturing
element.addEventListener("click", function(event) {
  console.log("Event Capturing");
}, true);
```

In this example, we have an element with the ID "myElement". The first `addEventListener` attaches an event listener without specifying `capture`, which means it will use the default behavior of event bubbling. When a click event occurs on the element, the console will log "Event Bubbling".

The second `addEventListener` explicitly sets `capture` to `true`, indicating that the event should be handled during the capturing phase. When a click event occurs on the element, the console will log "Event Capturing" before the bubbling phase.

By using `capture`, you can control whether an event is handled during the capturing phase (`true`), the bubbling phase (`false` or omitted), or both.


## addEventListner Basics 
- try to log the `e` and check target to see more properties in console
- use e.stopPropopagation() to stop event bubbling or capturing upto certain point

#### Run event only once 
To run an event only once in JavaScript, you can use the `addEventListener` method with the `once` option set to `true`. This ensures that the event listener is triggered only for the first occurrence of the event, and subsequent occurrences are ignored.

Here's an example:

```javascript
var element = document.getElementById("myElement");

element.addEventListener("click", function(event) {
  console.log("Event executed once");
}, { once: true });
```

In this example, the event listener is attached to the element with the ID "myElement" for the "click" event. The third parameter `{ once: true }` is an options object that specifies the `once` option as `true`.

When the element is clicked, the event listener will be executed, and the message "Event executed once" will be logged to the console. If the element is clicked again, the event listener will not be triggered.

Using the `once` option provides a convenient way to ensure that an event is handled only once, without the need to manually remove the event listener after it has been executed.

#### removeEventListner
In JavaScript, you can use the `removeEventListener` method to remove an event listener that was previously attached to an element. This allows you to stop listening for a specific event on that element.

The `removeEventListener` method requires the same event type, callback function, and capture option (if applicable) that were used when adding the event listener. Here's the syntax:

```javascript
element.removeEventListener(eventType, listener, useCapture);
```

- `eventType`: A string that specifies the type of the event (e.g., "click", "keydown", "mouseover").
- `listener`: The callback function that was originally added as the event listener.
- `useCapture` (optional): A boolean value that indicates whether the event listener was registered in the capturing phase (`true`) or the bubbling phase (`false` or omitted).

Here's an example that demonstrates how to add and remove an event listener:

```javascript
var button = document.getElementById("myButton");

function handleClick(event) {
  console.log("Button clicked!");
}

// Adding the event listener
button.addEventListener("click", handleClick);

// Removing the event listener
button.removeEventListener("click", handleClick);
```

In this example, the `handleClick` function is added as the event listener for the "click" event on the button element with the ID "myButton". After adding the event listener, whenever the button is clicked, the message "Button clicked!" is logged to the console.

Later, the `removeEventListener` method is used to remove the event listener from the button. This ensures that the `handleClick` function will no longer be invoked when the button is clicked.

It's important to note that for `removeEventListener` to work, the event listener function passed to `addEventListener` must be the same function reference. If you're using an anonymous function as the event listener, you won't be able to remove it later since there is no reference to it.
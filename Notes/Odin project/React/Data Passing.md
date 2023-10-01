## Intro 
data is transferred from parent components to child components via props. This data transfer is unidirectional, meaning it flows in only one direction. Any changes made to this data will only affect child components using the data, and not parent or sibling components. This restriction on the flow of data gives us more explicit control over it, resulting in fewer errors in our application.
Props are the information that you pass to a JSX tag

React component functions accept a single argument, a `props` object:

```jsx
function Button(props) {

  const buttonStyle = {
    color: props.color,
    fontSize: props.fontSize + 'px'
  };

  return (
    <button style={buttonStyle}>{props.text}</button>
  )
}

export default function App() {
  return (
    <div>
      <Button text="Click Me!" color="blue" fontSize={12} />
      <Button text="Don't Click Me!" color="red" fontSize={12} />
      <Button text="Click Me!" color="blue" fontSize={20} />
    </div>
  );
}
```

## Props destructing

```jsx
function Button({ text, color, fontSize }) {
  const buttonStyle = {
    color: color,
    fontSize: fontSize + "px"
  };

  return <button style={buttonStyle}>{text}</button>;
}

export default function App() {
  return (
    <div>
      <Button text="Click Me!" color="blue" fontSize={12} />
      <Button text="Don't Click Me!" color="red" fontSize={12} />
      <Button text="Click Me!" color="blue" fontSize={20} />
    </div>
  );
}
```

## Default props 
You may have noticed in the above examples that there is some repetition when defining props on the `Button` components within `App`. In order to stop repeating ourselves re-defining these common values, and to protect our application from undefined values, we can define default props that will be used by the component in the absence of supplied values.

```jsx
function Button({ text, color, fontSize }) {
  const buttonStyle = {
    color: color,
    fontSize: fontSize + "px"
  };

  return <button style={buttonStyle}>{text}</button>;
}

Button.defaultProps = {
  text: "Click Me!",
  color: "blue",
  fontSize: 12
};

export default function App() {
  return (
    <div>
      <Button />
      <Button text="Don't Click Me!" color="red" />
      <Button fontSize={20} />
    </div>
  );
}
```

You can also combine default props and prop destructuring. Here’s how it looks in action

```jsx
function Button({ text = "Click Me!", color = "blue", fontSize = 12 }) {
  const buttonStyle = {
    color: color,
    fontSize: fontSize + "px"
  };

  return <button style={buttonStyle}>{text}</button>;
}
```

## Function through props 

```jsx
function Button({ text = "Click Me!", color = "blue", fontSize = 12, handleClick }) {
  const buttonStyle = {
    color: color,
    fontSize: fontSize + "px"
  };

  return (
    <button onClick={handleClick} style={buttonStyle}>
      {text}
    </button>
  );
}

export default function App() {
  const handleButtonClick = () => {
    window.location.href = "http://www.google.com";
  };

  return (
    <div>
      <Button handleClick={handleButtonClick} />
    </div>
  );
}
```

- We only pass through a reference to `handleButtonClick`, i.e. we do not include parenthesis when passing the function to `Button`. If we were to do something like `handleClick={handleButtonClick()}` then the function would be called as the button renders.
    
- You can rename the function to whatever you like when passing through as props, the prop name and value do not need to be the same. We could just as easily write `superCoolFunction={handleButtonClick}`.
    
- Every `Button` calling this function will navigate to the same page. We can refactor the function and supply a parameter within `Button` to customize this functionality. 



#### Going in detail for last point 
###### What is refactoring a function mean
Refactoring a function means making changes to the code of a function to improve its structure, readability, efficiency, or maintainability without altering its external behavior. The goal of refactoring is to enhance the code's quality while keeping the same functionality. Refactoring is a common practice in software development to make code easier to understand, modify, and maintain.

##### After refactoring 
```jsx
function Button({ text = "Click Me!", color = "blue", fontSize = 12, handleClick }) {
  const buttonStyle = {
    color: color,
    fontSize: fontSize + "px"
  };

  return (
    <button onClick={() => handleClick('https://www.theodinproject.com')} style={buttonStyle}>
      {text}
    </button>
  );
}

export default function App() {
  const handleButtonClick = (url) => {
    window.location.href = url;
  };

  return (
    <div>
      <Button handleClick={handleButtonClick} />
    </div>
  );
}
```
When supplying a parameter to the function we can’t just write `onClick={handleClick('www.theodinproject.com')}`, and instead must attach a reference to an anonymous function which then calls the function with the parameter. Like the previous example, this is to prevent the function being called during the render.

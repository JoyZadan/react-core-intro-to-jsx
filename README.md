# Introduction to JSX

![GitHub last commit](https://img.shields.io/github/last-commit/JoyZadan/react-core-intro-to-jsx?color=yellow&style=for-the-badge)
![GitHub contributors](https://img.shields.io/github/contributors/JoyZadan/react-core-intro-to-jsx?color=purple&style=for-the-badge)
![GitHub language count](https://img.shields.io/github/languages/count/JoyZadan/react-core-intro-to-jsx?color=blue&style=for-the-badge)
![GitHub top language](https://img.shields.io/github/languages/top/JoyZadan/react-core-intro-to-jsx?color=yellow&style=for-the-badge)

---
# **REACT ESSENTIALS > Introduction to JSX**

## JSX
Reference: [JSX In Depth](https://reactjs.org/docs/jsx-in-depth.html)

JSX is an extension to the JavaScript language which allows you to simplify your React code and support for JSX is built into React so you can use it without any special conditions.

You can think of JSX elements like custom HTML tags which can have any name you wish. Just like regular XML or HTML elements. JSX  Elements can have *attributes* like classes, ID's and names, and can have *relationships* like parents, children and siblings.

While JSX is not necessary to write React applications, in reality React developers use it almost universally because it's simpler, more elegant and easier to read and maintain. Ultimately, when your app is run, the JSX code gets transpiled, or converted, to the vanilla JavaScript you're familiar with, and which your browser can understand.

If you want to see what a React component looks like without using JSX, just take a look at this app component - **App.js** - to render a simple HTML structure like a div with a couple of children.

`cd jsx-example/`
`npm start`

**Example of an App component without JSX**
```javascript
import React from 'react';
import './App.css';

function App() {
    return React.createElement(
        "div",
        { classname: "App" },
        React.createElement("header",
            { className: "App-header" },
            React.createElement("h1",
                null,
                "Hello from JSX!"
            )
        )
    );
}

export default App;
```
In the example above, instead of returning JSX code, to render a simple HTML with a div and a couple of children,
* First the App component returns a call to **React.createElement**.
* The React.createElement function takes three parameters:
    * the element to create, in this case a div
    * an object of properties to apply to that element, such as class names and IDs
    * and an arbitrary number of children elements.
        * In this case, the div has one child a **header** element,
            * which has a child itself, an **h1**,
                * and that **h1** itself has a child text node containing the text.

The div and the header have one class each, specified by the className property, and the **h1** element has no attributes so that parameter is set to null.

In the end, the example above renders the same result as the example below which uses JSX: </br>
**Example of an App component using JSX**

```javascript
import React from 'react';
import './App.css';

function App() {
    return (
        <div className="App">
            <header className="App-header">
                <h1>Hello from JSX!</h1>
        </div>
    );
}

export default App;
```

You can probably now imagine imagine what your code might look like if you had a div with 50 nested elements, and each of them had children of their own with classes, IDs and all the other stuff that a typical HTML page has! Without JSX, something as simple as creating the grid for your page layout or creating a form becomes incredibly complex, since every single element requires this call to **react.createElement()**.

JSX is simply syntactic sugar, which means that it simplifies the syntax for calling **react.createElement**. By using JSX, you can write your code so it looks mostly the same as standard HTML, but with the added benefit of being able to inject and use JavaScript wherever you need to do something HTML can't handle.

You might notice that in the examples above, both with JSX and without it, we're using the property **className** *to define a class for the app div*. This is because **class is a reserved word in JavaScript**, and we're writing the code in a JavaScript file, so we can't use it. Instead, when writing JSX code we must use the property className. If you inspect the page and look at
the resulting HTML, you'll see that **className gets transpiled down to class** in the end.

## JSX/ HTML Differences
| HTML | JSX | Explanation |
| :-- | :-- | :-- |
| class | className | *class* is always replaced with *className* |
| for | htmlFor | like *class*, *for* is a reserved word used for looping in JS, so if we want to specify a *for* attribute in a form, we must use *htmlFor* |
| onclick | onClick | All HTML attributes and event references in JSX become camelCase, this way, *onclick* event becomes *onClick* and *onchange* becomes *onChange*.   |
| tabindex | tabIndex | camelCased - JS naming conventions. All HTML attributes and event references in JSX become camelCase, this way, *tabIndex* becomes *tabIndex* |
| value | defaultValue | new attribute when working with forms |

Lastly, it's important to remember that **all custom JSX elements as well as the React components they represent, must be capitalized** (like the use of **App** in the example above). This is so the transpiler that converts the JSX to vanilla JavaScript can tell the difference between your custom JSX elements and standard HTML elements.

❗So remember that **all components should be capitalized** both *when defining them* and *when referring to them* in JSX code.

Additional readings:
* [What are the differences between JSX and HTML?](https://www.geeksforgeeks.org/what-are-the-differences-between-jsx-and-html/)
* [HTML vs JSX](https://www.freecodecamp.org/news/html-vs-jsx-whats-the-difference/)
* Reminder: [JS naming conventions](https://www.syncfusion.com/blogs/post/10-javascript-naming-conventions-every-developer-should-know.aspx)

*Since JSX isn’t a legitimate JS code, it must be compiled into JS with a tool like Babel or similar.*

## **Summary**
Remember that:
* React developers almost universally use JSX when writing React components because it greatly simplifies the code.
* In JSX, you need to replace certain attributes such as class with className and for with htmlFor.
* Custom JSX elements represent react components and must be capitalized both in their file names and in their use in the code, so the transpiler can differentiate them from regular HTML.

Next: See **Creating your first React application**

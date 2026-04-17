# Interview
**1. What is React and Why is it Popular?**
React's popularity stems from its component-based architecture that allows for reusable UI components.
The virtual DOM minimizes direct DOM manipulations, significantly enhancing performance.
**2.what is a single page application or Spa?**
Spa a single page application is a type of web application that loads a single HTML page and then instead of reloading the whole page only updates the affected parts of
the page according to the users's actions like only rendering the color change here from light blue to Pink this means it only contacts the server for the components in which you have added new features or have made certain changes. Now this process results in Faster load times better responsiveness and smoother user interactions however using Spas can become a challenge when it comes to search engine optimization because the application uses a single URL so it becomes harder for the search engines to crawl and index content effectively.
**3.what is jsx and how does it differ from HTML ?**
Jsx or JavaScript XML is a syntax extension for JavaScript that allows developers to write HTML like code directly into JavaScript files.

---------------
import React from 'react'
  const  App = () => {
   return (
    <div>
     <h1>Hello, World!</h1>
     <p>This is a simple React component.</p>
    </div>
  )
}
export default App
--------------------
**4.explain the difference between functional and class components ?**
 ## Functional Components vs Class Components (React)

| Feature |      Functional Components | Class Components |
|--------|---------------------------- |------------------|
| Usage Trend |--> Modern and widely used after Hooks introduction ---||-- Older approach, used before Hooks |
| Complexity |--> Simple and easier to use ---||-- More complex and verbose |
| Concept |--> Lightweight functions ---||-- Like large, traditional machines |
| State Mgmt |--> Managed using Hooks (e.g., useState) ---||-- Managed using this.state |
| Lifecycle Handling |--> useEffect Hook ---||-- Lifecycle methods (componentDidMount, etc.) |
| Syntax |--> Plain JavaScript functions ---||-- ES6 Classes extending React.Component |
| JSX Rendering |--> Directly return JSX ---||-- Requires render() method to return JSX |
| State Updates |--> useState setter function ---||-- this.setState() |
| Initial Nature |--> Originally stateless ---||-- Always supported state |
| Current Preference |--> Preferred in modern React ---||-- Less commonly used today |
**5.what is the difference between a stateless and a stateful component in react?**
## Stateless vs Stateful Components

| Feature | Stateless Components | Stateful Components |
|--------|----------------------|---------------------|
| Definition | Do not manage or store data  ---||-- Manage and store their own data |
| Data Handling | Receive data via props  ---||-- Maintain data using state |
| Complexity | Simple and easy to use  ---||-- More complex due to logic handling |
| Logic | No internal logic  ---||-- Can handle business logic |
| Use Case | Best for displaying UI content only  ---||-- Used when data changes over time |
| State | No state  ---||-- Has state |
| Example Type | Functional components (without hooks)  ---||-- Functional components (with hooks) or Class components |
**6.what are props in react and how are they used?**
props or properties are a way to pass data from a parent component to a child component in react
the child components cannot modify these values because they are read only so instead these values are used to trigger certain actions in the child components you must have understood at this point
that both props and state are used to control and manipulate how components behave and render 
**7.what is the difference between State and props in react?**

## State vs Props (React)
| Feature | State | Props |
|--------|------|-------|
| Definition | Mutable object that stores dynamic data  ---||--  Immutable object used to pass data |
| Data Nature | Dynamic (changes over time)  ---||--  Static (read-only inside component) |
| Mutability | Can be modified  ---||--  Cannot be modified |
| Control | Managed within the component  ---||--  Controlled by parent component |
| Accessibility | Private to the component  ---||--  Passed from parent to child |
| Use Case | Used for handling user interaction, API data, etc. ---||--  Used for passing data between components |
| Example | Counter value that increments/decrements  ---||--  Data passed like title, name, etc. 

**8.what are control and uncontrolled components control components are used ?**
## Controlled vs Uncontrolled Components (React)

| Feature | Controlled Components | Uncontrolled Components |
|--------|----------------------|--------------------------|
| Definition | Form data is controlled by React state | Form data is handled by the DOM itself |
| Data Control | Full control over input values | Limited control over input values |
| Use Case | Form validation, authentication (username/password) | Simple inputs like newsletter signup, file upload |
| Data Access | Accessed via state | Accessed via refs |
| React Involvement | React actively manages input changes | React does not directly track input changes |
| Complexity | Easier to manage and update | Harder to manage due to refs |
| Example | Uses `value` and `onChange` | Uses `ref` 

**
<input 
  type="password" 
  placeholder="Enter your password" 
  value={password} 
  onChange={(e) => setPassword(e.target.value)} 
/>
** Example: Controlled Component**
 
<input 
  type="email" 
  placeholder="Enter your email" 
  ref={emailRef} 
/>

**9.what is the purpose of the key attribute in react lists?**
const items = [{id: 1, name: 'Apple'}, {id: 2, name: 'Banana'},, {id: 3, name: 'Oranges'}]
if in this list containing apples bananas and orange I were to update only one of the fruit names say orange should the whole list be rendered no because it will be a waste of time since the other two elements never
changed in our case react understood which element to rerender based on the key associated with that element **key attributes** as a name suggests is primarily used to identify each item
uniquely when the list rerenders enabling react to track and update individual items in the list without having to reender the entire list .

**10. what are fragments in react and why are they used?**
fragments and react are a way to group together multiple elements without adding an extra node to the Dom like this H1 and P tags that are group
together with react fragments without adding an extra containers around them in short fragments are used when you want to avoid unnecessary wrapper elements like this div tag

**11.what is the virtual dom and how does react use it to improve performance ?**
## What is Virtual DOM and How React Uses It?

### Virtual DOM
The Virtual DOM is a lightweight JavaScript representation of the actual DOM (Document Object Model).  
Instead of directly manipulating the real DOM, React creates a virtual copy of it in memory.

---

### How React Uses Virtual DOM to Improve Performance

1. **Initial Rendering**
   - React creates a Virtual DOM tree based on JSX.

2. **State/Props Change**
   - When data changes, React creates a new Virtual DOM.

3. **Diffing Algorithm**
   - React compares (diffs) the new Virtual DOM with the previous one.

4. **Efficient Updates**
   - Only the changed elements are updated in the real DOM (not the entire UI).

---

### Why It Improves Performance

- Minimizes direct DOM manipulation (which is slow)
- Updates only necessary parts of the UI
- Uses efficient diffing algorithm
- Improves rendering speed and user experience

---

### Simple Example

If a counter updates:
- React does NOT re-render the whole page
- It only updates the number that changed

---

### Summary

| Feature | Virtual DOM |
|--------|------------|
| Nature | In-memory representation of real DOM |
| Speed | Faster than direct DOM manipulation |
| Update Strategy | Selective updates using diffing |
| Benefit | Better performance and smoother UI |

**12.what are react life cycle methods and when are they used?**
react life cycle methods are special functions that provide granular level
control to developers to hook into specific points in a component's life cycle the reason why we need life cycle method methods is so that you can attach certain events to a component's life
cycle that is when the component is first initialized it needs to do this and when it is like in um when it is about to end you need to do this wrap up all of this close these timers and do
this and do that when the component is about to be closed off so to attach certain events to a component's life cycle is why you need the life cycle methods .
These stages include:
1. Mounting (component is created and inserted into DOM)
2. Updating (component re-renders due to changes)
3. Unmounting (component is removed from DOM)

---

## 1. Mounting Phase
(When the component is created)

| Method | Purpose |
|--------|--------|
| constructor() | Initialize state and bind methods |
| render() | Returns JSX to display UI |
| componentDidMount() | Runs after component is added to DOM (API calls, subscriptions) |

---

## 2. Updating Phase
(When state or props change)

| Method | Purpose |
|--------|--------|
| render() | Re-renders UI |
| componentDidUpdate() | Runs after update (API calls, DOM updates) |

---

## 3. Unmounting Phase
(When component is removed)

| Method | Purpose |
|--------|--------|
| componentWillUnmount() | Cleanup (timers, subscriptions, event listeners) |

---

## When Are They Used?

- **API Calls** → componentDidMount()
- **Updating UI after data change** → componentDidUpdate()
- **Cleanup tasks** → componentWillUnmount()
- **Initial setup** → constructor()

---

## In Modern React (Hooks)

Lifecycle methods are mostly replaced by Hooks in functional components:

| Class Lifecycle | Hook Equivalent |
|----------------|-----------------|
| componentDidMount | useEffect(() => {}, []) |
| componentDidUpdate | useEffect(() => {}, [dependencies]) |
| componentWillUnmount | useEffect(() => { return () => {} }) |

---

## Summary

- Mostly used in **class components**
- Lifecycle methods control how a component behaves over time
- In modern React, **Hooks (useEffect)** are preferred

**13.explain the use State and use effect hooks with examples ?**
use state is basically used to store the fesh data and their loading States use State you can think of use
State as a container in which you store a particular value so say if you have a count variable so every single time I'm increasing the value of count it's stored inside this useState variable and
every single time I'm increasing it the value the previous value is fetched from this useStates's container useEffect on the other hand is used to perform side effects like when you're making an API call so what happens in the background
that is all controlled by use effects it is used to fet the data when the component mounts so such a if you are uh if you're setting up a clock or maybe there's a popup which is supposed to happen after a certain period of time all of
these actions are important like a timer going on in the background um maybe a clock that is going on on your web page in the corner it is important but it should not mess around with the main part of your web page some function needs to
make sure that this clock is continuously ticking in the background .

**14.what do you understand by props drilling?**
props drilling it's like if you have multiple children in the same parent there's a parent there's a child there's a grandchild there's a grand grandchild now there's a possibility that one of the props that you're getting in the
parent element now although the child element and the grandchild element do not want to use it but the grand grand or the great grandchild wants to use that particular prop so it needs to pass
through all of these components as well it needs to pass through the parent it needs to pass through the child grandchild and then it will reach the great grandchild so even though the child and the grandchild really don't
need to use a component they will still need to pass it through them so that the great grandchild gets it and that's where that's that becomes a problem if there are like too many nested elements
what if it had even like a great great grandchild and just keep on going and then that would just become hectic at one point and you just lose track of where the prompt was actually supposed
to go and where it actually went or in technical terms props drilling is when data has to be passed through many layers of components.

**15.what is the context API and how is it used for State Management ?**
context API is a way to solve the problem of this props drilling how what context API does is instead of the props having to go through all of these
intermediary components context API can create a global variable or it can provide a global space where these variables will automatically get stored in so that whenever other variables or
any other CH any other child components wants to get this variable they don't have to go and ask their parent where is the variable and then the parent ask their parent it doesn't have to be that way it can just directly go to This
Global space and retrieve the component or retrieve the variable whatever it is looking for or in technical terms the context API and react is a feature that allows you to manage and share state or
data globally across a component tree without needing to pass prompts manually at every single level .

**16.what are higher order components Give an example?**
A higher order component is a function that takes a component as an input and returns a new component with additional functionality or modified Behavior .

->wrapped component react

**17.explain the concept of reconciliation in react ?**
reconciliation is like a process in react when it's like what happens in the background when a particular component is updated and how
the virtual domor and the original dor is working together to display the content in the user interface let's look at them one by one.
there are obviously different phases for this
   initial render->when a component is first rendered when it's first rendered in react actually creates a virtual Dom to check what has changed in your code and whatever changes have been made only those
certain Elements which you have changed in your code will be reflected in your original Dom only those components will be rendered the other components will not be rendered as no change was made to those components next you have state or
   state or props change -> when a state or a props change react creates a new virtual Dom every single time a new virtual dor is created because it's a lightweight copy of the original domor so it doesn't take
a lot of effort or a lot of it doesn't create a lot of performance optimization issues so every single time you render the component a new virtual domor is created which checks whatever changes have been made and updates accordingly
  diffing -> diffing is basically the comparing part is called as diffing or maybe the difference between the both of them the original Dom and the virtual Dom that is called as diffing
  updating the Dom  -->whatever changes are there in the virtual Dom because of the changes in the code that you made only those things will be changed in the original Dom as well that is called as updating the Dom
committing phase-> what is whatever changes were made rolling them out and committing them to the original domor is called as committing phase finally react commits that changes to the actual
**18.how do react portals work and when should they be used?**
react portal is a way to render a components of children into different parts of the Dom outside the parent components hierarchy.
**19.how does react router handle navigation in a single page ?**
**20.what is react strict mode and how does it help developers ?**
React strict mode helps developers identify potential problems in an application by intentionally invoking certain warnings and behaviors in the application so the react strict mode essentially acts as a safety net just to make sure that all the safe
coding practices so that you practice all the safe coding practices and that whatever warnings that you're getting in your code early on does not lead to an error later on in the code









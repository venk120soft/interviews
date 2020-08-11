# Questions asked in Interviews

## Persistent system interview

Explain your daily routine while working with Microsoft?
App Studio
Currently working on chat based document sharing application which is available in both desktop and web. In daily basis used to create components that will talk throw web api to Azure Cosmos DB on firing the respective events. handling the state in single redux store with one way binding for all the  actions performed on the react components.

1) What is javascript? is Javascript synchronous? how does the asynchronous operations performed under the hood in javascript?
  Javascript is case sensitive, synchronous, single threaded and object oriented programming language

2) What are the latest ECMA script features (not ECMA 6)

3) Can you explain the react life cycle methods and hooks?

4) Before api hit have you performed any Authentication in UI?

5) Why do the react components is always capital( ex: MyComponent)? and events are in camelCase? (ex: onClick)
For all small letter components React thinks like html tags, even though you write small 
the JSX tag name convention (lowercase names refer to built-in components, capitalized names refer to custom components).

```javascript
// For example, this code will not run as expected:

import React from 'react';

// Wrong! This is a component and should have been capitalized:
function hello(props) {
  // Correct! This use of <div> is legitimate because div is a valid HTML tag:
  return <div>Hello {props.toWhat}</div>;
}

function HelloWorld() {
  // Wrong! React thinks <hello /> is an HTML tag because it's not capitalized:
  return <hello toWhat="World" />;
}
```
6) Why do the react events are capitalized?

7) is React Case sensitve?
Yes React is case sensitive

8) What are the features and disadvantages of react?

9) What are the authentication process you followed?
Forms, oAuth token authentication
What is oAuth 2.0 authentication
single authentication for multiple websites

10) Whats the differnce between call, apply, bind in javascript?
call-passing the elements like 1,2,3,4
apply passing the elements like an array [1,2,3,4]
bind
also what is the other difference on them?

11) What is the latest version of ECMA and their features?

12) What is the difference between map and foreach?
Both will iterate on the collection where as map will return the new list
ex: myArray.forEach(x=>xonsole.log(x));
const newArray =myArray.map(x=>
return x+1;
)
13) Have you aware of ADA issues or 5 most common complaints?

14) Have you ever work with any third party middle ware with react?? and why?
I have worked with Redux thunk to make the UI and api responses is in synch
Redux thunk is the middileware between the react and redux, when ever we make a api call one action is performed by that time instead of dispacthing the action at same time
we are wrapping the action in seperate arrow function This will help to synch the UI with api response.
dispatch({type:"INCREMENT", payload:2}); Converting in to seperatiing action methods

const incrementCount=(val)=>{
  return (dispatch)=>{
  dispatch()
  }
}

15) How to read the url parameters in react router
https://medium.com/better-programming/how-to-pass-multiple-route-parameters-in-a-react-url-path-4b919de0abbe
```javascript
<Route exact path="/genres" component={Genres} />
<Route exact path="/movie/:id" component={MovieDetailsContainer} />
// this is an example of a dynamically updating route. The first part of the path, the "/movie/” part, doesn’t change, but the :id is a route parameter that is set dynamically
<Route path="/genres/:genreName/:genreId" component={GenreList} />
```
16) how do you access route parameters from a URL?
this.props.match.params has all the paramters can be accessed like ex: his.props.match.params.genreId

17) can you write the Sample React Class Component?
18) Can you print the Fibanaci series until the given number?

19) What are HOC? can you give one example?

20) Can we pass props from child to parent? How?
https://www.pluralsight.com/guides/how-to-pass-props-object-from-child-component-to-parent-component
there is no way to pass props from a child component to a parent component. However, we can always pass around functions from the parent to child component. 
The child component can then make use of these functions. The function can then update the state in a parent component, as we saw above. 
Once our state gets changed, it is passed down as props again. Thus, all the relevant components get rendered again. A similar pattern can be used when we have multiple page components in our React app. If we want to pass data from one page to the other, we can lift up the state to the parent component (in most cases, the App component). The parent would have all the individual page components as its child. Thus, the data will be managed as state in the topmost level component and at the same time, we can pass it to any of the child components.

```javascript
import React, { Component } from 'react';
class App extends Component {
  constructor(props) {
    super(props);
    this.state = {
      isDisplayed: true,
    };
  }
  toggleShowHide = () => {
    this.setState(state => ({ isDisplayed: !state.isDisplayed }));
  };
  render() {
    const hello = 'Say Hello to learning Props/State in React!';
    return (
      <div>
        <HelloReact hello={hello} isDisplayed={this.state.isDisplayed} />
        <Button onClick={this.toggleShowHide} />
      </div>
    );
  }
}
const Button = ({ onClick }) => (
  <button onClick={onClick} type="button">
    Toggle Show/Hide
  </button>
);
const HelloReact = ({ hello, isDisplayed }) =>
  isDisplayed ? <h1>{hello}</h1> : null;
export default App;
```
## Mind Tree

What is Optional Chainiing in Typescript?

What is promises? How do you handle it? Can you write one promise without axios?
We have used axios.

Can you tell me the life cycle hooks that will execute while render phase and update phase seperatly

What is the difference between null and undefined?

What is the difference between == and ===?

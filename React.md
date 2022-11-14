# Props In React
 <h2 style="color:green;"> Functional Components </h2>
 
1. Pass props as properties in functional components like this:

```javascript
const Greet = (props) => {
    return <h1>Hello {props.name}</h1>
}
```

* Now, in App.js write the code given below:
```javascript
<Greet name="Bruce"/>
<Greet name="Clark"/>
```

Output:
> Hello Bruce
> Hello Clark

2. Passing HTML as props in functional components:
* App.js
```javascript
<div>
    <h1>Hello {props.name} you like {props.heroName}</h1>
    {props.children}
</div>
```

Output:
> Hello Bruce you like Superman.
> This is a children props.

 <h2 style="color:green;"> Class Components </h2>
Unlike the functional component where we specify the props parameter in a class component the properties are available through (this.props) which is reserved in class component.

1. Welcome.js
```javascript
return (
<h1>Welcome {this.props.name}</h1>
)
```

Basically we are accessing the props with **this** keyword.

2. App.js
```javascript
return (
<Welcome name="Clark"/>
)
```

Output:
> Welcome Clark

# State In React
 <h2 style="color:green;"> Class Components </h2>
 
Message.js

```javascript
class Message extends Component {
    constructor() {
        super()
        this.state = {
            message: "Welcome Visitor!",
        }
    }
    changeMessage() {
        this.setState({
            message: "Thank you for subscribing"
        })
    }
    render() {
        return (
            <>
                <h1>{this.state.message}</h1>
                <button onClick={
                    () => this.changeMessage()
                }>Subscribe</button>
            </>
        )
    }
}
```

App.js
```js
<Message/>
```

Output:
> Welcome Visitor
> **Subscribe**

# Desctucturing Props And State

## Destructuring Props
 <h2 style="color:green;"> Functional Components </h2>
There are **two ways** to destructor props in functional component:

**First way** is to destructure it in the function parameter itself.

Greet.js
```js
const Greet = ({name, heroName0}) => {
	return (
		<>
			<h1>
				Hello {name} a.k.a {heroName}
			</h1>
		</>
	)
}
```

**Second way** to destructor the props in functional component is to destructure it inside body.

Greet.js
```js
const Greet = props => {
	const {name, heroName} = props
	return (
		<>
			<h1>
				Hello {name} a.k.a {heroName}
			</h1>	
		</>
	)
}
```

 <h2 style="color:green;"> Class Components </h2>
Now, in class component we generally tend to destructive props or state in the render method.

Welcome.js
```js
render() {
	const {name, heroName} = this.props
	return(
		<h1>
			Welcome {name} a.k.a {heroName} 
		</h1>
	)
}
```

## Destructuring State

Code:
```js
render() {
	const {state, state2} = this.state
	return(...)
}
```

# Event Handling

 <h2 style="color:green;"> Functional Components </h2>
FunctionClick.js
```js
function clickHandler() {
	console.log('Button Clicked')
}
return (
	<>
		<button onClick={clickHandler}>Click</button>
	</>
)
```

 <h2 style="color:green;"> Class Components </h2>
ClassClick.js
```js
clickHandler() {
	console.log("Clicked the button")
}
render(){
	return(
		<>
			<button onClick={this.clickHandler}>Click Me</button>
		</>
	)
}
```

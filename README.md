# Redux Intro with React

From tutorial: https://daveceddia.com/how-does-redux-work/

![screenshot of counter](https://i.imgur.com/0RwTqxV.png)

## Steps:
### 1. Connect the component to Redux.  
```
// Counter.js
this.props.count
```
### 2. mapStateToProps
```
// Counter.js
const mapStateToProps = (state) => ({
    count: state.count
});
export default connect(mapStateToProps)(Counter);
```
### 3. Create the store
```
// index.js
const store = createStore(reducer);
```
### 4. Create a reducer
```
// index.js
function reducer(state = initialState, action) {
    switch(action.type) {
        case "INCREMENT":
            return {
                count: state.count +1
            };
        case "DECREMENT":
            return {
                count: state.count -1
            };
        default:
            return state;
    }
}
```
### 5. Provide the store to the app
```
// index.js
<Provider store = {store}>
    <Counter />
</Provider>
```
### 6. Wire up actions
```
// 
increment = () => {
    this.props.dispatch({ type: "INCREMENT" })
}

decrement = () => {
    this.props.dispatch({ type: "DECREMENT" })
}
```

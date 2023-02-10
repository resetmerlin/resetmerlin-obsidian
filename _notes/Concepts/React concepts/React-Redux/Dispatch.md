1. What is dispatch?

	- In a React-Redux application, the dispatch function is used to trigger an action that will update the state of the application. The dispatch function is typically provided by the store object, which is created using the createStore function from the redux library.

	- When an action is dispatched, it is passed through a series of "reducers" that determine how the state of the application should be updated in response to that action. Each reducer is a pure function that takes the current state and an action as input, and returns the next state.

	- When you use the connect function from the react-redux library to connect a component to the store, the dispatch function is typically made available to the component as a prop, so the component can trigger actions by calling dispatch with an action object.

2. Summary
	- In summary, Dispatch is a way to send an action to the store and update the state.



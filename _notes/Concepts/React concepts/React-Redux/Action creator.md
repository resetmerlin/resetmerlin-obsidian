1. What is Action creator?
	- In Redux, actions and action creators are related concepts that work together to update the state of the store.
	
	- An action is an object that describes the type of operation being performed and the payload of data that will be used to update the state. An action typically has a "type" property that specifies the type of operation and a "payload" property that contains the data to be used in the update.
	
	- An action creator is a function that creates and returns an action.  ***Action creators make it easier to create and dispatch actions in a consistent and organized manner. They can also be used to encapsulate logic that is used to create the action, such as transforming data or making API calls.

Here is an example:

```js
// Action
const ADD_TODO = {
  type: "ADD_TODO",
  payload: {
    id: 1,
    text: "Learn Redux"
  }
};

// Action Creator
function addTodo(text) {
  return {
    type: "ADD_TODO",
    payload: {
      id: Math.random(),
      text: text
    }
  };
}

// Dispatching the Action
dispatch(addTodo("Learn Redux"));

```
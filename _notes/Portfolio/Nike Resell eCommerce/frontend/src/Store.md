```js

import { createStore, combineReducers, applyMiddleware } from "redux";

import thunk from "redux-thunk";

import { composeWithDevTools } from "redux-devtools-extension";

import {

  cyberProductReducers,

  cyberProductDetailReducers,

} from "./reducers/cyberProductReducers";

import { cyberCartReducers } from "./reducers/cyberCartReducers";

import { cyberUserLoginReducers } from "./reducers/cyberUserReducer";

const reducer = combineReducers({
  cyberProductLists: cyberProductReducers,
  cyberProductDetails: cyberProductDetailReducers,
  cyberCart: cyberCartReducers,
  cyberLogin: cyberUserLoginReducers,
});

const cartItemsFromStorage = localStorage.getItem("cyberCartItems")
  ? JSON.parse(localStorage.getItem("cyberCartItems"))
  : [];

  

const userInfoFromStorage = localStorage.getItem("userInfo")
  ? JSON.parse(localStorage.getItem("userInfo"))
  : null;

const initialState = {
  cyberCart: {
    cyberCartItems: cartItemsFromStorage,
  },

  userLogin: {
    userInfo: userInfoFromStorage,

  },

};

const middleware = [thunk];

const store = createStore(

  reducer,

  initialState,

  composeWithDevTools(applyMiddleware(...middleware))

);

  

export default store;
```

1. Explaination:
	1. The variable is defined using 'combineReducers' method from redux, and this combines multiple reducers into a single reducer for the entire application state.
	```js
	const reducer = combineReducers({
	  cyberProductLists: cyberProductReducers,
	  cyberProductDetails: cyberProductDetailReducers,
	  cyberCart: cyberCartReducers,
	  cyberLogin: cyberUserLoginReducers,
});

```
		In this code, 'reducer' is composed of four reducers: 'cyberProductLists', 'cyberProductDetails', 'cyberCart', 'cyberLogin'

	2. The initialState is an object that defines the initial state of the application.
	```js
	const initialState = {
  cyberCart: {
    cyberCartItems: cartItemsFromStorage,
  },

  userLogin: {
    userInfo: userInfoFromStorage,

  },

};
```

	3. The variable name 'middleware' is defined by using thunk from redux-thunk. It allows asynchronous actions in Redux
	```js
	const middleware = [thunk];
```


	4. The variable store is created by using 'createStore' method from the 'redux' library. createStore takes 3 arguments, which is reducer, initialStatem enhancer.

		this is an example of using creatStore
		```js
	const store = createStore(myReducer, initialState, myEnhancer);
```

	5.  This is a code that I got
	```js
	const store = createStore(
	  reducer,
	  initialState,
	  composeWithDevTools(applyMiddleware(...middleware))
);
```

	6. So composeWithDevTools is an enhancer. This integrates the Redux DevTools browser extension with your Redux store. It ables to visualize the state changes.

![[Pasted image 20230204120356.png]]
		

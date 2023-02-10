```js
import {
  CYBER_USER_LOGIN_REQUEST,
  CYBER_USER_LOGIN_SUCCESS,
  CYBER_USER_LOGIN_FAIL,
  CYBER_USER_LOGOUT,
} from "../constants/userConstants";


export const cyberUserLoginReducers = (state = {}, action) => {
  switch (action.type) {
    case CYBER_USER_LOGIN_REQUEST:
      return { loading: true, ...state };
  
    case CYBER_USER_LOGIN_SUCCESS:
      return {
        loading: false,
        userInfo: action.payload,
      };

    case CYBER_USER_LOGIN_FAIL:
      return { loading: false, error: action.payload };
      
    case CYBER_USER_LOGOUT:
      return {};

    default:
      return state;

  }

};
```

1. Explaination:
	1. This code is about login [[Reducer]]. Which mean is when user logins and calls [[User action]], this reducer is also being executed. 
	2. But how this reducer is being executed?
	3. [[Reducer]] is a function that takes the current state and an action as input, and returns a new state. [[User action]] being called by when user logins right? 


	this code is from [[User action]].
	```js
    dispatch({ type: CYBER_USER_LOGIN_REQUEST });
```


	4. this [[Dispatch]], triggers action to update the state.  So when an action is excuted, it dispatch to the reducer and the reducer determine how the state of the application should be updated in response to that action.

	5. If u look at the code cyberUserLoginReducers, it uses switch method to verify the case. When the case is equal as an action.type, it returns the new state.
	```js

export const cyberUserLoginReducers = (state = {}, action) => {
  switch (action.type) {
    case CYBER_USER_LOGIN_REQUEST:
      return { loading: true, ...state };

  
    default:
      return state;

  }

};
```
	6. When User action executes, it dispatch({ type: CYBER_USER_LOGIN_REQUEST });, and 'cyberUserLoginReducers' get this action.type. When there is a case equals to the action.type(CYBER_USER_LOGIN_REQUEST ), it return the new state or update the state.


	7. However eventhogh u made this action and reducer, the react-redux doesn't work till u make specific [[Store]]. In the [[Store]], u have to define 
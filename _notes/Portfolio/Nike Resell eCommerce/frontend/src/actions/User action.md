```js
import {
  CYBER_USER_LOGIN_REQUEST,
  CYBER_USER_LOGIN_SUCCESS,
  CYBER_USER_LOGIN_FAIL,
} from "../constants/userConstants";
import axios from "axios";


//action creator
export const loginAction = (email, password) => async (dispatch) => {
  try {
    dispatch({ type: CYBER_USER_LOGIN_REQUEST });
    const config = {
      headers: {
        "Content-Type": "application/json",
      },
    };

    const { data } = await axios.post(
      "/api/users/login",
      { email, password },
      config
    );

    dispatch({ CYBER_USER_LOGIN_SUCCESS, payload: data });
    
    localStorage.setItem("userInfo", JSON.stringify(data));
    
  } catch (error) {
    dispatch({
      type: CYBER_USER_LOGIN_FAIL,
      payload:
        error.response && error.response.data.message
          ? error.response.data.message
          : error.messge,
    });

  }

};
```

1. Explaination

	- This is an action for the user to login. When user logins, he or she submits email and password right? so we gonna make this action to be true.

2. Steps
	1. First we have to create [[User Constants]] for the action. [[Constants]] is important if u use as an action type in react-redux.
	2. Second, we create [[Action creator]] to work just like an action but function.  When user logins, we want this action to be called. So we will name this action as 'loginAction'. This Action creator(function) will get email and password arguments. 
	```js
export const loginAction = (email, password) => async (dispatch) => {

  try {
  } catch (error) {
  }

};
```
		use try, catch method to handle error while fetch api

	3. Once user request this action, user will [[Dispatch]] the type from [[User Constants]].  
	```js
	    dispatch({ type: CYBER_USER_LOGIN_REQUEST });
```

	4. If this is dispatched action succeed, we will create variable name 'config' to define [[Content-type]] and [[MIME type]]. 
	```js
	const config = {
      headers: {
        "Content-Type": "application/json",
      },
    };
```

	5. then, we will use [[axios]] to [[fetch api]]. When user logins, he/she submits email and password to the server right? According to [[HTTP request methods]], this method equals to post method. User will request body(email, password) to submit to 'url' or endpoint. 
	```js
	const { data } = await axios.post(

      "/api/users/login",

      { email, password },

      config
      //const config = {
      //headers: {
        //"Content-Type": "application/json",
     // },
   // };

    );
```
		so in this code, url is 
	```js
"/api/users/login"
```

		and request body is 
	```js
{ email, password },
```
	
	**last, this is the property(headers) from [[Axios config]].
	```js
  config
      //const config = {
      //headers: {
        //"Content-Type": "application/json",
     // },
   // };
```

6. After fetching api using axios, we dispatch action if it succeed and we will payload the data that we get from the server(res). So the data we can get is defined by the backend. 

7. We will also store this userInfo data in [[localStorage]]. 
	```js
	 localStorage.setItem("userInfo", JSON.stringify(data));
```



8. Whenever it has error, we will send action type which is login got failed.
	```js
	 dispatch({
      type: CYBER_USER_LOGIN_FAIL,
      payload:
        error.response && error.response.data.message
          ? error.response.data.message
          : error.messge,
    });
```
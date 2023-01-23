
## Current code

This is from [[Cart Constans]]
```js
import {

  CYBER_CART_ADD_ITEM,

  CYBER_CART_REMOVE_ITEM,

  CYBER_CART_SAVE_SHIPPING_ADDRESS,

  CYBER_CART_SAVE_PAYMENT_METHOD,

} from "../constants/cartConstants";
 ```
	 we import these constants from cart constants


 
```js

import axios from "axios";
//action creator
//Redux thunk
export const addItemToCart = (id, qty) => async (dispatch, getState) => {
```
	we will get argument of dispatch, getState by using async operation. The role of getState is to get whole state from store script



## From Store script 

The whole state I refered from [[Store]] script 
```js
// this is from Store script
const reducer = combineReducers({
  cyberProductLists: cyberProductReducers,
  cyberProductDetails: cyberProductDetailReducers,
  cyberCart: cyberCartReducers,
});
```

## Current code

and then we will fetch data by using [[axios]]
	
```js
  const { data } = await axios.get(`/api/cyberProducts${id}`);
```
	It tells that we use get method to get data from server which is api call.


after fetching data from server, we will [[Dispatch]] it specifically.
```js
  dispatch({

    type: CYBER_CART_ADD_ITEM,

    payload: {

      cyberProduct: data._id,

      name: data.name,

      image: data.image,

      price: data.price,

      countInStock: data.countInStock,

      qty,

    },

  });

```


we will gonna make the data to store in the browser's [[localStorage]]
```js

  localStorage.setItem("cyberCartItems",JSON.stringify(getState().cyberCart.cyberCartItems)
  );
};
```

## From Store script 

to make this work, we have to set in the [[Store]] script
```js
const cartItemsFromStorage = localStorage.getItem("cyberCartItems")

  ? JSON.parse(localStorage.getItem("cyberCartItems"))

  : [];

```

## Current code
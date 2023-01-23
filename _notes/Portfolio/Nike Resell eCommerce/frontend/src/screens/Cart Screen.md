```js
import CartList from "../components/CartList";

import React, { useState, useEffect } from "react";

import {useParams, Link, useSearchParams, useLocation} from "react-router-dom";

import { useDispatch, useSelector } from "react-redux";
```
This is from [[Cart Action]]
```js
import { cyberProductsAction } from "../actions/cyberProductActions";
```


```js
const CartScreen = () => {

  const dispatch = useDispatch();
```

- Before this We code to navigate to go to this Cart Screen
```js
    navigate(`/cart/${id}?qty=${qty}`);
```
- Current URL : http://127.0.0.1:5173/cart/63bf630e02d1a3b301eeb75a?qty=1
```js
  const { id } = useParams();
```
	If I use useParams(), and console.log the value, the result will be like this  
```
63bf630e02d1a3b301eeb75a
```
	 The thing we are doing right now is try to get cart quantity. 

	
 - We can use  [[useLocation]] to get current locaton.   
```js
  const location = useLocation().search;
```

	if we console.log(location), this is gonna display like this
```
?qty=1
```
	but the thing is we want to get number next to ?qty= 
	
- [[URLSearchParams]] will help to get the number of quantity

```js
  const qty = new URLSearchParams(location).get("qty");
  // Result will be 1
```

- Now, we get the quantity that sent from previous screen. Next is get cyberCart states from store script
```js
  const cyberCart = useSelector((state) => state.cyberCart);
  
  const { cyberCartItems } = cyberCart;
```
-  We check if the id(useParams) is true or not and then dispatch addItemToCart action. 

```js
  useEffect(() => {

    if (id) {

      dispatch(addItemToCart(id, qty));

    }

  }, [dispatch, id, qty]);
```
	pass the arguments id, qty.
	

```js
   return (

    <>

      {" "}

      <h1 className="title">Order/Payment</h1>

      <div className="row__cart">

        <div

          className="row__list-group-item "

          style={{

            height: "3rem",

            borderBottom: "1px solid black",

          }}

        >

          <div className="list-item-image"></div>

          <div className="list-item-title">Product name</div>

  

          <div className="list-item-price">Price</div>

  

          <div className="list-item-qty">Quantity</div>

          <div className="list-item-qty">Delete</div>

        </div>

        <div className="row">

          {cyberCartItems.map((cartItems) => (

            <CartList CartValue={cartItems}></CartList>

          ))}

        </div>

      </div>

    </>

};

  

export default CartScreen;
```

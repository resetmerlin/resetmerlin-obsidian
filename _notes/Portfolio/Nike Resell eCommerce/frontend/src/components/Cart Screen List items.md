```jsx


import React, { useState } from "react";
import { useParams, Link } from "react-router-dom";
import { useDispatch, useSelector } from "react-redux";
import { addItemToCart } from "../actions/cyberCartAction";

  

const CartList = ({ CartValue }) => {

  const dispatch = useDispatch();

  

  return (

    <>

      <div className="row__list-group-item">

        <div className="list-item-image"
        style={{ backgroundImage: `url(${CartValue.image})` }}>
        </div>

        <Link to={`/cyberProduct/${CartValue.cyberProduct}`}
         className="list-item-title">

          {CartValue.name}

        </Link>

        <div className="list-item-price">{CartValue.price}</div>

  
```

	This Script is quite easy, however most important part is this one.
```jsx
        <form className="list-item-qty">
          <select
            value={CartValue.qty}
            onChange={(e) =>
              dispatch(
                addItemToCart(CartValue.cyberProduct, Number(e.target.value))
              )
            }
          >
            {[...Array(CartValue.countInStock).keys()].map((x) => (
              <option key={x + 1} value={x + 1}>
                {x + 1}
              </option>
            ))}
          </select>
        </form>


```
If u visualize the form code, it will be like this:
![[Pasted image 20230115170204.png]]
	we just created select form on the below of tag Quantity.  
If u split this code precisely, it would be like this:

```jsx
		<select
            value={CartValue.qty}
            onChange={(e) =>
              dispatch(
                addItemToCart(CartValue.cyberProduct, Number(e.target.value))
              )
            }
          >
```
- value={CartValue.qty} : The quantity we selected from product screen, 
![[Pasted image 20230115170602.png]]
- If u click Order now, it will display like this:
 ![[Pasted image 20230115170651.png]]
- And the Select code enable us to change quantity in cart screen. When we select quantity of product, the value will be store into localStorage. 
- So the question is.. do we have to regenerate setlocalStorage?
- Answer is nope.
- we handled localStorage at [[Cart Action]]. That mean is we just have to [[Dispatch]] action again.
```jsx 
 onChange={(e) =>
              dispatch(
                addItemToCart(CartValue.cyberProduct, Number(e.target.value))
              )
```

- If we change the quantity from select form, we dispatch addItemToCart action which takes two arguments(id,qty). We can get id from CartValue.cyberProduct, and able to get qty by targeting current change of quantity select form. 

```jsx
        <i className="bx bxs-trash list-item-delete"></i>
      </div>

    </>

  );

};

  

export default CartList;
```
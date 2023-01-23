1. get params from current location URL
	- . http://127.0.0.1:5173/cart/63bf630e02d1a3b301eeb75a?qty=1
	- I want to get the number next to qty= 
	- get location url first 


```js

  const location = useLocation().search;
  
```
			if I console.log(location), I will get ?qty=1. 

-  I can use [[URLSearchParams]] to get a param that i want
-    const quantity = new URLSearchParams(location).get("qty");

	  
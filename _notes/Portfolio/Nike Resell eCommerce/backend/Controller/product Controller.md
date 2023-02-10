1. The reason making this [[Controllers]] is because it enable us to handle the incoming request, retrieves the necessary data from the model, and passes it to the view to be displayed to the user. 

```js
import asyncHandler from "express-async-handler";
import cyberProductModel from "../models/productModel.js";

// @desc Fetch all products
// @route GET /api/products
// @access  Public
const getProducts = asyncHandler(async (req, res) => {
  const cyberProducts = await cyberProductModel.find({});

  res.json(cyberProducts);

});
 
// @desc Fetch single product
// @route GET /api/products/:id
// @access  Public
const getProductById = asyncHandler(async (req, res) => {
  const cyberProduct = await cyberProductModel.findById(req.params.id);

  if (cyberProduct) {

    return res.json(cyberProduct);

  } else {

    res.status(404);
    //custom error handler
    throw new Error("Product not found");
  }

  res.json(cyberProduct);

});


export { getProductById, getProducts };
```
***

***Explaination 

1. Before looking at this code, we need to know about [[Product routes]] code. This code is fine, but we can implement by using Controller. 

2. Basic structure of Controller is like this:
```js
import asyncHandler from "express-async-handler";
import cyberProductModel from "../models/productModel.js";

const getProducts = asyncHandler(async (req, res) => {
});

const getProductById = asyncHandler(async (req, res) => {
});
 
export { getProductById, getProducts };
```
3. Inside of 'getProducts' and 'getProductById', we will gonna put the code from product routes.

```js
import asyncHandler from "express-async-handler";
import cyberProductModel from "../models/productModel.js";


// @desc Fetch all products
// @route GET /api/products
// @access  Public
const getProducts = asyncHandler(async (req, res) => {

	//this is from Product Routes
    const cyberProducts = await cyberProductModel.find({});
    res.json(cyberProducts);
    
});


// @desc Fetch single product
// @route GET /api/products/:id
// @access  Public
const getProductById = asyncHandler(async (req, res) => {

  const cyberProduct = await cyberProductModel.findById(req.params.id);
  
    if (cyberProduct) {
      return res.json(cyberProduct);
    } else {
      res.status(404);
      //custom error handler
      throw new Error("Product not found");
    }
    res.json(cyberProduct);
});
 
export { getProductById, getProducts };
```

4. After finishing cutting code from product routes, we can delete the original code
```js
//From Product Routes
router.get(
  "/",
  asyncHandler(async (req, res) => {
    const cyberProducts = await cyberProductModel.find({});
    res.json(cyberProducts);

  })

```
	Into like this:
```js
router.route("/").get(getProducts)

```
	it is much clean right??

5. We can make other code much cleaner before like 'router.get("/").get(getProducts)'.


		Before
```js
router.get(
  "/:id",
 asyncHandler(async (req, res) => {
    const cyberProduct = await cyberProductModel.findById(req.params.id);
  
    if (cyberProduct) {

      return res.json(cyberProduct);

    } else {

      res.status(404);

      //custom error handler

      throw new Error("Product not found");

    }

  

    res.json(cyberProduct);

  })

);
```
	After
```js
router.route("/:id").get(getProductById)
```

6. Final result is gonna be like this, u can see the difference [[Product routes]] compare to before.
```js
import asyncHandler from "express-async-handler";
import cyberProductModel from "../models/productModel.js";
  
// @desc Fetch all products
// @route GET /api/products
// @access  Public
const getProducts = asyncHandler(async (req, res) => {
  const cyberProducts = await cyberProductModel.find({});
  res.json(cyberProducts);
});

// @desc Fetch single product
// @route GET /api/products/:id
// @access  Public

const getProductById = asyncHandler(async (req, res) => {
  const cyberProduct = await cyberProductModel.findById(req.params.id);
  if (cyberProduct) {
    return res.json(cyberProduct);
  } else {
    res.status(404);
    //custom error handler
    throw new Error("Product not found");
  }
  res.json(cyberProduct);
});

  
export { getProductById, getProducts };
```
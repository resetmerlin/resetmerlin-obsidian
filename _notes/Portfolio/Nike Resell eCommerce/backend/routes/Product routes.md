1. After the [[product Controller]],
```js
import express from "express";
const router = express.Router();

import {
  getProductById,
  getProducts,
} from "../controllers/cyberProductControllers.js";
  

router.route("/").get(getProducts);
router.route("/:id").get(getProductById);
  

export default router;
```

2. Before the [[product Controller]],
```js
import express from "express";
const router = express.Router();
import expressAsyncHandler from "express-async-handler";
import cyberProductModel from "../models/productModel.js";
import asyncHandler from "express-async-handler";

// @desc Fetch all products
// @route GET /api/products
// @access  Public
router.get(
  "/",
  asyncHandler(async (req, res) => {
    const cyberProducts = await cyberProductModel.find({});
    res.json(cyberProducts);
  })
);
// @desc Fetch single product
// @route GET /api/products/:id
// @access  Public
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

export default router;
```
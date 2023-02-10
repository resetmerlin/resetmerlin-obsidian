```js
import express from "express";
const router = express.Router();
import { protection } from "../middleware/authMiddleware.js";

import {
  authenticationUser,
  getClientProfile,
} from "../controllers/userController.js";

  

router.route("/login").post(authenticationUser);
router.route("/profile").get(protection, getClientProfile);

  

export default router;
```

1. After protection function begins, start getClientProfile function after this


2. This is login server flow
![[Sign-in workflow.excalidraw]]

3. This is Profile server flow
![[profile server-flowexcalidraw]]
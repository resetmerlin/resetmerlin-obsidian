### router.route(path)

1. It returns an instance of a single route which you can then use to handle HTTP verbs with optional middleware. Use `router.route()` to avoid duplicate route naming and thus typing errors.

2. Building on the `router.param()` example above, the following code shows how to use `router.route()` to specify various HTTP method handlers.

```javascript
const router = express.Router()

router.param('user_id', (req, res, next, id) => {
  // sample user, would actually fetch from DB, etc...
  req.user = {
    id,
    name: 'TJ'
  }
  next()
})

router.route('/users/:user_id')
  .all((req, res, next) => {
  // runs for all HTTP verbs first
  // think of it as route specific middleware!
    next()
  })
  .get((req, res, next) => {
    res.json(req.user)
  })
  .put((req, res, next) => {
  // just an example of maybe updating the user
    req.user.name = req.params.name
    // save user ... etc
    res.json(req.user)
  })
  .post((req, res, next) => {
    next(new Error('not implemented'))
  })
  .delete((req, res, next) => {
    next(new Error('not implemented'))
  })
```

This approach re-uses the single `/users/:user_id` path and adds handlers for various HTTP methods.
1. What is axios?

	- axios is a JavaScript library that allows you to make HTTP requests from the browser or Node.js. It is similar to the Fetch API, but with a few additional features such as automatic JSON parsing and support for older browsers.

	- Axios is commonly used for making API calls to retrieve or update data on a server. It can also be used for other types of HTTP requests, such as sending a file or submitting a form. Additionally, it is also often used to handle response from server and handle error if any.

2. Example:

```js
// POST 요청 전송
axios({
  method: 'post',
  url: '/user/12345',
  data: {
    firstName: 'Fred',
    lastName: 'Flintstone'
  }
});
```

	
	`axios()`에 url을 전달해 요청할 수 있다. 선택적으로 `config` 객체를 2번째 인자로 추가 전달할 수 있다.
```
axios(url[, config])
```
```js
// GET 요청 전송 (기본 메서드)
axios('/user/12345');
```

## HTTP 메서드 별칭

```js
axios.get(url[, config])            // GET
axios.post(url[, data[, config]])   // POST
axios.put(url[, data[, config]])    // PUT
axios.patch(url[, data[, config]])  // PATCH
axios.delete(url[, config])         // DELETE

axios.request(config)
axios.head(url[, config])
axios.options(url[, config])
```

 
 별칭 메소드를 사용하면 설정([[Axios config]])에서 `url`, `method` 및 `data` 속성을 지정할 필요가 없다.

```js
// axios() 사용 시
axios({
  url: '/user/12345',
  method: 'put',
  data: {
    firstName: 'Fred',
    lastName: 'Flintstone'
  }
})
```

```js
// axios.put() 별칭 메서드 사용 시
axios.put('/user/12345', {
  firstName: 'Fred',
  lastName: 'Flintstone'
})
```


If you want more, read axios document

https://yamoo9.github.io/axios/
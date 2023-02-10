1. What is Formik?
	- Formik is a popular library for handling forms in React. 
	- Formik is one of the most popular open source form library for React and React Native. It has 31.4k stars on GitHub and 2.1 million user downloads on npm.

2. Usage
	1. Install formik via npm 
	```
	npm install formik --save
	``` 

	2.  Import Formik in react
	```js
	import { Formik, Form, Field, ErrorMessage } from "formik";
	```

	3.  Wrap your form component inside the `Formik` component:
	```jsx
	<Formik
	  initialValues={{ email: '', password: '' }}
	  onSubmit={(values, { setSubmitting }) => {
    setTimeout(() => {
      alert(JSON.stringify(values, null, 2));
      setSubmitting(false);
	    }, 400);
	  }}
>			
  {({ isSubmitting }) => (
    <Form>
      <Field type="email" name="email" />
      <ErrorMessage name="email" component="div" />
      <Field type="password" name="password" />
      <ErrorMessage name="password" component="div" />
      <button type="submit" disabled={isSubmitting}>
        Submit
      </button>
    </Form>
  )}
</Formik>
```

	4.  Use the `Field` component to bind form inputs to Formik state:
	```jsx
	<Field type="email" name="email" />
	<ErrorMessage name="email" component="div" />
	```
# Guide

## Request Config Defaults

You can specify config defaults that will be applied to every request.

### Global `axios` Defaults

```ts
axios: {
  defaults: {
    baseUrl: 'https://api.example.com'
    headers: {
      common: {
        Authorization: AUTH_TOKEN
      }
      post: {
        'Content-Type': 'application/x-www-form-urlencoded'
      }
    }
  }
}
```

### Custom Instance Defaults

* Set config defaults when creating the instance
* Alter defaults after instances has been created

### Config Order of Precedence

Config will be merged with an order of precedence.

1. Library defaults
2. `defaults` property of the instance
3. `config` argument for the request

## Interceptors

You can intercept requests or responses before they are handled by `then` or `catch`.

* Add a request interceptor

  ```ts
  axios
    .interceptors
    .request
    .use(
      config => config, 
      error => Promise.reject(error)
    );
  ```

* Add a response interceptor

  ```ts
  axios
    .interceptors
    .response
    .use(
      response => response,
      error => Promise.reject(error)
    );
  ```

* Remove an interceptor

  ```ts
  const myInterceptor = axios.interceptors.request.use(...);
  axios.interceptors.request.eject(myInterceptor);
  ```

* Add interceptors to a custom instance of `axios`

  ```ts
  const instance = axios.create();
  instance.interceptors.request.use(...);
  ```

## Handling Errors

```ts
axios.get('...').catch(error => {...});
```

* `error.response`
  * The request was made and the server reponded with a status code that falls out of the `validateStatus` range
  * Available fields: `data`, `status`, `headers`
* `error.request`
  * The request was made but no response was received
  * An instance of `XMLHttpRequest` in the browser
  * An instance of `http.ClientRequest` in Node.js
* `error.message`
  * Something happened in setting up the request that triggered an Error
* `error.config`

## Cancellation

You can cancel a request using a **cancel token**. 

* Create a cancel token using the `CancelToken.source` factory.

  ```ts
  const source = axios.CancelToken.source();

  axios
    .get('...', { cancelToken: source.token })
    .catch(thrown => {
      if (axios.isCancel(thrown)) {
        console.log('Request canceled:', thrown.message);
      }
    });

  axios.post(
    '...',
    { name: 'new name' },
    { cancelToken: source.token }
  );

  source.cancel('Operation cancelled by user.');
  ```

* Create a cancel token by passing an executor function to the `CancelToken` constructor

  ```ts
  const CancelToken = axios.CancelToken;
  let cancel;

  axios.get('...', {
    cancelToken: new CancelToken(c => { cancel = c; })
  });

  cancel();
  ```

> **Note:** You can cancel several requests with the same cancel token.

## Using `application/x-www-form-urlencoded` Format

### Browser

* Use the `URLSearchParams` API

  ```ts
  const params = new URLSearchParams();
  params.append('param1', 'value1');
  params.append('param2', 'value2');
  axios.post('/foo', params);
  ```

* Use the `qs` library

  ```ts
  import qs from 'qs';
  
  const data = { bar: 123 };

  const options = {
    method: 'POST',
    headers: {
      'content-type': 'application/x-www-from-urlencoded'
    },
    data: qs.stringify(data),
    url,
  };

  axios(options);
  ```

### Node.js

* Use the `querystring` module

  ```ts
  import querystring from 'querystring';

  axios.post(
    '...',
    querystring.stringify({ foo: 'bar' })
  );
  ```

* Use the `qs` library
  * This method is preferrable if you need to stringify nested objects
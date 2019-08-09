# API

```ts
import axios from 'axios';
```

## With Configuration

* `axios(config)`
* `axios(url[, config])`

## Request Method Aliases

* `axios.request(config)`
* `axios.get(url[, config])`
* `axios.delete(url[, config])`
* `axios.head(url[, config])`
* `axios.options(url[, config])`
* `axios.post(url[, data[, config]])`
* `axios.put(url[, data[, config]])`
* `axios.patch(url[, data[, config]])`

## Concurrency

Helper functions for dealing with concurrent requests.

* `axios.all(iterable)`
* `axios.spread(callback)`

## Creating an Instance

You can create a new instance of axios with a custom config.

* `axios.create([config])`

### Instance Methods

The available instance methods are listed below. The specified config will merge with the instance config.

* `axios#request(config)`
* `axios#get(url[, config])`
* `axios#delete(url[, config])`
* `axios#head(url[, config])`
* `axios#options(url[, config])`
* `axios#post(url[, data[, config]])`
* `axios#put(url[, data[, config]])`
* `axios#patch(url[, data[, config]])`
* `axios#getUri([config])`

## Request Configuration

These are the available config options for making requests. Only the `url` is required. Requests will default to `GET` if `method` is not specified.

* `url: string`
  * The server URL that will be used for the request
  * Example - `'/user'`
* `method: string`
  * The request method to be used when making the request
  * Example - `'get'` (default)
* `baseURL: string`
  * Will be prepended to `url`, unless `url` is absolute
  * It can be convenient to set this for an instance of axios, to pass relative URLs to methods of that instance
  * Example - `'https://some-domain.com/api/`
* `transformRequest: Array<(data, headers) => data>`
  * Allows changes to the request data before it is sent to the server
  * This is only applicable for request methods `PUT`, `POST`, `PATCH`, and `DELETE`
  * The last function in the array must return a string or an instance of `Buffer`, `ArrayBuffer`, `FormData`, or `Stream`
  * You may modify the `headers` object
* `transformResponse: Array<data => data>`
  * Allows changes to the response data to be made before it is passed to `then`/`catch`
* `headers: object`
  * Custom headers to be sent
  * Example - `{ 'X-Requested-With': 'XMLHttpRequest' }`
* `params: object`
  * The URL parameters to be sent wit hthe request
  * Must be a plain object or a `URLSearchParams` object
  * Example - `{ ID: 12345 }`
* `paramsSerializer(params): string`
  * An optional function in charge of serializing `params`
* `data: object`
  * The data to be sent as the request body
  * Only applicable for request methods `PUT`, `POST`, and `PATCH`
  * When no `transformRequest` is set, must be one of the following types:
    * `string`, `object`, `ArrayBuffer`, `ArrayBufferView`, `URLSearchParams`
    * Browser only - `FormData`, `File`, `Blob`
    * Node only - `Stream`, `Buffer`
  * Example - `{ firstName: 'Fred' }`
* `timeout: number`
  * Specifies the number of milliseconds before the request times out
  * If the request takes longer than `timeout`, the request will be aborted
  * Default - `0` (no timeout)
  * Example - `1000`
* `withCredentials: boolean`
  * Indicates whether or not cross-site Access-Control requests should be made using credentials
  * Example - `false` (default)
* `adapter(config): Promise`
  * Allows custom handling of requests, which makes testing easier
  * Return a `Promise` and supply a valid response
* `auth: { username: string; password: string; }`
  * Indicates that HTTP Basic auth should be used, and supplies credentials
  * This will set an `Authorization` header, overwriting any existing `Authorization` custom headers you have set using `headers`
  * Please note that only HTTP Basic auth is configurable through this parameter
  * For Bearer tokens and such, use `Authorization` custom headers instead
* `responseType: string`
  * Indicates the type of data that the server will respond with
  * Options are:
    * `'arraybuffer'`
    * `'document'`
    * `'json'`
    * `'text'`
    * `'stream'`
    * `'blob'` (browser only)
  * Default - `'json'`
* `responseEncoding: string`
  * Indicates encoding to use for decoding responses
  * Note: Ignored for `responseType` of `'stream'`, or client-side requests
  * Default - `'utf8'`
* `xsrfCookieName: string`
  * The name of the cookie to use as a value for xsrf token
  * Default - `'XSRF-TOKEN'`
* `xsrfHeaderName: string`
  * The name of the http header that carries the xsrf token value
  * Default - `'X-XSRF-TOKEN'`
* `onUploadProgress(progressEvent): void`
  * Allows handling of progress events for uploads
* `onDownloadProgress(progressEvent): void`
  * Allows handling of progress events for downloads
* `maxContentLength: number`
  * Defines the max size of the http response content in bytes allowed
  * Example - `2000`
* `validateStatus(status): boolean`
  * Defines whether to resolve or reject the promise for a given HTTP response status code
  * If the function returns `true` (or is set to `null` or `undefined`), the promise will be resolved
  * Otherwise, the promise will be rejected
* `maxRedirects: number`
  * Defines the maximum number of redirects to follow in Node.js
  * If set to `0`, no redirects will be followed
  * Default - `5`
* `socketPath: string | null`
  * Defines a UNIX Socket to be used in Node.js
  * Only `socketPath` or `proxy` can be specified
  * Default - `null`
  * Example - `'/var/run/docker.sock'` sends requests to the docker daemon
* `httpAgent: new http.Agent({ keepAlive: true })`
* `httpsAgent: new https.Agent({ keepAlive: true })`
  * Define a custom agent to be used when performing http and https requests, respectively, in Node.js
  * This allows options to be added, like `keepAlive` that are not enabled by default
* ```
  proxy: {
    host: string;
    port: number;
    auth: {
      username: string;
      password: string;
    }
  }
  ```
  * Defines the hostname and port of the proxy server
  * You can also define your proxy using the conventional `http_proxy` and `https_proxy` environment variables
  * If you are using environment variables for your proxy configuration, you can also define a `no_proxy` environment variable as a comma-separated list of domains that should not be proxied
  * Use `false` to disable proxies, ignoring environment variables
  * `auth` indicates that HTTP Basic auth should be used to connect to the proxy, and supplies credentials
  * This will set a `Proxy-Authorization` header, overwriting any existing `Proxy-Authorization` custom headers you have set using `headers`
* `cancelToken: new CancelToken(function(cancel) {})`
  * Specifies a cancel token that can be used to cancel the request

## Response Schema

The response for a request contains the following information.

* `data: object`
  * The response that was provided by the server
* `status: number`
  * The HTTP status code from the server response
* `statusText: string`
  * The HTTP status message from the server response
* `headers: object`
  * The headers that the server responded with
  * All header names are lower cased
* `config: object`
  * The config that was provided to `axios` for the request
* `request: object`
  * The request that generated this response
  * It is the last ClientRequest instance in Node.js (in redirects) and an XMLHttpRequest instance in the browser

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
# irctc-api
A package built on top of IRCTC Website APIs to book train tickets, managing user profile faster and simpler. Currently this package only works on NodeJs environment and we were not recommending this to use on browser or any other Javascript environment.

[![NPM Downloads](https://img.shields.io/npm/dw/irctc-api)](https://www.npmjs.com/package/irctc-api)
[![Node Current](https://img.shields.io/node/v/irctc-api)](https://www.npmjs.com/package/irctc-api)
[![Contributors](https://img.shields.io/github/contributors/suryavaddiraju/irctc-api.svg)](https://github.com/suryavaddiraju/irctc-api/graphs/contributors)
[![GitHub License](https://img.shields.io/github/license/suryavaddiraju/irctc-api)](http://www.apache.org/licenses/LICENSE-2.0)
[![NPM Version](https://img.shields.io/npm/v/irctc-api)](https://www.npmjs.com/package/irctc-api)
[![GitHub Issues or Pull Requests](https://img.shields.io/github/issues/suryavaddiraju/irctc-api)](https://github.com/suryavaddiraju/irctc-api/issues)
[![GitHub last commit](https://img.shields.io/github/last-commit/suryavaddiraju/irctc-api)](https://github.com/suryavaddiraju/irctc-api)
[![GitHub Actions Workflow Status](https://img.shields.io/github/actions/workflow/status/suryavaddiraju/irctc-api/node.js.yml)](https://github.com/suryavaddiraju/irctc-api/actions/workflows/node.js.yml)

## Useful Links

<a href="https://github.com/suryavaddiraju/irctc-api"><img src="https://github.githubassets.com/assets/GitHub-Mark-ea2971cee799.png" alt="GitHub Logo" width="50" height="50"/></a> <a href="https://www.npmjs.com/package/irctc-api"><img src="https://upload.wikimedia.org/wikipedia/commons/d/db/Npm-logo.svg" alt="npm Logo" width="50" height="50"/></a> <a href="https://dev.vaddiraju.in/irctc-api/api_reference"><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/d/d2/Read-the-docs.png/330px-Read-the-docs.png" alt="Documentation Logo" width="50" height="50"/></a>

## Installing

To install the this package, simply type i or install irctc-api using the node package manager

```shell
npm install irctc-api
```

## Prerequisite

This Package uses [viu](https://github.com/atanunq/viu), A rust module uses iterm image protocol for displaying images within System Terminal.

We use that for displaying captcha images on command line for login and bookings as to make your booking flow in a seamless way.

Hence you are required to download the viu executable file related to your OS and Processor Architecture from the [viu release Assets](https://github.com/atanunq/viu/releases/latest) then add the folder where the `viu` is stored to your environment variables.

Remeber to add the folder path and not the viu.exe file path in your environment variables.


### Notes

- Currently this project is designed to accept only UPI Collect request as payment option and other payment modes are not supported as of now. When the payment request is initiated, The command line will display the payment request details such that you need to complete the payment from your UPI mobile App.

- We request to verify whether viu is working or not by giving the below command

```shell
viu example.jpeg -t
```

### Import

This Package exports a class named `IRCTC` which contains three functions.

- book
- last_transaction
- pnr_status

To send a request, you only need to import the `IRCTC`.

```js
// ES5 example
const { IRCTC } = require("irctc-api");
```

```js
// ES6+ example
import { IRCTC } from "irctc-api";
```
### Examples

The Code Examples are hosted at [Github Repo - suryavaddiraju/irctc-api](https://github.com/suryavaddiraju/irctc-api/tree/main/examples)

### Usage

To send a request, you:

- Initiate IRCTC class
- Call available function operation on class with input as javascript object.

```js
// a client can be shared by different commands. But it is currently in development untill then use client seperately.
const client = new IRCTC();

const params = {
  /** input parameters */
};
const command = client.book(params);
```

#### Async/await

We recommend using [await](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/await)
operator to wait for the promise returned by send operation as follows:

```js
// async/await.
try {
  const data = await client.book(params);
  // process data.
} catch (error) {
  // error handling.
} finally {
  // finally.
}
```

Async-await is clean, concise, intuitive, easy to debug and has better error handling
as compared to using Promise chains or callbacks.

## Getting Help

Please use these community resources for getting help.
We use the [GitHub issues](https://github.com/suryavaddiraju/irctc-api/issues) for tracking bugs and feature requests, but have limited bandwidth to address them.

- Visit [API Reference](https://dev.vaddiraju.in/irctc-api/api_reference).

## Contributing

Any modifications will be overwritten the next time the `irctc-api` package is updated. To contribute to the package you can check our [contribution](https://dev.vaddiraju.in/irctc-api/contribution) page.

## License

This package is distributed under the
[Apache License, Version 2.0](http://www.apache.org/licenses/LICENSE-2.0),
see LICENSE for more information.

## Client Commands (Operations List)

<details>
<summary>
book
</summary>
<a href="https://dev.vaddiraju.in/irctc-api/api_reference#book">Command API Reference</a> / <a href="https://dev.vaddiraju.in/irctc-api/api_reference#book_input">Input</a> / <a href="https://dev.vaddiraju.in/irctc-api/api_reference#book_output">Output</a>
</details>
<details>
<summary>
last_transaction
</summary>
<a href="https://dev.vaddiraju.in/irctc-api/api_reference#last_transaction">Command API Reference</a> / <a href="https://dev.vaddiraju.in/irctc-api/api_reference#last_transaction_input">Input</a> / <a href="https://dev.vaddiraju.in/irctc-api/api_reference#last_transaction_output">Output</a>
</details>
<details>
<summary>
pnr_status
</summary>
<a href="https://dev.vaddiraju.in/irctc-api/api_reference#pnr_status">Command API Reference</a> / <a href="https://dev.vaddiraju.in/irctc-api/api_reference#pnr_status_input">Input</a> / <a href="https://dev.vaddiraju.in/irctc-api/api_reference#pnr_status_output">Output</a>
</details>

## Copyright

All Rights Reserved. &copy; Vaddiraju Surya Teja, 2024

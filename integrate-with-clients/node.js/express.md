# Express

## Add Supergood as a dependency

```bash
npm install supergood@latest
```

## Initialize Supergood as early in your app as possible

```typescript
import express from "express";
import Supergood from "supergood"

// or using CommonJS
// const express = require('express');
// const Supergood = require('supergood');

const app = express();

Supergood.init()

// All controllers should live here
app.get("/", function rootHandler(req, res) {
  res.end("Hello world!");
});

app.listen(3000);
```

**Environment variables**

Set the environment variables `SUPERGOOD_CLIENT_ID` and `SUPERGOOD_CLIENT_SECRET` using the API keys generated in the [getting started instructions](../../getting-started.md).

**Passing keys**

You can also pass the API keys in manually without setting environment variables.

Replace `<CLIENT_ID>` and `<CLIENT_SECRET>` with the API keys you generated in the [getting started instructions](../../getting-started.md).

```typescript
const Supergood = require('supergood')

Supergood.init({ clientId: <CLIENT_ID>, clientSecret: <CLIENT_SECRET> })
```

## Links

* [Supergood npm package](https://www.npmjs.com/package/supergood)
* [Supergood-js Source Code](https://github.com/supergoodsystems/supergood-js)
* [Supergood Docs](https://docs.supergood.ai)

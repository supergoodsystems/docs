---
description: Install Supergood as Middleware for your NestJS application.
---

# Setup for NestJS on Lambda

## Install the Supergood library

```bash
npm install supergood@latest
```

## Initialize the Supergood library as middleware

Create new middleware as `supergood.middleware.ts` or add to existing middleware. Setting `useRemoteConfig: true` will introduce an additional async call on Lambda start, and will allow certain Supergood features to be available such as fine-grained redaction and on-premise schema validation.&#x20;

This middleware flushes the Supergood cache _after_ your response is returned to the client, so it will not slow down your lambda function.

```
import { Injectable, NestMiddleware } from '@nestjs/common';
import { Request, Response, NextFunction } from 'express';

@Injectable()
export class SupergoodMiddleware implements NestMiddleware {
  async use(req: Request, res: Response, next: NextFunction) {
    const Supergood = require('supergood');
    Supergood.init({
      clientId: process.env.SUPERGOOD_CLIENT_ID,
      clientSecret: process.env.SUPERGOOD_CLIENT_SECRET,
      config: {
        useRemoteConfig: false,
      },
    });

    res.on('finish', async () => {
      await Supergood.close();
    });

    next();
  }
}
```

## Add the Supergood middleware

Inside of `app.module.ts`&#x20;

Add the Supergood middleware to any route containing API calls you wish to track. This example applies Supergood middleware to all routes.

```
export class AppModule implements NestModule {
  configure(consumer: MiddlewareConsumer) {
    consumer.apply(SupergoodMiddleware).forRoutes('*');
  }
}
```



## Example Repository

Here is an example repository of Supergood running on a NestJS application deployed on Lambda.

[https://github.com/supergoodsystems/nestjs-aws-lambda-example](https://github.com/supergoodsystems/nestjs-aws-lambda-example)

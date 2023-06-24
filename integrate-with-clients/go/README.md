# Go

## **Add Supergood as a dependency**

```go
import (
    supergood "github.com/supergoodsystems/supergood-go"
)
```

## **Initialize Supergood as early in your app as possible**

Remember to Set the default http client to the default Supergood client to begin monitoring your calls.&#x20;

```go
sg, err := supergood.New(&supergood.Options{RecordRequestBody: true})
if err == nil {
	http.DefaultClient = sg.DefaultClient
}
```

## **Environment Variables**

Set the environment variables `SUPERGOOD_CLIENT_ID` and `SUPERGOOD_CLIENT_SECRET` using the API keys generated in the [getting started instructions](../../getting-started.md).

```go
sg, err := supergood.New(&supergood.Options{RecordRequestBody: true, ClientId: <CLIENT_ID>, ClientSecret: <CLIENT_SECRET>})
if err == nil {
	http.DefaultClient = sg.DefaultClient
}
```

## Passing Keys

You can also pass the API keys in manually without setting environment variables.

Replace `<CLIENT_ID>` and `<CLIENT_SECRET>` with the API keys you generated in the [getting started instructions](../../getting-started.md).

### Links

* [Supergood-go Source Code](https://github.com/supergoodsystems/supergood-go)
* [Supergood-go example integration](https://github.com/supergoodsystems/plaid-go)

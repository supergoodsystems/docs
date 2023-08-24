# Go

The Supergood Go client connects Supergood to your Go application. Follow these steps to integrate with the Go client.

## **1. Add Supergood as a dependency**

```go
import (
    supergood "github.com/supergoodsystems/supergood-go"
)
```

## **2. Initialize Supergood as early in your app as possible**

Set the default HTTP client to the default Supergood client to begin monitoring your calls.&#x20;

```go
sg, err := supergood.New(&supergood.Options{RecordRequestBody: true})
if err == nil {
	http.DefaultClient = sg.DefaultClient
}
```

## **3. Set API Keys**

**Environment variables**

Set the environment variables `SUPERGOOD_CLIENT_ID` and `SUPERGOOD_CLIENT_SECRET` using the API keys generated in the [getting started instructions](../../getting-started.md).

**Passing keys**

You can alternatively pass the API keys in manually without setting environment variables.

Replace `<CLIENT_ID>` and `<CLIENT_SECRET>` with the API keys you generated in the [getting started instructions](../../getting-started.md).

```go
sg, err := supergood.New(&supergood.Options{RecordRequestBody: true, ClientId: <CLIENT_ID>, ClientSecret: <CLIENT_SECRET>})
if err == nil {
	http.DefaultClient = sg.DefaultClient
}
```

## 3. Monitor your API calls

You're all set to use Supergood!

Head back to your [dashboard](https://dashboard.supergood.ai) to start monitoring your API calls and receiving reports.

## Links

* [Supergood-go Source Code](https://github.com/supergoodsystems/supergood-go)
* [Supergood-go example integration](https://github.com/supergoodsystems/plaid-go)

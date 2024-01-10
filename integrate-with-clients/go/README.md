# Go

The Supergood Go client connects Supergood to your Go application. Follow these steps to integrate with the Go client.

## **1. Add Supergood as a dependency**

```go
import (
    supergood "github.com/supergoodsystems/supergood-go"
)
```

## **2. Create your API keys**&#x20;

**Environment variables**

Create your `SUPERGOOD_CLIENT_ID` and `SUPERGOOD_CLIENT_SECRET` credentials which can be found by following the [getting started instructions](../../getting-started.md).

## **3. Initialize Supergood as early in your app as possible**

Set the default HTTP client to the default Supergood client to begin monitoring your calls.

```go
sg, err := supergood.New(&supergood.Options{
	ClientID:     os.Getenv("SUPERGOOD_CLIENT_ID"),
	ClientSecret: os.Getenv("SUPERGOOD_CLIENT_SECRET"),
	ServiceName:  "My-Supergood-Service",
})

if err == nil {
	http.DefaultClient = sg.DefaultClient
}
```

The ClientID and ClientSecret above are instantiated explicitly.  If you do not provide them in the constructor, the Supergood Client will attempt to read them from environment variables `SUPERGOOD_CLIENT_ID` and `SUPERGOOD_CLIENT_SECRET`.

## 3. Monitor your API calls

You're all set to use Supergood!

Head back to your [dashboard](https://dashboard.supergood.ai) to start monitoring your API calls and receiving reports.

## 4. Redacting Sensitive Keys

There may be some sensitive key material that you would like to redact on the client before it is ingested by Supergood. This can be done directly in the [Supergood Dashboard ](https://dashboard.supergood.ai/endpoints)and opening up the `keys redacted` pane. Redacted fields can also be explicitly set in the Go client constructor. More details on how can be found [here](https://docs.supergood.ai/integrate-with-clients/go/configuration).

## Links

* [Supergood-go Source Code](https://github.com/supergoodsystems/supergood-go)
* [Supergood-go example integration](https://github.com/supergoodsystems/plaid-go)

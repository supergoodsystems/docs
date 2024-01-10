# Configuration

[Go Client Instantiation](https://docs.supergood.ai/integrate-with-clients/go)

This page describes possible parameter configurations. Pass any desired configuration to the `new` function.

### ClientID

_Default: ""_

`ClientID` can be found on https://dashboard.supergood.ai/api-keys. It defaults to the `SUPERGOOD_CLIENT_ID` environment variable if not provided.

### ClientSecret

`ClientSecret` can be found on https://dashboard.supergood.ai/api-keys. It defaults to the `SUPERGOOD_CLIENT_SECRET` environment variable if not provided.



{% hint style="warning" %}
The following parameters in this guide can bee configured directly in the Supergood dashboard without having to explicitly set it in the Go client constructor. [https://dashboard.supergood.ai/endpoints](https://dashboard.supergood.ai/endpoints)
{% endhint %}

### RedactRequestBodyKeys

`RedactRequestBodyKeys` is a map of top level domains to a list of key paths within the request body of values to be redacted.&#x20;

```go
RedactRequestBodyKeys: map[string][]string{
	"plaid.com": []string{"path.to.redacted.[].field"},
},
```

### RedactRequestHeaderKeys

`RedactRequestHeaderKeys` is a map of top level domains to a list of keys within the request headers of values to be redacted

```go
RedactRequestBodyKeys: map[string][]string{
	"plaid.com": []string{"client-id", "client-secret},
},
```

### RedactResponseBodyKeys

`RedactResponseBodyKeys` is a map of top level domains to a list of key paths within the response body of values to be redacted.

```go
RedactResponseBodyKeys: map[string][]string{
	"plaid.com": []string{"path.to.redacted.[].field"},
},
```

### RedactResponseHeaderKeys

`RedactResponseHeaderKeys` is a map of top level domains to a list of keys within the response headers of values to be redacted

```go
RedactResponseBodyKeys: map[string][]string{
	"plaid.com": []string{"client-id", "client-secret},
},
```

### **AllowedDomains**

_Default: \[]_

List of strings to match against the host of the request URL in order to determine whether or not to log the request to Supergood, based on the domain. Case sensitive. By default, requests from all domains are logged.&#x20;

### **FlushInterval**

_Default: 1 \* time.Second_

`FlushInterval` configures how frequently Supergood sends batches of logs to the API. This parameter cannot be set directly in the Supergood dashboard and must be configured on the client.

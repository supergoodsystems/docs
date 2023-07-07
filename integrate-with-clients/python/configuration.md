# Configuration

Optional configuration may be passed to the `Client`, the parameters may be configured as follows:

## flushInterval

_Default:_ _1000_

Time in milliseconds between cache flushes. Smaller intervals are advised for larger traffic volumes. Represented as an integer.

**Example:**

```
Client(config={ flushInterval: 1000 })
```

## includedKeys

_Default: \[]_&#x20;

An array of keys in the string path dot format like `path.to.key` that will not be redacted on the client side before being sent to the server.

**Example**:

Below will NOT redact the value stored at the key `authorization_token` located on the either on the body of the request or the body of the response.

```
Client(config={ includedKeys: ['authorization_token'] })
```

## ignoredDomains

_Default: \[]_

An array of domains to ignore when caching traffic.

In the format of:`<domain-name>.<top-level-domain>`

**Example**:

```
Client(config={ ignoredDomains: ['amazon.com', 'google.com'] })
```


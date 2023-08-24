# Configuration

This page describes possible parameter configurations. Pass any desired configuration to the `Client`.

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

This example will NOT redact the value stored at the key `authorization_token` located on either the body of the request or the body of the response.

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


# Configuration

Optional configuration may be passed to the `init` function, the parameters may be configured as follows:

## flushInterval

_Default:_ _1000_

Time in milliseconds between cache flushes. Smaller intervals are advised for larger traffic volumes. Represented as an integer.

**Example:**

```typescript
Supergood.init({ config: { flushInterval: 1000 }})
```

## keysToHash

_Default: \[]_&#x20;

An array of keys in the string path dot format like `path.to.key` that will take the SHA1 hash of the actual value instead of the returned value. This masks sensitive information that can not live outside of your server.

Keys to hash must start with `request` or `response` and the second key must be `body` or `headers`. After that, the path can be arbitrarily long.

**Example**:

`request.body.authorization_token` will hash the value stored at the key `authorization_token` located on the body of the request.

```typescript
Supergood.init({ config: keysToHash: ['request.body.authorization_token'] }})
```

## allowedDomains

_Default: \[]_

An array of domains to ignore when caching traffic. Will match on partial domains and takes precedence over domains specified in ignoredDomains.

**Example**:

```typescript
Supergood.init({ config: { allowedDomains: ['amazon.com', 'google'] }})
```

## ignoredDomains

_Default: \[]_

An array of domains to ignore when caching traffic.

In the format of:`<domain-name>.<top-level-domain>`

**Example**:

```typescript
Supergood.init({ config: { ignoredDomains: ['amazon.com', 'google.com'] }})
```


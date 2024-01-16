# Configuration

This page describes possible parameter configurations. Pass any desired configuration to the `init` function.

## flushInterval

_Default:_ _1000_

Time in milliseconds between cache flushes. Smaller intervals are advised for larger traffic volumes. Represented as an integer.

**Example:**

```
Supergood.init({ flushInterval: 1000 })
```

## forceRedactAll

_Default: true_

A flag, by default set to "true" will redact all the payload values for the request body, request headers, response body and response headers and send only the metadata of the payload value to the Supergood servers.

The metadata consists only of the data type and data length.&#x20;

If this flag is set to "false", Supergood will attempt to redact values that it deems to represent sensitive keys. All sensitive keys are configurable in the Supergood Dashboard.

**Example**:

```
Supergood.init({ forceRedactAll: false })
```

## ignoredDomains

_Default: \[]_

An array of domains to ignore when caching traffic.

Will pattern match on the hostname, as long as the input string is contained in the hostname.

**Example**:

```
Supergood.init({ ignoredDomains: ['amazon.com', 'google.com'] })
```

## allowedDomains

_Default: \[]_

An array of domains to only allow when caching traffic, overrides any `ignoredDomains` set.

Will pattern match on the hostname, as long as the input string is contained in the hostname.

**Example**:

```
Supergood.init({ allowedDomains: ['amazon.com', 'google.com'] })
```

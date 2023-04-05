# Understand Your Configuration

Upon initialization, each Supergood client fetches a pre-defined configuration from the Supergood server. The configuration supports the following options.

## Flush interval

_Default:_ 1000ms

Time in milliseconds between cache flushes. Smaller intervals are advised for larger traffic volumes.

## Keys to hash

_Default: None_

A list of keys in the string path dot format like `path.to.key` that will take the SHA1 hash of the actual value instead of the returned value. This masks sensitive information that can not live outside of your server.

Keys to hash must start with `request` or `response` and the second key must be `body` or `headers`. After that, the path can be arbitrarily long.

**Example**:

`request.body.authorization_token` will hash the value stored at the key `authorization_token` located on the body of the request.

## Ignored domains

_Default: None_

A list of domains to ignore when caching traffic.

In the format of:`<domain-nam>.<top-level-domain>`

**Examples**:

* `supergood.ai`
* `amazon.com`

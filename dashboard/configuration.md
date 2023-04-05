# Configuration

Upon initialization, each Supergood Client will fetch a pre-defined configuration from the Supergood Server. The configuration supports the following options.

### Flush Interval

_Default:_ 1000ms

Time in milliseconds between cache flushes, smaller intervals are advised for larger volumes of traffic.

### Keys to Hash

_Default: None_

A list of keys in the string path dot format like path.to.key that will take the SHA1 hash of the actual value instead of the returned value. This is used to mask sensitive information that can not live outside of your server.

Keys to hash must start with `request` or `response` and the second key must be `body` or `headers` , after that the path can be arbitrarily long.&#x20;

Example:

`request.body.authorization_token` will hash the value stored at the key `authorization_token` located on the body of the request.

### Ignored Domains

_Default: None_

A list of domains to ignore when caching traffic.

In the format of:`<domain-nam>.<top-level-domain>` \
\
Examples:

* `supergood.ai`
* `amazon.com`

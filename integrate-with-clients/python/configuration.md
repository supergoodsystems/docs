# Configuration

This page describes possible parameter configurations. Pass any desired configuration to the `Client`.

## flushInterval

_Default:_ _1000_

Time in milliseconds between cache flushes. Smaller intervals are advised for larger traffic volumes. Represented as an integer.

**Example:**

```python
Client(config={ flushInterval: 1000 })
```

## configInterval

_Default: 10000_

Time in milliseconds between fetching the remote config from the Supergood wizard. Represented as an integer.

**Example:**

```
Client(config={ configInterval: 5000 })
```

## ignoredDomains

_Default: \[]_

An array of domains to ignore when caching traffic.

In the format of:`<domain-name>.<top-level-domain>`

**Example**:

```python
Client(config={ ignoredDomains: ['amazon.com', 'google.com', 'bbc.co.uk'] })
```

## ignoreRedaction

_Default: False_

Boolean to override the redaction of all values.

**Example:**

```python
Client(config={ ignoreRedaction: True })
```


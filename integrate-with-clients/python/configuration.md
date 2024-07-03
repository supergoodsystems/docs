# Configuration

This page describes possible parameter configurations. Pass any desired configuration to the `Client`.

## flushInterval

_Default:_ _1000_

Time in milliseconds between cache flushes. Smaller intervals are advised for larger traffic volumes. Represented as an integer.

**Example:**

```python
Client(config={ "flushInterval": 1000 })
```

## configInterval

_Default: 10000_

Time in milliseconds between fetching the remote config from the Supergood wizard. Represented as an integer.

**Example:**

```python
Client(config={ "configInterval": 5000 })
```

## ignoredDomains

_Default: \[]_

An array of domains to ignore when caching traffic.

In the format of:`<domain-name>.<top-level-domain>`

**Example**:

```python
Client(config={ ignoredDomains: ['amazon.com', 'google.com', 'bbc.co.uk'] })
```

## forceRedactAll

_Default: False_

Redacts all leaf values from all payloads. Ignores allowed sensitive keys

**Example:**

```python
Client(config={ "forceRedactAll": True })
```

## log{Request|Response}{Headers|Body}

_Defaults: True_

4 Boolean parameters that allow for more fine-tuned control over what gets removed from the payload. Setting any to false will remove values from the respective object.

**Examples:**

```python
# Example 1: Log everything except responseHeaders
Client(config={ "logResponseHeaders": False })
# Example 2: Only log requests
Client(config={ "logResponseHeaders": False, "logResponseBody": False}
```

## ignoreRedaction

_Default: False_

Boolean to override the redaction of all values.

**Example:**

```python
Client(config={ "ignoreRedaction": True })
```

## useRemoteConfig

_Default: True_

Can be set to False to ignore reading from remote config. Generally only used in a few serverless applications.

**Example:**

```python
Client(config={ "useRemoteConfig": False })
```

## runThreads

_Default: True_

Can be set to False to stop running background threads. Generally only used in a few serverless applications.

**Example:**

```python
Client(config={ "runThreads": False })
```

## redactByDefault

_Default: False_

Redacts full payloads excepting for any keys explicitly marked as `Allow` via the Supergood UI. Used for more data-sensitive flows that want to allow-list as opposed to disallow-list keys.

**Example:**

```python
Client(config={ "redactByDefault": False })
```

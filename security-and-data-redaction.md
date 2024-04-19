# Security & Data Redaction

Supergood ensures that sensitive data will never leave your server, unless you explicitly allow it. In order to accomplish this, the following configuration options are available on the Supergood clients.

In order for the Supergood client to know which fields to redact, a remote configuration fetch is performed upon initialization and once every few seconds after that. Please note that if the parameter `useRemoteConfig` is set to false, and either of the following two flags are set, all fields will always be redacted.

## forceRedactAll

_This configuration flag is available in all clients: Ruby, NodeJS, Python and GoLang._

```javascript
Supergood.init({
  clientId: process.env.SUPERGOOD_CLIENT_ID,
  clientSecret: process.env.SUPERGOOD_CLIENT_SECRET,
  config: {
    forceRedactAll: true
  },
})
```

This flag will force every value to be nulled out and replaced only by it's metadata which includes the key's name and path, data type, and size. If this flag is set, all values will be nulled out regardless of what is configured in the Supergood Dashboard.

As an example,

This input:

```
{ 
  name: 'Alex',
  address: {
    street_number: 123,
    street_address: 'Fake Street',
    city: 'San Francisco',
  },
  tags: ['developer', 'engineer', documentation']
}
```

Will be nulled out, and sent to Supergood as:&#x20;

```
{ 
  name: 'string:4',
  address: {
    street_number: 'integer:3',
    street_address: 'string:11',
    city: 'string:13',
  },
  tags: ['string:9', 'string:8', 'string:13']
}
```

## redactByDefault

_This configuration flag is only available in the NodeJS and GoLang clients._

```javascript
Supergood.init({
  clientId: process.env.SUPERGOOD_CLIENT_ID,
  clientSecret: process.env.SUPERGOOD_CLIENT_SECRET,
  config: {
    redactByDefault: true
  },
})
```

This flag behaves similarly to `forceRedactAll` as it nulls out all values, but it will respect the sensitive keys specified by the remote configuration. If no remote configuration is available, it redacts the values by default.&#x20;

In order to configure the sensitive keys to redact:

1. Head to https://dashboard.supergood.ai
2. Click on the "Endpoints" tab on the left hand side.
3. Use the filters at the top to find the Project and Endpoint you wish to configure.
4. Click on the "Sensitive Keys" button on the row, and the panel will come out of the right side of the screen.
5. Scroll down to the payload view, and click on values you wish to mark as sensitive.&#x20;
6. Click save when you're done.

Depending on the cadence of your configuration fetch, you might need to wait up to 10 seconds for the changes to be reflected in the client.

<figure><img src=".gitbook/assets/sensitive-key-toggle.gif" alt=""><figcaption></figcaption></figure>


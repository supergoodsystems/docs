# How it Works

Supergood is a lightweight client and monitoring service that ingests all your company's external API calls for cost and performance analysis as well as error reporting and alerting. It is currently available for [Node.js](installing-clients/node.js.md), [Python](installing-clients/python.md), [Ruby](installing-clients/ruby.md) and [Go](installing-clients/go-coming-soon.md) codebases supporting most all http clients for each language.

The Supergood client quietly sits inside of your codebase and passively monitors all outbound HTTP requests. No proxy server required.&#x20;

Upon installation, the client will attach itself to whichever HTTP library you are using for the given language and efficiently cache all outbound requests and responses you make. At a set interval that you define, these calls are shipped off to the Supergood Dashboard for analysis, reporting and alerting.

## Hashing Sensitive Data

While the Supergood database is encrypted, there potentially may be data embedded within these API calls that you're unwilling to send off to a remote server. As such, you are able to configure on a key level at any depth in the JSON, which values needed to be obfuscated on the headers and/or body. Optionally, you're able to hash the entire headers or body if desired.

Hashing is done on your server and is configurable any time in the Supergood Dashboard.

Read more in the [Configuration](dashboard/configuration.md) Section.




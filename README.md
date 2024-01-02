# How It Works

**Supergood** is a lightweight client and monitoring service that ingests all your company's external API calls for cost and performance analysis, error reporting, and alerting. Supergood is currently available for [Node.js](integrate-with-clients/node.js), [Python](installing-clients/python.md), [Ruby](integrate-with-clients/ruby/), and [Go](installing-clients/go-coming-soon.md) codebases, supporting all HTTP clients for each language.

The Supergood client quietly sits inside of your codebase and passively monitors all outbound HTTP requests. No proxy server required.

Upon installation, the client will attach itself to whichever HTTP library you're using for the given language and efficiently cache all outbound requests and responses you make. At a set interval that you define, these calls are sent to the Supergood Dashboard for analysis, reporting, and alerting.

## Redacting sensitive data

While the Supergood database is encrypted, there could be data embedded within these API calls that you're unwilling to send to a remote server. As such, you can configure on a key level, at any depth in the JSON, which values need to be obfuscated on the headers and/or body. You can hash the entire headers or body if desired.

Redacting is done on your server and is configurable at any time in the Supergood Dashboard.

Learn more about redacting in the [Configuration](broken-reference/) section.

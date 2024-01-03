# How It Works

**Supergood** is a lightweight client and monitoring service that ingests all your company's external API calls for cost and performance analysis, error reporting, and alerting. The Supergood client quietly sits inside of your codebase and passively monitors all outbound HTTP requests. No proxy server required.

Supergood is currently available for [Node.js](integrate-with-clients/node.js), [Python](installing-clients/python.md), [Ruby](integrate-with-clients/ruby/), and [Go](installing-clients/go-coming-soon.md) backends, supporting all HTTP clients for each language.

Upon initialization, the client will attach itself to the native HTTP library for the given language and cache outbound requests and responses. At a set interval, these payloads are sent to the Supergood Dashboard for analysis, reporting, and alerting.

## Configuration

The **Supergood Dashboard** enables remote configuration for the clients installed on your server. In addition to serving as a control center for every external API running through your system, the dashboard also enables users to exclude specific APIs from being monitored and modify the list of sensitive keys Supergood has automatically identified and redacted.

## Redacting sensitive data

In order to ensure that sensitive data never leaves your server, users can configure on a key level, at any depth in the JSON, which values need to be redacted on the headers and/or body.

Redacting is done on your server and is configurable at any time in the **Supergood Dashboard.**

Before redacting, metadata from these values including Data Type and Data Length are extracted in order for Supergood to perform continuous anomaly detection on your providers. These redacted values are completely removed from the Supergood server and show up as **"\<supergood-redacted>"** when inspecting payloads on the **Supergood Dashboard**.

## Compliance

Supergood is SOC2 Type I compliant and is actively undergoing an audit for SOC2 Type II. A full report is available upon request by reaching out to security@supergood.ai .

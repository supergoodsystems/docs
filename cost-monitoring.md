---
description: >-
  This feature is currently only available in the GoLang client v0.3.4 and
  later.
---

# Cost Monitoring

## Rate Limiting by Cost Thresholds

Users are able to set a daily cost limit per project and per API endpoint. If the cost of API calls exceeds a daily dollar amount, the Supergood client will automatically block outbound API calls and return a 429 error with the message: "Blocked by Supergood: Too many requests".

The daily limit is reset automatically at midnight UTC.

In order to configure the cost and thresholds:

1. Navigate to "Endpoints" on the left hand side of the page.
2. Select the relevant "Project" and "Vendor" using the selectors at the top of the page.
3. Click on the "configure" text under the "Price" column to open up the endpoint configuration side panel.
4. Navigate to the "Price per call / Quotas" tab
5. Set usage type to be "Price per call" , the dollar amount per call, the threshold you want to alert and/or rate limit on when exceeded and the relevant action when exceeded.
6. Click the "Save" button to start enforcing thresholds.

If this alert fires, you can go back to this page to increase the threshold or set "On Cost Threshold Exceeded" to "No action" to disable it.

The threshold check runs every 2 minutes, at which point the next refresh of your remote config (default 10 seconds) should trigger the Supergood block.

<figure><img src=".gitbook/assets/cost-threshold.gif" alt=""><figcaption><p>Video demonstration on configuring the cost limit thresholds.</p></figcaption></figure>

---
description: Capture API calls with more fine grained control.
---

# Explicit Capture

If you do not wish to install the Supergood library to capture everything globally, the Node library makes it easy to set up explicit capture windows, in two different ways.

Note that neither method will perform an explicit flush, so if you're running on a serverless system such as lambda, we advise you to execute a `Supergood.close()` after the lambda returns a value to the client.&#x20;

More instructions on getting setup for Lambda here: [Setup for Lambda](broken-reference)

## withCapture

Instead of calling `Supergood.init` globally, you can wrap all of the async calls you wish to track using `withCapture.`Pass in the configuration parameters you would pass into init, but into withCapture.

```
await Supergood.withCapture(<config-params>, async () => {
  await asyncCallToTrack();
  await anotherAsyncCallToTrack();
});

await asyncCallNotBeingTracked();
```

## startCapture & stopCapture

Similar to withCapture, you can begin and end a capture span by calling startCapture and stopCapture on a code path. These functions will **not** make a remote call if `useRemoteConfig` is set to false in your configuration, in which awaiting a `startCapture` is unnecessary.

```
Supergood.startCapture(<config-params>) // await is not necessary if useRemoteConfig is set to 'false'

await asyncCallToTrack();
await anotherAsyncCallToTrack();

Supergood.stopCapture();

await asyncCallNotBeingTracked();
```

`withCapture` , `startCapture` and `stopCapture` all use [AsyncLocalStorage](https://nodejs.org/api/async\_context.html) under the hood.

## Objective

Use this API to register a `resource://` URL, which is needed to load a custom JSM file defined in an Experiment. This API also takes care of flushing the JSM cache and unloading any loaded JSM which is using the registered `resource://` url.

This API is used in the following example: https://github.com/thundernest/sample-extensions/tree/master/experiment

## Usage

A background script could look like the following:

```
async function main() {
  // Define the resource URL for the modules folder, which is part of our Experiment.
  await browser.ResourceUrl.register("exampleapi","modules/");

 ...
}

main();

```

The files in the `modules/*` folder will be accessible via `resource://exampleapi/*`.

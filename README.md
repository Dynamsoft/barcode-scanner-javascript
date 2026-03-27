# barcode-scanner-javascript-dev

A JavaScript wrapper around Dynamsoft Barcode Reader JavaScript Edition, focused on easier adoption with a minimal, ready-to-use API.

## Why This Repo Exists

The official Dynamsoft Barcode Reader JavaScript Edition is powerful, but teams often need to wire together setup details before they can ship a smooth scanning flow. This project aims to provide a thinner, friendlier layer on top of the core SDK so developers can get from install to first scan faster.

The wrapper is intended to help with:

- faster onboarding for new projects
- a smaller surface area for common barcode-scanning use cases
- sensible defaults for camera-based scanning in the browser
- easier integration into demos, prototypes, and production apps

## Goals

- Keep the API small and easy to understand
- Cover the most common browser scanning workflows first
- Stay close to Dynamsoft Barcode Reader capabilities instead of hiding them completely
- Make adoption simple for teams that want a practical default setup

## Planned Scope

This repository is currently in the early setup stage. The intended package will focus on:

- initializing the Dynamsoft barcode engine with minimal configuration
- starting and stopping live camera scanning
- decoding from image files
- returning normalized, easy-to-consume scan results
- exposing escape hatches for advanced Dynamsoft configuration when needed

## Intended Developer Experience

The target experience is something along these lines:

```js
import { createBarcodeScanner } from "barcode-scanner-javascript";

const scanner = await createBarcodeScanner({
  license: "YOUR_LICENSE_KEY",
  container: "#scanner",
});

await scanner.start();

scanner.on("scan", (result) => {
  console.log(result.text, result.format);
});
```

And for image decoding:

```js
const result = await scanner.decodeFile(file);
console.log(result);
```

The exact API may evolve as implementation takes shape, but the design direction is intentionally minimal.

## Project Structure

```text
src/       Source code for the wrapper
samples/   Example integrations and demo apps
docs/      Additional documentation and design notes
```

## Status

This project is under active development. The repository structure is in place, and the next step is implementing the core wrapper API and sample applications.

## Roadmap

- define the public API for scanner creation and lifecycle
- add browser-based camera scanning support
- add file/image decoding helpers
- add sample apps for plain JavaScript and framework usage
- document configuration, events, and result objects
- add tests and release packaging

## Who This Is For

This wrapper is a good fit for teams that:

- want to use Dynamsoft Barcode Reader JavaScript Edition
- prefer a simpler integration layer for common cases
- need to get a scanning experience working quickly
- still want access to advanced SDK behavior when necessary

## Contributing

Contributions are welcome as the wrapper takes shape. Early feedback is especially useful around:

- API design
- result shape
- configuration defaults
- browser compatibility expectations
- sample app priorities

## License

License information for this wrapper should be added here once the package structure is finalized.

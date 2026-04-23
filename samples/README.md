# Barcode Scanner Samples

This directory contains sample applications and demonstrations for the Dynamsoft Barcode Scanner JavaScript SDK.

**[View All Live Demos](https://dynamsoft.github.io/barcode-scanner-javascript/)** - Try samples online without downloading!

## Structure

```
samples/
├── index.html              # Main navigation page - start here!
├── hello-world/            # Quick-start examples
├── scenarios/              # Real-world use case demonstrations
└── frameworks/             # Framework integration examples (coming soon)
```

## Quick Start

**Online:** Visit **[https://dynamsoft.github.io/barcode-scanner-javascript/](https://dynamsoft.github.io/barcode-scanner-javascript/)** to try all samples instantly.

**Local:** Open [index.html](index.html) in your browser to explore all available samples.

### Hello World Examples

Simple standalone examples to get started quickly:

- **[hello-world.html](hello-world/hello-world.html)** - Continuously scan multiple unique barcodes via camera
- **[scan-a-single-barcode.html](hello-world/scan-a-single-barcode.html)** - Scan one barcode and stop
- **[read-an-image.html](hello-world/read-an-image.html)** - Read barcodes from uploaded images

## Scenario Samples (17 total)

Real-world use case demonstrations organized by category:

### Workflow Examples
- **batch-inventory** - Batch scanning for inventory management
- **cart-builder** - Shopping cart with barcode scanning
- **pick-one-to-fill** - Pick correct items from multiple candidates
- **scan-and-search** - Barcode scanning with lookup functionality

### Barcode Type Focused
- **scan-qr-code** - QR code optimized scanning
- **scan-common-2D-codes** - Common 2D formats (QR, DataMatrix, PDF417)
- **scan-common-1D-and-2D** - Wide range of 1D and 2D formats
- **scan-datamatrix-code** - DataMatrix optimized
- **scan-dpm-codes** - Direct Part Mark (DPM) codes on metal/plastic
- **scan-1D-Retail** - 1D retail barcodes (EAN, UPC)
- **scan-1D-Industrial** - 1D industrial barcodes (Code 39, Code 128)

### Industry Specific
- **read-a-drivers-license** - Driver's license PDF417 reading and parsing
- **read-vin** - Vehicle Identification Number (VIN) reading
- **read-and-parse-GS1-AI** - GS1 Application Identifier parsing

### Advanced Features
- **show-result-texts-on-the-video** - Overlay barcode text on live video
- **scan-from-distance** - Distance scanning with zoom/ROI tuning
- **locate-an-item-with-barcode** - Locate items in lists/layouts

## Framework Examples (14 total)

Integration examples showing how to use BarcodeScanner in popular frameworks:

### Frontend Frameworks
- **angular** - Angular integration with TypeScript
- **react** - React integration with Vite
- **vue** - Vue 3 integration with Vite
- **next** - Next.js integration
- **nuxt** - Nuxt integration
- **svelte** - Svelte integration with Vite

### Module Systems
- **es6** - ES6 modules (CDN-based, no build process)
- **native-ts** - Native TypeScript with Rollup
- **requirejs** - RequireJS AMD modules (CDN-based)

### Desktop & Mobile
- **electron** - Electron desktop app integration
- **capacitor** - Capacitor mobile hybrid app
- **webview** - Native mobile WebView integration

### Other
- **pwa** - Progressive Web App example
- **blazor** - Blazor WebAssembly integration

Each framework sample includes a README with setup and run instructions.

## Documentation

For detailed API documentation and guides, visit:
- [API Reference](../docs/barcode-scanner-api-reference.md)
- [User Guide](../docs/user-guide.md)
- [Customization Guide](../docs/barcode-scanner-customization.md)

## Links

- [Dynamsoft Barcode Reader Documentation](https://www.dynamsoft.com/barcode-reader/docs/web/programming/javascript/)
- [GitHub Repository](https://github.com/Dynamsoft/barcode-scanner-javascript)
- [Get a License](https://www.dynamsoft.com/customer/license/trialLicense)

## Getting Started

1. Open [index.html](index.html) in your browser
2. Browse the available samples
3. Click on any sample to see it in action
4. View the source code to understand how it works
5. Adapt the code for your own use case

Most samples can be run directly in the browser without any build process!

# Dynamsoft Barcode Reader JavaScript Edition - Ready-to-Use (RTU) API

A powerful, easy-to-use JavaScript barcode scanning library for web applications. Scan barcodes from camera streams or image files with just a few lines of code.

[![npm version](https://img.shields.io/npm/v/dynamsoft-barcode-reader-bundle.svg)](https://www.npmjs.com/package/dynamsoft-barcode-reader-bundle)
[![downloads](https://img.shields.io/npm/dm/dynamsoft-barcode-reader-bundle.svg)](https://www.npmjs.com/package/dynamsoft-barcode-reader-bundle)

## Table of Contents

- [Introduction](#introduction)
- [Why Choose the JavaScript Ready-to-Use Edition](#why-choose-the-javascript-ready-to-use-edition)
- [Features](#features)
- [Supported Barcode Formats](#supported-barcode-formats)
- [Browser Support](#browser-support)
- [Installation](#installation)
- [Quick Start](#quick-start)
    - [Scan a Single Barcode via Camera](#scan-a-single-barcode-via-camera)
    - [Scan Multiple Barcodes Continuously](#scan-multiple-barcodes-continuously)
    - [Read Barcodes from an Image](#read-barcodes-from-an-image)
- [Live Demos](#live-demos)
- [Documentation](#documentation)
- [Framework Integration](#framework-integration)
- [License](#license)
- [Support & Resources](#support--resources)

## Introduction

Dynamsoft Barcode Reader JavaScript Edition (Ready-to-Use API) enables developers to integrate barcode scanning functionality into web applications with minimal effort. Built on industry-leading barcode recognition algorithms, it provides high accuracy and performance while maintaining an intuitive, developer-friendly API.

**Get scanning in under 5 minutes** with our pre-built UI and sensible defaults, or customize every aspect to match your application's requirements.

## Why Choose the JavaScript Ready-to-Use Edition

- **Zero Configuration Required** - Start scanning with a single line of code using built-in defaults
- **Pre-built Camera UI** - Professional viewfinder with scan region highlighting included out of the box
- **High Accuracy** - Industry-leading recognition algorithms with 99%+ accuracy on standard barcodes
- **Cross-Platform** - Works seamlessly across desktop and mobile browsers (Chrome, Firefox, Safari, Edge)
- **Flexible Deployment** - CDN, npm, or self-hosted options available
- **Framework Friendly** - Ready-made samples for React, Vue, Angular, Next.js, Nuxt, Svelte, and more
- **Production Ready** - Battle-tested by thousands of applications worldwide
- **Fully Customizable** - Access advanced configuration when you need precise control

## Features

- **Live Camera Scanning** - Real-time barcode detection from device cameras
- **Image File Decoding** - Read barcodes from uploaded images or files
- **Multi-Barcode Detection** - Scan multiple barcodes simultaneously with deduplication
- **Customizable UI** - Modify the built-in UI or create your own from scratch
- **Scan Region Control** - Define specific areas of the camera feed to scan
- **High Performance** - WebAssembly-powered for fast processing
- **Responsive Design** - Works on desktop and mobile devices
- **Advanced Templates** - Fine-tune recognition for challenging scenarios

## Supported Barcode Formats

**1D Barcodes:** Code 128, Code 39, Code 93, Code 11, Codabar, Interleaved 2 of 5, Industrial 2 of 5, ITF-14, EAN-8, EAN-13, UPC-A, UPC-E, MSI Code, GS1 DataBar, GS1 Composite

**2D Barcodes:** QR Code, Data Matrix, PDF417, Aztec, MaxiCode

**Postal Codes:** USPS Intelligent Mail, Postnet, Planet, Australian Post, UK Royal Mail (RM4SCC)

**Patch Code**

**[View all 50+ supported formats](https://www.dynamsoft.com/barcode-reader/barcode-types/)**

## Browser Support

| Browser | Desktop | Mobile |
| ------- | ------- | ------ |
| Chrome  | 78+     | 78+    |
| Firefox | 68+     | 68+    |
| Safari  | 14+     | 14+    |
| Edge    | 79+     | 79+    |

**[View full system requirements](https://www.dynamsoft.com/faq/barcode-reader/web/capabilities/system-requirement.html)**

## Installation

### Option 1: CDN (Fastest Setup)

```html
<script src="https://cdn.jsdelivr.net/npm/dynamsoft-barcode-reader-bundle@11.4.2001/dist/dbr.bundle.js"></script>
```

### Option 2: npm

```bash
npm install dynamsoft-barcode-reader-bundle@11.4.2001
```

### Option 3: yarn

```bash
yarn add dynamsoft-barcode-reader-bundle@11.4.2001
```

## Quick Start

### Scan a Single Barcode via Camera

**[▶ Try it on JSFiddle](https://jsfiddle.net/DynamsoftTeam/gcqjf5r7/)**

```html
<!DOCTYPE html>
<html>
	<head>
		<title>Barcode Scanner</title>
		<script src="https://cdn.jsdelivr.net/npm/dynamsoft-barcode-reader-bundle@11.4.2001/dist/dbr.bundle.js"></script>
	</head>
	<body>
		<script>
			// Instantly launch scanner with built-in 24-hour trial license
			new Dynamsoft.BarcodeScanner().launch().then((result) => {
				alert(result.barcodeResults[0].text);
			}).catch((error) => {
				console.error(error);
				alert("Error: " + error.message);
			});
		</script>
	</body>
</html>
```

### Scan Multiple Barcodes Continuously

**[▶ Try it on JSFiddle](https://jsfiddle.net/DynamsoftTeam/d6comprf/)**

```html
<!DOCTYPE html>
<html>
	<head>
		<title>Multi-Barcode Scanner</title>
		<script src="https://cdn.jsdelivr.net/npm/dynamsoft-barcode-reader-bundle@11.4.2001/dist/dbr.bundle.js"></script>
	</head>
	<body>
		<script>
			new Dynamsoft.BarcodeScanner({
				scanMode: Dynamsoft.EnumScanMode.SM_MULTI_UNIQUE,
				onUniqueBarcodeScanned: (result) => {
					console.log(`[${result.formatString}] ${result.text}`);
				},
			}).launch();
		</script>
	</body>
</html>
```

### Read Barcodes from an Image

```html
<!DOCTYPE html>
<html>
	<head>
		<title>Read from Image</title>
		<script src="https://cdn.jsdelivr.net/npm/dynamsoft-barcode-reader-bundle@11.4.2001/dist/dbr.bundle.js"></script>
	</head>
	<body>
		<input type="file" id="fileInput" accept="image/*" />
		<div id="results"></div>

		<script>
			const scanner = new Dynamsoft.BarcodeScanner();

			document
				.getElementById("fileInput")
				.addEventListener("change", async (e) => {
					const file = e.target.files[0];
					try {
						const result = await scanner.decode(file);

						document.getElementById("results").innerHTML =
							result.decodedBarcodesResult?.barcodeResultItems
								.map((item) => `${item.formatString}: ${item.text}`)
								.join("<br>") || "No barcode found";
					} catch (error) {
						console.error(error);
						document.getElementById("results").innerHTML = "Error: " + error.message;
					}
				});
		</script>
	</body>
</html>
```

## Live Demos

**[View All Live Demos](https://dynamsoft.github.io/barcode-scanner-javascript/)** - Explore interactive samples

### Hello World Samples

- [Scan Single Barcode](./samples/hello-world/scan-a-single-barcode.html)
- [Scan Multiple Barcodes](./samples/hello-world/hello-world.html)
- [Read from Image File](./samples/hello-world/read-an-image.html)

### Scenario-Based Samples

- [Batch Inventory Scanning](./samples/scenarios/batch-inventory/)
- [Shopping Cart Builder](./samples/scenarios/cart-builder/)
- [Scan QR Codes](./samples/scenarios/scan-qr-code/)
- [Read Driver's License (PDF417)](./samples/scenarios/read-a-drivers-license/)
- [Scan DPM Codes](./samples/scenarios/scan-dpm-codes/)
- [Distance Scanning with Zoom](./samples/scenarios/scan-from-distance/)

**[View all samples](./samples/)**

## Documentation

**Getting Started**

- [User Guide](./docs/user-guide.md) - Step-by-step tutorial to build your first scanner
- [API Reference](./docs/barcode-scanner-api-reference.md) - Complete API documentation
- [Customization Guide](./docs/barcode-scanner-customization.md) - Learn how to customize the scanner

**Advanced Topics**

- [Migration from v10 to v11](./docs/migrate-from-v10.md)
- [Official Documentation](https://www.dynamsoft.com/barcode-reader/docs/web/programming/javascript/)

## Framework Integration

Pre-built samples available for popular frameworks:

| Framework | Sample Link                                                     |
| --------- | --------------------------------------------------------------- |
| React     | [samples/frameworks/react](./samples/frameworks/react/)         |
| Vue 3     | [samples/frameworks/vue](./samples/frameworks/vue/)             |
| Angular   | [samples/frameworks/angular](./samples/frameworks/angular/)     |
| Next.js   | [samples/frameworks/next](./samples/frameworks/next/)           |
| Nuxt 3    | [samples/frameworks/nuxt](./samples/frameworks/nuxt/)           |
| Svelte    | [samples/frameworks/svelte](./samples/frameworks/svelte/)       |
| Electron  | [samples/frameworks/electron](./samples/frameworks/electron/)   |
| Capacitor | [samples/frameworks/capacitor](./samples/frameworks/capacitor/) |

**[View all framework samples](./samples/frameworks/)**

## License

### Trial License

A **built-in 24-hour trial license** is automatically used if no license is configured. This allows you to test the SDK immediately without any setup.

### Extended Evaluation

For extended evaluation beyond 24 hours, **[request a free 30-day trial license](https://www.dynamsoft.com/customer/license/trialLicense/?product=dbr&package=js)**.

### Production Use

For production deployment, **[contact sales](https://www.dynamsoft.com/contact/)** to purchase a commercial license.

To configure your license:

```javascript
const scanner = new Dynamsoft.BarcodeScanner({
	license: "YOUR_LICENSE_KEY_HERE",
});
```

## Support & Resources

**[Official Documentation](https://www.dynamsoft.com/barcode-reader/docs/web/programming/javascript/)**

**[Report Issues](https://github.com/Dynamsoft/barcode-reader-javascript-samples/issues)**

**[Contact Support](https://www.dynamsoft.com/contact/)** - support@dynamsoft.com

---

**Copyright © 2003–2026 Dynamsoft. All Rights Reserved.**

The use of Dynamsoft Barcode Reader JavaScript Edition is governed by the [Dynamsoft Terms and Conditions](https://www.dynamsoft.com/barcode-reader/license-agreement/#javascript).

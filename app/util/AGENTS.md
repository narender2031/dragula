# util

**Parent**: [app](../AGENTS.md) | **Repository**: A simple toolbar to drag and drop images from Unsplash to anywhere.

> Provides a collection of general-purpose helper functions for image manipulation, external image uploading, user subscription management, and integration with external image resource APIs. Encapsulates diverse utility functionalities required across the application.

## Key Concepts

### Semantic Concepts

- **Canvas Dimension Scaling based on Quality Settings**: Adjusts a given dimension value by applying a scaling factor determined by the application's quality settings (low, medium, or high).
- **Image Resizing and Data URL Conversion**: Resizes an input image to fit within a fixed-size canvas (2400x1600) while preserving its aspect ratio, then converts the resulting canvas content into a base64-encoded data URL.
- **Image Data URL Generation**: Generates a base64-encoded Data URL from an HTML image element by drawing it onto an offscreen canvas, optionally resizing it, and then exporting the canvas content.
- **Imgur Image Upload from Data URI**: Uploads a Base64 encoded image, provided as a data URI, to the Imgur image hosting service by sending it as multipart/form-data via an HTTP POST request.
- **User Subscription API**: Sends user email, MAC address, operating system platform, and application version to a remote service to register or subscribe the user.

### Code Patterns
**Transformer** (7), **Async/Callback** (5), **Utilities** (3), **Accessor** (3), **Module** (3), **Factory** (2)

## Key Components

### Public API

**Functions:**
- `const getOriginalDataUrl = (img) => {}` - Resizes an input image to fit within a fixed-size canvas (2400x1600) while preserving its aspect ratio, then converts the resulting canvas content into a base64-encoded data URL.
  Calls: changeDimension, ctx.drawImage, canvas.toDataURL
- `const getDataUrl = (img) => {}` - Generates a base64-encoded Data URL from an HTML image element by drawing it onto an offscreen canvas, optionally resizing it, and then exporting the canvas content.
  Calls: changeDimension, ctx.drawImage, canvas.toDataURL
- `const unploadImage = (dataUri) => {}` - Uploads a Base64 encoded image, provided as a data URI, to the Imgur image hosting service by sending it as multipart/form-data via an HTTP POST request.
  Calls: request.post
- `const subscribe = (email, mac) => {}` - Sends user email, MAC address, operating system platform, and application version to a remote service to register or subscribe the user.
  Calls: request.post
- `const updateUser = (uid, status) => {}` - Sends client-side telemetry data, including user activity status, platform, and usage counts, to a remote server via an asynchronous PATCH request.
  Calls: request.patch, os.platform, store.get

### Implementation

**Core Functions:**
- `const getOriginalDataUrl = (img) => {}` - Resizes an input image to fit within a fixed-size canvas (2400x1600) while preserving its aspect ratio, then converts the resulting canvas content into a base64-encoded data URL.
  Calls: changeDimension, ctx.drawImage, canvas.toDataURL
- `const getDataUrl = (img) => {}` - Generates a base64-encoded Data URL from an HTML image element by drawing it onto an offscreen canvas, optionally resizing it, and then exporting the canvas content.
  Calls: changeDimension, ctx.drawImage, canvas.toDataURL
- `const unploadImage = (dataUri) => {}` - Uploads a Base64 encoded image, provided as a data URI, to the Imgur image hosting service by sending it as multipart/form-data via an HTTP POST request.
  Calls: request.post
- `const subscribe = (email, mac) => {}` - Sends user email, MAC address, operating system platform, and application version to a remote service to register or subscribe the user.
  Calls: request.post
- `const updateUser = (uid, status) => {}` - Sends client-side telemetry data, including user activity status, platform, and usage counts, to a remote server via an asynchronous PATCH request.
  Calls: request.patch, os.platform, store.get
- `const changeDimension = (dimension) => {}` - Adjusts a given dimension value by applying a scaling factor determined by the application's quality settings (low, medium, or high).
  Calls: store.get
- `const fetchRandom = () => {}` - Fetches a random image URL from the Unsplash API, returning the direct URL of the image after a successful redirect.
  Calls: fetch
- `const fetchFromKeyword = (keyword) => {}` - Fetches a random image URL from Unsplash based on a provided keyword, returning the direct URL to the image.
  Calls: fetch

## Folder Overview

### Files

| Name | Summary |
|------|---------|
| `canvas.js` | Implements a collection of utility functions for creating offscreen HTML canvas elements, drawing images, and generating data URL representations. Defines methods for dynamically adjusting image dimensions based on application quality settings before rendering. |
| `imgur.js` | Implements functionality for uploading images to an external service. It prepares image data by extracting base64 content from a data URI and dispatches it via an HTTP POST request. |
| `subscribe.js` | Orchestrates user subscription and status updates by sending data to a remote server. It manages the initial registration of users and subsequent updates to their application usage metrics. |
| `unsplash.js` | Implements functions for retrieving image URLs from the Unsplash API, providing utilities for accessing Unsplash image resources. |

## Dependencies

### Standard Library
- `os`: Obtains system-level information, specifically the operating system platform, for inclusion in network request payloads.

### External Packages
- `electron-store`: Retrieves persistent application configuration settings and user metrics for various operations.
- `request-promise-native`: Facilitates asynchronous HTTP POST and PATCH requests for external service communication.
- `node-fetch`: Executes asynchronous HTTP GET requests to external image resource APIs.

## See Also

- [Parent overview →](../AGENTS.md) - Repository-level concepts and architecture
- [assets/ →](../assets/AGENTS.md) - Provides a collection of static media resources, including TrueType fonts and various image files in GIF and PNG formats. Contains visual and typographic assets essential for application rendering and display.
- [css/ →](../css/AGENTS.md) - Contains global and component-specific styling definitions that dictate the visual presentation and layout of the application's user interface, establishing its aesthetic and structural appearance.

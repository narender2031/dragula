# util

**Parent**: [app](../AGENTS.md) | **Repository**: A simple toolbar to drag and drop images from unsplash to anywhere.

> Provides a collection of utility functions for image processing, external image hosting, user subscription management, and dynamic image retrieval from third-party APIs.

## Key Concepts

### Semantic Concepts

- **Canvas Dimension Scaling based on Quality Settings**: Adjusts a given dimension value by applying a scaling factor determined by the application's quality settings (low, medium, or high).
- **Image Resizing and Data URL Conversion**: Resizes an input image to fit within a fixed-size canvas (2400x1600) while preserving its aspect ratio, then converts the resulting canvas content into a base64-encoded data URL.
- **Image Data URL Generation**: Generates a base64-encoded Data URL from an HTML image element by drawing it onto an offscreen canvas, optionally resizing it, and then exporting the canvas content.
- **Imgur Image Upload from Data URI**: Uploads a Base64 encoded image, provided as a data URI, to the Imgur image hosting service by sending it as multipart/form-data via an HTTP POST request.
- **User Subscription API**: Sends user email, MAC address, operating system platform, and application version to a remote service to register or subscribe the user.

### Code Patterns
**Async/Callback** (5), **Transformer** (4), **Utilities** (3), **Accessor** (3), **Module** (2), **Factory** (1)

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
| `canvas.js` | Defines utility functions for image processing, enabling the creation of data URLs from images and dynamic adjustment of image dimensions based on application quality settings. |
| `imgur.js` | Provides functionality for uploading images to an external service by extracting base64 data from data URI strings. It dispatches asynchronous HTTP POST requests to an external API for image submission. |
| `subscribe.js` | Implements functions for managing user subscriptions and updating user status with a remote service. Orchestrates the transmission of user details, system information, and application metrics via HTTP requests. |
| `unsplash.js` | Implements functions for retrieving random image URLs from the Unsplash API, either generally or based on a specific keyword. It functions as a utility module for interacting with the Unsplash image service. |

## Dependencies

### Standard Library
- `os`: Provides operating system platform information for inclusion in outgoing service requests.

### External Packages
- `electron-store`: Manages persistent application settings and retrieves local metrics for various operations.
- `request-promise-native`: Facilitates asynchronous HTTP requests for external API interactions, including image uploads and user status updates.
- `node-fetch`: Executes asynchronous HTTP GET requests to external image APIs for content retrieval.

## See Also

- [Parent overview →](../AGENTS.md) - Repository-level concepts and architecture
- [assets/ →](../assets/AGENTS.md) - Contains static visual and typographic resources utilized by an application. Provides various image files in PNG and GIF formats, alongside TrueType Font files for the Open Sans typeface, supporting diverse text rendering styles.
- [css/ →](../css/AGENTS.md) - Provides the core visual styling for an application's user interface, establishing the aesthetic and responsive behavior of various UI components.

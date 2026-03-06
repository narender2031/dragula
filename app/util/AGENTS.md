# util

**Parent**: [app](../AGENTS.md) | **Repository**: A simple toolbar to drag and drop images from Unsplash

> Provides a collection of utility functions for interacting with external services and performing image-related operations. It encapsulates logic for image processing, uploading to remote hosts, fetching from image APIs, and managing user subscriptions with usage metrics.

## Key Concepts

### Semantic Concepts

- **HTML Canvas Image Scaling and Data URL Conversion**: Creates a new canvas element, scales an input HTML image element's dimensions using a helper function, draws the scaled image onto the canvas, and then converts the canvas content into a base64-encoded data URL string.
- **Canvas Image Resizing and Data URL Generation**: Generates a base64 data URL from an HTML image element, drawing it onto a dynamically created canvas. Scales and centers the image to fit within fixed dimensions of `changeDimension(2400)` by `changeDimension(1600)` pixels, preserving its aspect ratio.
- **Application Quality-Based Dimension Scaling**: Calculates a scaled dimension value by applying a reduction factor based on a user-defined quality setting. It reduces the input dimension by 70% for 'low' quality, 50% for 'medium' quality, and retains the original dimension for other quality settings.
- **Base64 Data URI Image Upload via HTTP POST**: Initiates an asynchronous HTTP POST request to an image upload endpoint, extracting the base64 encoded image data from a provided data URI. Prepares the request payload by setting the extracted image data into the `formData` property of an external `options` object.
- **Remote User Subscription API Interaction**: Initiates a subscription request by sending user email, MAC address, operating system platform, and application version to a remote API endpoint.

### Code Patterns
**Transformer** (5), **Async/Callback** (5), **Accessor** (3), **Module** (3), **Utilities** (2), **Service** (2)

## Key Components

### Public API

**Functions:**
- `const getOriginalDataUrl = (img) => {}` - Generates a base64 data URL from an HTML image element, drawing it onto a dynamically created canvas.
  Calls: changeDimension
- `const getDataUrl = (img) => {}` - Creates a new canvas element, scales an input HTML image element's dimensions using a helper function, draws the scaled image onto the canvas, and then converts the canvas content into a base64-encoded data URL string.
  Calls: changeDimension
- `const unploadImage = (dataUri) => {}` - Initiates an asynchronous HTTP POST request to an image upload endpoint, extracting the base64 encoded image data from a provided data URI.
- `const subscribe = (email, mac) => {}` - Initiates a subscription request by sending user email, MAC address, operating system platform, and application version to a remote API endpoint.
- `const updateUser = (uid, status) => {}` - Performs an HTTP PATCH request to update a user's active status and transmit system metrics to a remote server.

### Implementation

**Core Functions:**
- `const getOriginalDataUrl = (img) => {}` - Generates a base64 data URL from an HTML image element, drawing it onto a dynamically created canvas.
  Calls: changeDimension
- `const getDataUrl = (img) => {}` - Creates a new canvas element, scales an input HTML image element's dimensions using a helper function, draws the scaled image onto the canvas, and then converts the canvas content into a base64-encoded data URL string.
  Calls: changeDimension
- `const unploadImage = (dataUri) => {}` - Initiates an asynchronous HTTP POST request to an image upload endpoint, extracting the base64 encoded image data from a provided data URI.
- `const subscribe = (email, mac) => {}` - Initiates a subscription request by sending user email, MAC address, operating system platform, and application version to a remote API endpoint.
- `const updateUser = (uid, status) => {}` - Performs an HTTP PATCH request to update a user's active status and transmit system metrics to a remote server.
- `const changeDimension = (dimension) => {}` - Calculates a scaled dimension value by applying a reduction factor based on a user-defined quality setting.
- `const fetchRandom = () => {}` - Initiates an asynchronous HTTP request to the Unsplash API's random image endpoint, subsequently extracting the direct image URL from the successful response.
- `const fetchFromKeyword = (keyword) => {}` - Retrieves a random image URL from Unsplash by constructing a query based on a provided keyword.

## Folder Overview

### Files

| Name | Summary |
|------|---------|
| `canvas.js` | Implements functions for image processing using HTML canvas elements. It provides utilities to generate base64 data URLs from images and to calculate scaled dimensions based on quality settings. |
| `imgur.js` | Implements a function for asynchronously uploading images to a remote service. It prepares the request by extracting base64 encoded image data from a data URI and sending it via an HTTP POST request. |
| `subscribe.js` | Orchestrates user subscription and update processes by sending user-specific and system-level data to remote API endpoints. Defines functions for initiating new subscriptions and updating existing user profiles with application usage metrics. |
| `unsplash.js` | Implements functions for fetching random and keyword-based image URLs from the Unsplash API. It abstracts the process of making HTTP requests and parsing the API responses to extract direct image links. |

## Dependencies

### Standard Library
- `os`: Acquires operating system platform identifiers for inclusion in user subscription and update payloads.

### External Packages
- `electron-store`: Underlies persistent configuration retrieval for image quality settings and application usage metrics.
- `request-promise-native`: Manages asynchronous HTTP requests for uploading images and interacting with remote API services.
- `node-fetch`: Performs asynchronous HTTP GET requests to external image APIs.

## See Also

- [Parent overview →](../AGENTS.md) - Repository-level concepts and architecture
- [assets/ →](../assets/AGENTS.md) - Provides a collection of static visual and typographic resources for an application. Contains various image files in GIF and PNG formats, along with the Open Sans typeface in multiple weights and styles.
- [css/ →](../css/AGENTS.md) - Provides the visual styling for a web application's user interface elements, establishing global layout, typography, and specific appearance rules for various components.

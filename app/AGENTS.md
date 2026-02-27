# app

**Parent**: [default](../AGENTS.md) | **Repository**: A simple toolbar to drag and drop images from unsplash to anywhere.

> Provides the main client-side application logic, user interface, and static resources. Orchestrates user interface interactions, manages application settings, and integrates with external services.

## Key Concepts

### Semantic Concepts

- **Onboarding Flow Navigation**: Manages the sequential progression through an application's onboarding or guided tour interface, transitioning between UI states based on user interaction and persistent onboarding status.
- **Screenshot Upload to Imgur**: Captures an image from a canvas, uploads it to Imgur, and sends the resulting public URL to the main Electron process for further handling.
- **User Onboarding with Email and Device ID**: Handles the initial user onboarding process by validating the provided email, retrieving the device's unique MAC address, and submitting this information to a subscription API. It then updates local application settings and manages UI transitions to guide the user through the setup.
- **Electron IPC Drag Data Transfer**: Initiates a drag operation in an Electron renderer process, preventing default browser behavior and sending image data (either current or original) to the main process via Inter-Process Communication (IPC) for native drag-and-drop handling.
- **Renderer Process Initialization**: Manages the initial loading sequence of the Electron renderer process, including displaying a welcome screen, checking user onboarding status, and updating user activity via an API call.

### Code Patterns
**Handler** (25), **Mutator** (22), **Async/Callback** (6), **Accessor** (4), **Transformer** (2), **Entry Point** (1)

## Folder Overview

### Folders

| Name | Summary |
|------|---------|
| [assets/](assets/AGENTS.md) | Contains static visual and typographic resources utilized by an application. Provides various image files in PNG and GIF formats, alongside TrueType Font files for the Open Sans typeface, supporting diverse text rendering styles. |
| [css/](css/AGENTS.md) | Provides the core visual styling for an application's user interface, establishing the aesthetic and responsive behavior of various UI components. |
| [util/](util/AGENTS.md) | Provides a collection of utility functions for image processing, external image hosting, user subscription management, and dynamic image retrieval from third-party APIs. |

### Files

| Name | Summary |
|------|---------|
| `index.html` | Defines the foundational structure and user interface layout for a web application. Establishes the main sections, interactive elements, and links to external stylesheets for presentation. |
| `renderer.js` | Orchestrates user interface interactions within an Electron renderer process by handling various click and keyboard events. Manages UI element visibility, loads images based on user input and stored settings, and communicates with the main process for application control and external link navigation. |

## Dependencies

### Standard Library
- `os`: Supplies operating system platform details for contextualizing external service requests.

### External Packages
- `electron-store`: Manages persistent application settings and local metrics, ensuring configuration and operational data are stored and retrieved across sessions.
- `request-promise-native`: Facilitates asynchronous HTTP requests for interacting with external APIs, supporting data exchange and service integration.
- `electron`: Enables core inter-process communication within the Electron application, facilitating control and coordination between renderer and main processes.
- `macaddress`: Provides hardware identification capabilities, though its specific application within the module is not explicitly defined.
- `node-fetch`: Executes asynchronous HTTP GET requests to external image APIs for content retrieval.

## See Also

- [Parent overview →](../AGENTS.md) - Repository-level concepts and architecture

# app

**Parent**: [default](../AGENTS.md) | **Repository**: A simple toolbar to drag and drop images from Unsplash to anywhere.

> Provides the core client-side application, encompassing static assets, styling definitions, general-purpose utility functions, and the foundational HTML structure. Implements the renderer-side JavaScript logic for user interface interactions and communication with the Electron main process.

## Key Concepts

### Semantic Concepts

- **Onboarding Flow Navigation**: Manages the sequential progression through an application's onboarding or guided tour interface, transitioning between UI states based on user interaction and persistent onboarding status.
- **Screenshot Upload to Imgur**: Captures an image from a canvas, uploads it to Imgur, and sends the resulting public URL to the main Electron process for further handling.
- **User Onboarding with Email and Device ID**: Handles the initial user onboarding process by validating the provided email, retrieving the device's unique MAC address, and submitting this information to a subscription API. It then updates local application settings and manages UI transitions to guide the user through the setup.
- **Electron IPC Drag Data Transfer**: Initiates a drag operation in an Electron renderer process, preventing default browser behavior and sending image data (either current or original) to the main process via Inter-Process Communication (IPC) for native drag-and-drop handling.
- **Renderer Process Initialization**: Manages the initial loading sequence of the Electron renderer process, including displaying a welcome screen, checking user onboarding status, and updating user activity via an API call.

### Code Patterns
**Handler** (23), **Mutator** (22), **Async/Callback** (6), **Accessor** (4), **Transformer** (3), **Validator** (2)

## Folder Overview

### Folders

| Name | Summary |
|------|---------|
| [assets/](assets/AGENTS.md) | Provides a collection of static media resources, including TrueType fonts and various image files in GIF and PNG formats. Contains visual and typographic assets essential for application rendering and display. |
| [css/](css/AGENTS.md) | Contains global and component-specific styling definitions that dictate the visual presentation and layout of the application's user interface, establishing its aesthetic and structural appearance. |
| [util/](util/AGENTS.md) | Provides a collection of general-purpose helper functions for image manipulation, external image uploading, user subscription management, and integration with external image resource APIs. Encapsulates diverse utility functionalities required across the application. |

### Files

| Name | Summary |
|------|---------|
| `index.html` | Defines the foundational structure and user interface layout for a web application. Establishes the main entry point for the browser, incorporating elements such as a search bar, an image display area, alert sections, and a toolbar. |
| `renderer.js` | Orchestrates user interface interactions within the renderer process, handling various click and keydown events to manage UI elements, load images, and navigate external links. It facilitates communication with the Electron main process for window management and application settings. |

## Dependencies

### Standard Library
- `os`: Provides system-level information, specifically the operating system platform, for inclusion in network request payloads.

### External Packages
- `electron-store`: Underlies persistent storage for application settings and user metrics, enabling retrieval of configuration data across different parts of the application.
- `request-promise-native`: Facilitates asynchronous HTTP POST and PATCH requests for communication with external services.
- `electron`: Enables inter-process communication with the Electron main process, facilitating window management and application-level interactions.
- `macaddress`: Provides access to hardware-specific identifiers for potential device-level tracking or unique identification.
- `node-fetch`: Executes asynchronous HTTP GET requests to external image resource APIs.

## See Also

- [Parent overview →](../AGENTS.md) - Repository-level concepts and architecture

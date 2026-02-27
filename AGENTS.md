# default

**Location**: Root directory

> Contains the foundational elements of the Dragula Electron application, including its licensing information, project metadata, and the primary script responsible for initializing and managing the main application window.

## Repository Overview
**[README.md](README.md)**

Introduces the "Dragula" application, detailing its core functionality as a toolbar for dragging and dropping images from Unsplash. Highlights key features such as universal drag-and-drop support, original image viewing, image search capabilities, markdown copying, and direct image downloads.

## Code Style

- **Indentation**: tabs
- **Naming**: camelCase
- **Error Handling**: Minimal error handling
- **Common Patterns**: Arrow functions, Destructuring

## Conventions & Guidelines

- [JavaScript Conventions](JAVASCRIPT_CONVENTIONS.md)
- [Architecture & Development Guidelines](ARCHITECTURE.md)

## Key Concepts

### Semantic Concepts

- **Onboarding Flow Navigation**: Manages the sequential progression through an application's onboarding or guided tour interface, transitioning between UI states based on user interaction and persistent onboarding status.
- **Screenshot Upload to Imgur**: Captures an image from a canvas, uploads it to Imgur, and sends the resulting public URL to the main Electron process for further handling.
- **User Onboarding with Email and Device ID**: Handles the initial user onboarding process by validating the provided email, retrieving the device's unique MAC address, and submitting this information to a subscription API. It then updates local application settings and manages UI transitions to guide the user through the setup.
- **Electron IPC Drag Data Transfer**: Initiates a drag operation in an Electron renderer process, preventing default browser behavior and sending image data (either current or original) to the main process via Inter-Process Communication (IPC) for native drag-and-drop handling.
- **Renderer Process Initialization**: Manages the initial loading sequence of the Electron renderer process, including displaying a welcome screen, checking user onboarding status, and updating user activity via an API call.

### Code Patterns
**Entry Point** (2), **Mutator** (2), **Configuration** (2), **Module** (1), **Factory** (1), **Accessor** (1)

## Folder Overview

### Folders

| Name | Summary |
|------|---------|
| [app/](app/AGENTS.md) | Provides the core client-side application, encompassing static assets, styling definitions, general-purpose utility functions, and the foundational HTML structure. Implements the renderer-side JavaScript logic for user interface interactions and communication with the Electron main process. |

### Files

| Name | Summary |
|------|---------|
| `LICENSE` | Defines the MIT License terms, specifying the permissions and limitations for using, copying, modifying, and distributing the associated software. Establishes the legal framework for the software's usage and distribution. |
| `README.md` | Introduces the "Dragula" application, detailing its core functionality as a toolbar for dragging and dropping images from Unsplash. Highlights key features such as universal drag-and-drop support, original image viewing, image search capabilities, markdown copying, and direct image downloads. |
| `main.js` | Orchestrates the creation and initial configuration of the main Electron browser window. It also manages the window's positioning, applying stored preferences or default settings. |
| `package-lock.json` | Records the precise dependency tree and their exact versions, ensuring consistent and reproducible installations across different environments. Specifies the resolved URLs and integrity hashes for all direct and transitive project dependencies. |
| `package.json` | Defines the project's metadata, build configurations, and script commands for the Dragula Electron application. It also lists all development and runtime dependencies required for the application's functionality and maintenance. |
## Package Manager

Use **npm**: `npm install`, `npm run start`, `npm run build`, `npm run ship`, `npm run build:linux`, `npm run ship:linux`

## Dependencies

### Standard Library
- `os`: Provides access to operating system-specific information, which might be used for path resolution or environment checks.
- `fs`: Supports fundamental file system operations, potentially for managing downloaded images or configuration files.

### External Packages
- `electron-store`: Persists application settings and user preferences, including window position, across sessions.
- `electron`: Underlies the application's core desktop framework, enabling the creation and management of the main graphical user interface window.
- `electron-dl`: Facilitates robust file download capabilities within the Electron application, supporting direct image downloads.
- `electron-updater`: Manages the application's automatic update process, ensuring users always have the latest version.
- `electron-positioner`: Directs the precise placement and centering of the application's browser window on the screen.

## Architecture

### Entry Points
- `main.js` - Orchestrates the creation and initial configuration of the main Electron browser window. It also manages the window's positioning, applying stored preferences or default settings.


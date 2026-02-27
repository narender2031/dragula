# default

**Location**: Root directory

> Provides the foundational structure for an Electron application, encompassing its licensing, documentation, and the primary entry point for application setup and window management. Defines project metadata and manages all required dependencies for development and runtime operations.

## Repository Overview
**[README.md](README.md)**

Introduces the 'Dragula' application, a simple toolbar for dragging and dropping images from Unsplash, and outlines its core features. Documents the application's functionality through descriptions and visual demonstrations.

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
**Entry Point** (2), **Factory** (2), **Mutator** (2), **Configuration** (2), **Accessor** (1)

## Folder Overview

### Folders

| Name | Summary |
|------|---------|
| [app/](app/AGENTS.md) | Provides the main client-side application logic, user interface, and static resources. Orchestrates user interface interactions, manages application settings, and integrates with external services. |

### Files

| Name | Summary |
|------|---------|
| `LICENSE` | Defines the terms and conditions for using, modifying, and distributing the software under the MIT License. Specifies the rights and limitations for users and developers of the project. |
| `README.md` | Introduces the 'Dragula' application, a simple toolbar for dragging and dropping images from Unsplash, and outlines its core features. Documents the application's functionality through descriptions and visual demonstrations. |
| `main.js` | Orchestrates the main application window's creation and positioning, functioning as an entry point for the Electron application's UI setup. |
| `package-lock.json` | Defines the precise dependency tree and their exact versions for a project. It guarantees consistent package installations across various development and deployment environments by locking down all direct and transitive dependencies. |
| `package.json` | Defines the project's metadata, including its name, version, and description, along with scripts for development and building. Configures the Electron application's build process and lists all development and runtime dependencies required for the project. |
## Package Manager

Use **npm**: `npm install`, `npm run start`, `npm run build`, `npm run ship`, `npm run build:linux`, `npm run ship:linux`

## Dependencies

### Standard Library
- `os`: Provides operating system-specific information and utilities for environmental checks.
- `fs`: Enables file system operations, potentially for reading or writing local data.

### External Packages
- `electron-store`: Persists application configuration and state, specifically storing and recalling the window's last known position.
- `electron`: Powers the desktop application framework, enabling the creation and management of browser windows.
- `electron-dl`: Underlies file download capabilities within the application.
- `electron-updater`: Supports automatic application updates, ensuring users always have the latest version.
- `electron-positioner`: Manages the precise placement and positioning of the application window on the screen.

## Architecture

### Entry Points
- `main.js` - Orchestrates the main application window's creation and positioning, functioning as an entry point for the Electron application's UI setup.


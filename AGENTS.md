# default

**Location**: Root directory

> Contains the primary entry point for the Electron application, defining the main window's lifecycle, creation, and dynamic positioning. It also includes essential project metadata and licensing details.

## Repository Overview
**[README.md](README.md)**

Introduces the 'Dragula' application, a simple toolbar for dragging and dropping images from Unsplash. Explains its core functionality and highlights key features such as drag-and-drop, original image usage, search capabilities, Markdown copying, and direct image downloads.

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

- **Electron Renderer Process UI Interaction and IPC**: Handles a click event by preventing its default action, conditionally loads an image if a source is missing, and updates the display styles of multiple UI elements. It also sets an image source dynamically using a stored setting and sends an inter-process communication message to the main Electron process.
- **Electron Renderer Process Event Handling and IPC**: Responds to a user interface click event by preventing its default action, adjusting the visibility of two display elements, invoking a local settings retrieval function, and dispatching a 'close' message via Electron's inter-process communication.
- **Electron Renderer Process Application Closure Signaling**: Handles a user-initiated close event by preventing its default browser behavior, subsequently hiding a settings display, showing an entry display, refreshing application settings, and signaling the main Electron process to close the application.
- **Interactive Input Submission via Keyboard Event**: Handles a keyboard `keydown` event, specifically checking for the Enter key press. Upon detecting an Enter key press, it retrieves the current value from the event target and initiates an image loading operation using that value, provided the value is not empty.
- **DOM Event Default Action Prevention**: Handles an event by preventing its default browser action and subsequently initiating an image load operation using the current value from a `keyword` input.

### Code Patterns
**Entry Point** (2), **Mutator** (2), **Configuration** (2), **Utilities** (1), **Factory** (1), **Accessor** (1)

## Folder Overview

### Folders

| Name | Summary |
|------|---------|
| [app/](app/AGENTS.md) | Provides the core application structure and user interface for an Electron application, integrating static assets, styling, utility functions, and front-end interaction logic. It orchestrates user interface events and manages application settings to deliver a functional user experience. |

### Files

| Name | Summary |
|------|---------|
| `LICENSE` | Defines the legal terms and conditions for using, modifying, and distributing the associated software. Specifies the permissions and limitations granted to users under the MIT License. |
| `README.md` | Introduces the 'Dragula' application, a simple toolbar for dragging and dropping images from Unsplash. Explains its core functionality and highlights key features such as drag-and-drop, original image usage, search capabilities, Markdown copying, and direct image downloads. |
| `main.js` | Defines core functionalities for managing the application's main Electron window, including its initial creation, display, and dynamic positioning. Functions as the primary entry point for the application's window management logic. |
| `package-lock.json` | Records the precise dependency tree of the project, including exact versions and integrity hashes for all direct and transitive packages. Ensures consistent and reproducible installations across various development and deployment environments. |
| `package.json` | Defines the project's metadata, dependencies, and build configurations for the Dragula application. It specifies the application's name, version, main entry point, and scripts for development and distribution. |
## Package Manager

Use **npm**: `npm install`, `npm run start`, `npm run build`, `npm run ship`, `npm run build:linux`, `npm run ship:linux`

## Dependencies

### Standard Library
- `os`: Offers operating system-specific utility functions for environmental awareness.
- `fs`: Provides file system interaction capabilities for various application operations.

### External Packages
- `electron-store`: Underlies the persistence and retrieval of application settings, including user preferences.
- `electron`: Powers the fundamental application framework and manages the main window's lifecycle.
- `electron-dl`: Enables robust download management features within the application.
- `electron-updater`: Supports automatic application updates, ensuring users always have the latest version.
- `electron-positioner`: Facilitates precise positioning and centering of the application's main window.

## Architecture

### Entry Points
- `main.js` - Defines core functionalities for managing the application's main Electron window, including its initial creation, display, and dynamic positioning. Functions as the primary entry point for the application's window management logic.


# JSErrorFlow-RealTime-Visualizer-Browser-Extension

![GitHub Workflow Status](https://img.shields.io/github/workflow/status/chirag127/JSErrorFlow-RealTime-Visualizer-Browser-Extension/ci.yml?label=Build&style=flat-square)
![Code Coverage](https://img.shields.io/codecov/c/github/chirag127/JSErrorFlow-RealTime-Visualizer-Browser-Extension?style=flat-square)
![Language](https://img.shields.io/github/languages/top/chirag127/JSErrorFlow-RealTime-Visualizer-Browser-Extension?style=flat-square)
![License](https://img.shields.io/github/license/chirag127/JSErrorFlow-RealTime-Visualizer-Browser-Extension?style=flat-square)
![GitHub Stars](https://img.shields.io/github/stars/chirag127/JSErrorFlow-RealTime-Visualizer-Browser-Extension?style=flat-square)

> **JSErrorFlow** provides elite, real-time JavaScript error visualization directly on the DOM, transforming opaque stack traces into actionable, visually pinpointed feedback for rapid frontend debugging.

This extension revolutionizes the debugging cycle by mapping JavaScript exceptions directly onto the affected HTML elements, offering superior context retention over traditional developer consoles.

[⭐ Star this Repo](https://github.com/chirag127/JSErrorFlow-RealTime-Visualizer-Browser-Extension)

---

## 🚀 Project Overview & Architecture

**JSErrorFlow** is engineered using a highly decoupled architecture standard for modern browser extensions, prioritizing performance, non-intrusiveness, and immediate feedback loops.

### Core Components

1.  **Injection Layer (Content Script):** Hooks into the target webpage's DOM and execution context. Responsible for intercepting `window.onerror` or monitoring specific frameworks' error streams.
2.  **Visualization Engine (Overlay Renderer):** A lightweight overlay system that draws visual indicators (e.g., bounding boxes, error tags) directly onto the elements referenced in the error stack trace.
3.  **Communication Bridge (Background Service Worker):** Manages persistent state, configuration, and handles secure, high-level communication between the injection layer and the browser UI panel.

### Architectural Diagram (High-Level View)

ascii
+----------------------------------+
|      Browser Extension UI/Panel    |
|  (Configuration & Logging History) |
+------------------+---------------+
                   |
        (Async Message Passing)
                   v
+----------------------------------+
|  Background Service Worker (Core) |
|  - State Management               |
|  - Inter-script Communication     |
+------------------+---------------+
                   |
        (DOM Injection/Interception)
                   v
+----------------------------------+
|  Content Scripts (Injected Page)   |
|  - Error Hooking (window.onerror)  |
|  - DOM Element Mapping & Highlighting |
+----------------------------------+


## 🗺️ Table of Contents

1.  [🚀 Project Overview & Architecture](#-project-overview--architecture)
    *   [Core Components](#core-components)
    *   [Architectural Diagram (High-Level View)](#architectural-diagram-high-level-view)
2.  [🗺️ Table of Contents](#-table-of-contents)
3.  [🛠️ Technology Stack & Compliance](#-technology-stack--compliance)
4.  [⚙️ Development & Setup](#-development--setup)
5.  [🤖 AI Agent Directives (SSOT for Future Automation)](#-ai-agent-directives-ssot-for-future-automation)
6.  [📚 Documentation & Contribution](#-documentation--contribution)
7.  [⚖️ License](#-license)

---

## 🛠️ Technology Stack & Compliance

As an elite project, **JSErrorFlow** is built for modern browser performance and strict security standards.

| Category | Technology | Standard Adherence |
| :--- | :--- | :--- |
| **Core Language** | TypeScript 5.x (Strict Mode) | Type Safety, Scalability |
| **Build Tool** | Vite 5+ (Rollup Backend) | Tree-Shaking, Dev Speed |
| **Extension Framework** | WXT (Wxt) | Manifest V3 Compliance, Unified API Layer |
| **Styling** | TailwindCSS 4.x | Utility-First, Maintainability |
| **Linting/Formatting** | Biome (Linter/Formatter) | Ultra-Fast Static Analysis |
| **Testing** | Vitest (Unit/Component) & Playwright (E2E) | Robust Verification |

## ⚙️ Development & Setup

This repository adheres to the Apex 'Zero-Defect' principle. Local setup requires Node.js (v20+ recommended).

### Prerequisites

bash
# 1. Clone the repository
git clone https://github.com/chirag127/JSErrorFlow-RealTime-Visualizer-Browser-Extension.git
cd JSErrorFlow-RealTime-Visualizer-Browser-Extension

# 2. Install dependencies using uv (hypothetical alignment for speed/modernity)
# Note: For Node projects, we use npm/pnpm, but align to the spirit of modern package management.
pnpm install 
# OR
npm install


### Execution Scripts

| Script | Command | Description |
| :--- | :--- | :--- |
| **Development** | `pnpm dev` | Runs Vite in watch mode, rebuilding extension assets on file change. |
| **Linting** | `pnpm lint` | Executes Biome to check code quality and formatting compliance. |
| **Testing (Unit)** | `pnpm test:unit` | Runs Vitest suites against isolated components/logic. |
| **Testing (E2E)** | `pnpm test:e2e` | Executes Playwright against a sample application or staging environment. |
| **Build** | `pnpm build` | Creates the production-ready, optimized distribution files for packaging. |

### Core Development Principles

*   **SOLID:** Strict adherence to Single Responsibility Principle in script separation (Content vs. Background).
*   **DRY:** Avoid redundant error handling logic; abstract error reporting into core utility modules.
*   **YAGNI:** Do not implement features until the user-facing debugging workflow explicitly demands them.

---

## 🤖 AI Agent Directives (SSOT for Future Automation)

<details>
<summary><strong>Apex AI Agent Configuration for JSErrorFlow</strong></summary>

### 1. System Identity & Philosophy

**Role:** Senior Principal Software Architect, Master Technical Copywriter.
**Philosophy:** "Zero-Defect, High-Velocity, Future-Proof." Enforce FAANG-level standards.
**Goal:** Maintain and evolve the extension's performance, debugging accuracy, and Manifest V3 compliance.

### 2. Technology Stack Definition (Contextual Alignment)

**Primary Language:** TypeScript (Strict Mode).
**Toolchain Enforcement:**
*   **Linting/Formatting:** Biome must be the *sole* authority on code style. Enforce a maximum line length of 120 characters.
*   **Bundling:** Vite/Rollup configuration must prioritize small asset size for the bundled extension files.
*   **Testing:** All new logic must have accompanying Vitest unit tests (minimum 90% coverage threshold for new feature files) and Playwright E2E validation for successful DOM highlighting.
*   **Manifest:** Strictly adhere to **Manifest V3 (MV3)** structure. Service Workers must be used correctly, minimizing long-running tasks.

### 3. Verification Commands

Agents must use these commands for initial environment verification:

bash
# Verify environment health and dependency integrity
# If 'pnpm' is used, this confirms the package manager is functional.
ls -la node_modules 

pnpm lint 

# Verify build output size
npm run build && du -sh dist


### 4. Architectural Directives

1.  **Decoupling:** Ensure Content Scripts cannot directly access Background Service Worker scope. All communication **MUST** flow through `chrome.runtime.sendMessage` or `chrome.runtime.onMessage`.
2.  **DOM Isolation:** Highlighting mechanisms must utilize Shadow DOM or highly specific CSS selectors to prevent styling leakage into the host page.
3.  **Error Normalization:** All native `Error` objects intercepted must be immediately serialized into a standardized, internal JSON structure before transmission across script boundaries.

</details>

---

## 📚 Documentation & Contribution

We welcome contributions that enhance visualization accuracy, performance, or extension stability. Please review our full contribution guidelines.

*   [CONTRIBUTING.md](./.github/CONTRIBUTING.md)
*   [SECURITY.md](./.github/SECURITY.md)
*   [ISSUE_TEMPLATE](./.github/ISSUE_TEMPLATE/bug_report.md)

## ⚖️ License

This project is licensed under the **CC BY-NC 4.0 License**. See the [LICENSE](./LICENSE) file for details.

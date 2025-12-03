<div align="center">
  <img src="https://github.com/user-attachments/assets/bcde869b-110f-40dc-a24c-976518ad9b77" alt="Graphite: WebDev Banner" />
</div>

<div align="center">
  <br />
  <img src="https://img.shields.io/badge/Platform-Client--Side-blue?style=for-the-badge&logo=Web&logoColor=white" alt="Platform: Client-Side" />
  <img src="https://img.shields.io/badge/AI_Core-Gemini_3.0_Pro-8A2BE2?style=for-the-badge&logo=google-gemini&logoColor=white" alt="AI Core: Gemini 3.0 Pro" />
  <img src="https://img.shields.io/badge/Framework-React_19-61DAFB?style=for-the-badge&logo=react&logoColor=black" alt="Framework: React 19" />
  <img src="https://img.shields.io/badge/Status-Proprietary_/_In_Development-orange?style=for-the-badge" alt="Status: In Development" />
  <img src="https://img.shields.io/badge/Ecosystem-Graphite_2-2F4F4F?style=for-the-badge" alt="Ecosystem: Graphite 2" />
</div>

<br>

> **Graphite: WebDev** is an advanced development environment that functions as a cognitive partner, translating natural language, strategic plans, and high-level concepts directly into functional, production-ready web applications. It moves beyond simple autocompletion to offer true architectural collaboration.

This repository provides a showcase of the proprietary technology and architecture behind Graphite: WebDev, a flagship application within the **Graphite 2** ecosystem. As this is a demonstration of an in-development platform, this is not an open-source project and there are no installation or contribution instructions.

---

### **Core Philosophy: From Cognition to Code**

Traditional development tools assist execution. Graphite is designed to assist *cognition*. It bridges the gap between the fluid, non-linear nature of human thought and the rigid, structured requirements of code. The environment is built to understand intent, architect solutions, and execute with precision, allowing creators to operate at the speed of their ideas.

### **The Multi-Modal Workspace**

Graphite provides three distinct, seamlessly integrated workspaces, allowing users to select the mode that best suits their task and expertise. The journey begins at a dedicated launch screen, guiding the user toward their preferred workflow.

<img width="1891" height="893" alt="Application launch window where user selects what mode to use" src="https://github.com/user-attachments/assets/b4aeec82-fb83-4c64-9f6f-c700363a439c" />

| Mode | Description | Ideal For |
| :--- | :--- | :--- |
| Designer Mode | A purely conversational interface where ideas are translated into a live, interactive webpage. The AI handles all file management and code generation behind the scenes. | Rapid prototyping, visual-first creators, and users with no coding experience. |
| **Developer Mode** | A full-featured, client-side IDE with a file manager, a high-performance code editor, an AI chat interface, and a sandboxed live preview with an integrated console. | Professional developers, technical users, and those who require granular control over the codebase. |
| Architect Mode | A visual, node-based canvas for designing complex prompt chains, orchestrating multi-agent workflows, and managing application state as a directed graph. | Strategic planning, non-linear development, and orchestrating complex, multi-step AI tasks. |

<br>

<div align="center">
  <img width="1867" height="892" alt="Designer Mode UI" src="https://github.com/user-attachments/assets/10f7d635-79e6-4a92-a604-501d1a57b984" />
  <em>The streamlined 'Designer Mode' focuses on the conversation and the live result.</em>
</div>

<br>

<div align="center">
  <img width="1890" height="893" alt="Developer Mode UI showing file tree, code editor, and AI chat" src="https://github.com/user-attachments/assets/aac847f7-ba9e-49ca-bac1-0bd9766c5451" />
  <em>The professional 'Developer Mode' provides a familiar and powerful IDE experience.</em>
</div>

---

### **Feature Deep Dive & Technical Showcase**

<details>
<summary><strong>Agentic Architecture & The Blueprint Canvas</strong></summary>

<br>

The Blueprint Canvas is the core of Graphite's strategic capabilities. It transforms the development process from a linear chat history into a dynamic, visual graph. Each node represents a distinct state or operation, allowing for branching, merging, and complex, non-linear workflows.

-   **Node-Based Flow:** Users can visually construct logic by connecting nodes representing user instructions, AI generations, file storage, and automated reviews.
-   **Multi-Agent Swarm:** The "Agent" node deploys a specialized team of AIs—a **Planner**, a **Developer**, and a **Visual Reviewer**—that collaborate to execute complex tasks. The system automates the planning, coding, and quality assurance process.
-   **State Reconstruction:** Every node in the graph can serve as a starting point for a new generation. The system traverses the graph backward, starting from a full file system snapshot at a root node and applying the deltas (`fileEdits`) from each subsequent AI node to perfectly reconstruct the codebase state at any point in time.

<img width="1891" height="893" alt="The Blueprint Canvas showing an Agentic Node awaiting user approval" src="https://github.com/user-attachments/assets/ad402255-3020-49d6-9989-f18e43557f6f" />

</details>

<details>
<summary><strong>The Shadow Output Protocol</strong></summary>

<br>

To ensure reliability, Graphite utilizes a proprietary communication layer called the **Shadow Output Protocol**. This system decouples the AI's conversational output from its machine-executable instructions.

-   **Structured & Deterministic:** The AI is required to respond with a strict JSON schema containing a natural-language `explanation` and a `changes` array. This eliminates the fragility of parsing code from a free-form text response.
-   **Surgical Operations:** The protocol supports high-precision file operations like `write` (create/overwrite) and `replace` (search and replace). The `replace` operation uses a flexible patching algorithm that can locate and modify code blocks even with variations in whitespace or formatting.
-   **Reliability:** This structured approach ensures that AI-driven code modifications are 100% accurate and predictable, preventing context loss and file corruption.

</details>

<details>
<summary><strong>Dynamic Context Management</strong></summary>

<br>

The system employs an intelligent context management pipeline to maximize the AI's understanding while respecting model token limits.

-   **Prioritization:** The user's currently active file is always included in the context in its entirety.
-   **Smart Truncation:** To save space, large, inactive files are automatically truncated. The system preserves the beginning and end of the file—where imports and key logic often reside—while replacing the middle with a clear "truncated" comment. This gives the AI crucial context without overloading the token window.
-   **User Control:** A dedicated Context Control panel allows the user to manually select which files and whether chat history should be included in the payload for the next AI generation, providing granular control over the AI's "memory."

<img width="1890" height="892" alt="The Context Memory Manager panel" src="https://github.com/user-attachments/assets/8200ccb2-e616-4f2d-b335-42ce26451709" />

</details>

<details>
<summary><strong>Full GitHub Integration</strong></summary>

<br>

Graphite: WebDev is fully integrated with GitHub, transforming it from a sandboxed editor into a powerful component of a professional development workflow.

-   **Repository Cloning:** Users can provide a GitHub Personal Access Token to browse and import their repositories. The system fetches the repository's file tree, filters for relevant web development files, and populates the virtual file system.
-   **Context-Aware Development:** The AI can read the entire imported codebase, enabling it to understand existing project structures, adhere to coding styles, and make context-aware modifications.
-   **Committing and Pushing:** From within the IDE, users can commit and push changes for any file directly back to their GitHub repository, complete with a commit message.

<img width="1891" height="893" alt="The GitHub repository import manager" src="https://github.com/user-attachments/assets/d1084d1d-028b-4b6f-9158-85a9381187b7" />
<img width="1890" height="893" alt="The GitHub commit and push security protocol interface" src="https://github.com/user-attachments/assets/ae02149e-b7c5-40d4-afdb-3aaf6698432b" />

</details>

<details>
<summary><strong>Sandboxed Execution & Live Preview</strong></summary>

<br>

All code is rendered in a secure, high-fidelity preview environment that mirrors a real web browser while protecting the user and the main application.

-   **Secure `iframe` Sandbox:** The preview runs in an `iframe` with a restrictive `sandbox` attribute, isolating its execution context.
-   **Infinite Loop Protection:** Before being injected, JavaScript code is transpiled on-the-fly using a client-side Babel plugin. This instruments all loops with a guard function that detects and terminates potential infinite loops, preventing browser freezes.
-   **Integrated Tooling:** The preview includes a responsive viewport controller and an integrated console. A custom script intercepts logs, errors, and warnings from the `iframe` and forwards them to the Developer Mode console panel via `postMessage`, creating a seamless debugging experience.

<img width="1890" height="892" alt="The Live Preview environment with responsive viewport controls" src="https://github.com/user-attachments/assets/248b763b-10e7-47c5-a7ed-2d1c04f7ea1c" />

</details>

<details>
<summary><strong>Adaptive & Personalized UI</strong></summary>

<br>

The entire user interface is built on a dynamic and customizable design system, allowing users to tailor the environment to their preferences.

-   **Multiple Themes:** Switch between `Clay`, `Flat`, `Glass`, and `Retro` themes to change the entire look and feel of the application.
-   **Light & Dark Modes:** A "Light Shift" slider provides granular control over the lighting and shadow intensity, with an automatic switch between light and dark modes.
-   **Internationalization:** The UI supports multiple languages, allowing for a fully localized experience.

---
Light mode:
<img width="1893" height="895" alt="Graphite: WebDev in Light Mode" src="https://github.com/dovvnloading/Graphite-WebDev/blob/main/ScreenShots/Screenshot%20light%20mode.png?raw=true" />

---

Dark Mode:
<img width="1889" height="893" alt="Graphite: WebDev in Dark Mode" src="https://github.com/user-attachments/assets/75c45009-7269-434e-a131-4928d6bc3e88" />

---

Language Selection: 
<img width="1891" height="893" alt="Language selection menu in the Settings modal" src="https://github.com/user-attachments/assets/bb660692-fd80-4a8a-8881-9947b270792e" />

</details>

---

### **Technology Stack**

| Category | Technology | Purpose |
| :--- | :--- | :--- |
| **Framework** | React 19, TypeScript | Core application structure and type safety. |
| **Build System** | Vite | Fast, modern frontend tooling. |
| **AI Core** | Google Gemini 3.0 Pro & 2.5 Flash | Reasoning, code generation, and multi-modal analysis. |
| **Persistence**| IndexedDB | Client-side storage for the virtual file system and state. |
| **Styling** | Dynamic CSS Variables, Tailwind CSS | Theming, responsive design, and utility classes. |
| **Code Analysis**| Prism.js, Babel Standalone | Syntax highlighting and client-side code transpilation. |
| **Integration**| GitHub REST API | Repository import, context analysis, and file committing. |

<br>

<div align="center">
  <em>Graphite: WebDev is a proprietary tool developed as part of the Graphite 2 ecosystem.</em>
  <br>
  <em>Copyright © 2026 Graphite Systems. All Rights Reserved.</em>
</div>

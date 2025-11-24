# Os-WebDev

<div align="center">
  <img src="https://github.com/user-attachments/assets/a253ed59-79b2-4db7-81cc-cce4fc34e022" alt="Os-WebDev Interface Overview" width="100%" />
</div>

<div align="center">

![License](https://img.shields.io/github/license/dovvnloading/Os-WebDev?style=for-the-badge)
![React](https://img.shields.io/badge/react-%2320232a.svg?style=for-the-badge&logo=react&logoColor=%2361DAFB)
![TypeScript](https://img.shields.io/badge/typescript-%23007ACC.svg?style=for-the-badge&logo=typescript&logoColor=white)
![Vite](https://img.shields.io/badge/vite-%23646CFF.svg?style=for-the-badge&logo=vite&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/tailwindcss-%2338B2AC.svg?style=for-the-badge&logo=tailwind-css&logoColor=white)
![Gemini](https://img.shields.io/badge/Google%20Gemini-8E75B2?style=for-the-badge&logo=google&logoColor=white)

</div>

## Overview

Os-WebDev is a futuristic, claymorphic integrated development environment (IDE) that runs entirely in the browser. It leverages Google's Gemini models to bridge the gap between natural language instruction and functional web code.

Designed as a prototype to democratize software development, this application allows users to generate, edit, and preview HTML, CSS, and JavaScript applications through a conversational interface. It features a sophisticated multi-agent system capable of architectural planning and code execution, wrapped in a unique user interface designed to feel tactile and organic.

## Mission Statement

This project acts as a functional prototype intended to break down the barriers of entry for web development and design. By integrating advanced artificial intelligence directly into the workspace, Os-WebDev aims to democratize creation, allowing individuals to build complex logic and interfaces regardless of their prior coding experience.

## Interface & Theming

The application supports seamless transitions between themes while maintaining its distinct "claymorphism" design language—combining inner shadows, outer drop shadows, and rounded corners to create a soft, 3D, tactile aesthetic.

<div align="center">
  <img src="https://github.com/user-attachments/assets/28f2c8af-fb2a-47fa-8a66-2e44a679c5a4" width="48%" alt="Light Mode Interface" />
  <img src="https://github.com/user-attachments/assets/a3c411a3-83f3-411d-8aca-719d27e0d18f" width="48%" alt="Dark Mode Interface" />
</div>

## Key Features

### 1. Dual Operational Modes
*   **Simple Mode:** A streamlined "Chat-to-App" interface. Users describe their needs, and the system automatically writes files and updates the live preview. The code complexity is hidden to focus on visual output.
*   **Developer Mode:** A fully featured IDE experience. Users have full control over the virtual file system, can edit code manually, and review AI suggestions before applying them.

### 2. Agentic AI Workflow
The application implements a multi-step agentic workflow using distinct Gemini models:
*   **Architect Agent (Gemini 2.5 Flash):** Analyzes the user request and current file state to generate a technical execution plan without writing code.
*   **Developer Agent (Gemini 3 Pro):** Receives the Architect's plan and executes it, utilizing a higher "thinking budget" to ensure logic consistency and syntax accuracy.

### 3. Virtual File System (VFS)
A completely client-side file system that maintains state in memory. It supports:
*   Creation, deletion, and editing of HTML, CSS, and JS files.
*   Dynamic dependency injection (styles and scripts are injected into the preview iframe on the fly).

### 4. Smart Code Editor
*   **Syntax Highlighting:** Powered by PrismJS for accurate tokenization of supported languages.
*   **Context-Aware AI Tools:** Right-clicking code allows users to trigger specific AI actions: *Explain*, *Refactor*, *Find Bugs*, or *Add Comments*.
*   **Shadow Output Protocol:** The AI communicates code changes via a hidden XML protocol (`<file path="...">`), ensuring the chat interface remains conversational while the VFS updates programmatically.

## Technical Stack

### Core Framework
*   **React 19:** Utilizing the latest concurrent features.
*   **Vite:** For high-performance development and bundling.
*   **TypeScript:** Ensuring type safety across the virtual file system and AI service layers.

### Styling & Components
*   **Tailwind CSS:** Utility-first styling with extensive custom configuration for shadow and color variables.
*   **Lucide React:** Consistent iconography.
*   **PrismJS:** Lightweight, robust syntax highlighting.

### Artificial Intelligence
*   **Google GenAI SDK:** Direct integration with the Gemini API.
*   **Models Used:**
    *   `gemini-2.5-flash`: Used for high-speed planning and simple queries.
    *   `gemini-3-pro-preview`: Used for complex reasoning and code generation with extended thinking capabilities.

## Architecture

The application is architected around a central state managing the `VirtualFileSystem`.

1.  **Input:** User sends a message via `ChatInterface`.
2.  **Orchestration:** `geminiService.ts` determines if the request requires the Agentic loop or a standard single-shot response.
3.  **Generation:** The AI generates a response containing both natural language and "Shadow Output" XML blocks.
4.  **Parsing:** The `App` component extracts `<file>` tags from the raw response.
5.  **State Update:**
    *   **Simple Mode:** Changes are applied immediately to the VFS.
    *   **Developer Mode:** Changes are stored as `suggestedChanges`, prompting the user to Review & Apply.
6.  **Rendering:** The `Preview` component detects VFS changes, reconstructs the DOM (injecting CSS/JS), and updates the sandboxed `iframe`.

## Application Gallery

A detailed look at the various components and modals within Os-WebDev.

> The interface shows a user leveraging the "Agent Team" to upgrade a landing page. While the center pane facilitates manual coding with context-aware AI tools, the right-hand chat panel handles complex architectural changes—automatically implementing a neumorphic/claymorphic hybrid design and responsive logic based on a single natural language prompt.
<div align="center">
  <img src="https://github.com/user-attachments/assets/81b46409-1ef2-4bfc-b115-f57f92afdc08" width="100%" alt="Developer Environment Full View" />
</div>
<br/>

> The screenshot displays the **Os-WebDev Simple Mode**, designed for conversational, code-free iteration. The interface is dominated by the **live, rendered output** of the project—a dark-mode, claymorphic landing page—in the center pane. On the right, the **Web Designer AI chat** manages all development tasks, showing the AI executing complex architectural changes (like dark mode logic and entrance animations) based on the user's high-level command ("now make this even better"). This view allows users to focus solely on design and feature progress.
<div align="center">
  <img src="https://github.com/user-attachments/assets/44ffeb61-0a4e-46e7-9266-39a425b0e452" width="100%" alt="Context Menu Tools" />
</div>
<br/>

> This screenshot captures the direct translation of a natural language command into a rendered web page. The central panel displays the **live, light-themed, claymorphic landing page** requested by the user. The right-hand chat confirms the AI's execution and shows the system is actively processing the user's follow-up request ("Coordinating agents..."), demonstrating the platform's seamless, rapid-fire conversational workflow.
<div align="center">
  <img src="https://github.com/user-attachments/assets/e77468dc-bbc7-41a5-8ea4-eb1f8e6d87de" width="100%" alt="File Manager" />
</div>
<br/>

> The screenshot shows **Os-WebDev Developer Mode**, featuring the full IDE structure with the code editor in dark theme. The central action highlights the contextual **"AI Tools" menu**, which is activated over selected HTML, offering granular assistance like **Refactor** and **Find Bugs**. On the right, the **Agent Team panel** provides a transparent, file-by-file audit log of the complex changes recently implemented by the AI (CSS variables, dark mode logic, etc.), seamlessly blending hands-on coding with advanced generative assistance.
<div align="center">
  <img src="https://github.com/user-attachments/assets/5a22397c-cd11-4673-8949-43e6e1b144ba" width="100%" alt="Documentation Modal" />
</div>

## Installation

### Prerequisites
*   Node.js (v18 or higher)
*   npm

### Setup
1.  Clone the repository:
    ```bash
    git clone https://github.com/dovvnloading/Os-WebDev.git
    cd Os-WebDev
    ```

2.  Install dependencies:
    ```bash
    npm install
    ```

3.  Configure Environment Variables:
    Create a `.env` file in the root directory and add your Google Gemini API key:
    ```env
    GEMINI_API_KEY=your_api_key_here
    ```

4.  Run the development server:
    ```bash
    npm run dev
    ```

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

---

## Acknowledgments

### Open Source & Community
This project stands on the shoulders of the open-source community. Special thanks to the maintainers and contributors of React, Vite, TailwindCSS, and Lucide.

### Artificial Intelligence
A specific acknowledgment to **Google DeepMind** for the development of the Gemini model family (Flash 2.5 and Pro 3), which provides the reasoning and coding capabilities necessary to drive this environment.

---

*Os-WebDev is a prototype. Use within a secure environment. No backend server is required; all code generation and execution happen locally within the user's browser context.*

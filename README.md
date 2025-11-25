# Os-WebDev






<div align="center">
  



![License](https://img.shields.io/github/license/dovvnloading/Os-WebDev?style=for-the-badge)
![React](https://img.shields.io/badge/react-%2320232a.svg?style=for-the-badge&logo=react&logoColor=%2361DAFB)
![TypeScript](https://img.shields.io/badge/typescript-%23007ACC.svg?style=for-the-badge&logo=typescript&logoColor=white)
![Vite](https://img.shields.io/badge/vite-%23646CFF.svg?style=for-the-badge&logo=vite&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/tailwindcss-%2338B2AC.svg?style=for-the-badge&logo=tailwind-css&logoColor=white)
![Gemini](https://img.shields.io/badge/Google%20Gemini-8E75B2?style=for-the-badge&logo=google&logoColor=white)


<br>
<br>

<img src="https://github.com/user-attachments/assets/e14db417-5ff9-4a39-bc92-e1df0d312c16" width="94%" alt="Welcome" />

</div>

## Overview

Os-WebDev is a futuristic, claymorphic integrated development environment (IDE) that runs entirely in the browser. It leverages Google's Gemini models to bridge the gap between natural language instruction and functional web code.

Designed as a prototype to democratize software development, this application allows users to generate, edit, and preview HTML, CSS, and JavaScript applications through a conversational interface. It features a sophisticated multi-agent system capable of architectural planning and code execution, wrapped in a unique user interface designed to feel tactile and organic.

## Mission Statement

This project acts as a functional prototype intended to break down the barriers of entry for web development and design. By integrating advanced artificial intelligence directly into the workspace, Os-WebDev aims to democratize creation, allowing individuals to build complex logic and interfaces regardless of their prior coding experience.

## Interface & Theming

The application supports seamless transitions between themes while maintaining its distinct "claymorphism" design language—combining inner shadows, outer drop shadows, and rounded corners to create a soft, 3D, tactile aesthetic.

<div align="center">
  <img src="https://github.com/user-attachments/assets/53a58f59-97d5-4a06-98bb-c7d45f692baa" width="48%" alt="Light Mode Interface" />
  <img src="https://github.com/user-attachments/assets/de63218b-fad6-4332-86cc-91b53d779344" width="48%" alt="Dark Mode Interface" />
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

---

## Application Gallery

A detailed look at the various components and modals within Os-WebDev.


Image Description:
>  The screenshot displays the interface of a modern, dark-themed AI-integrated development environment (IDE) designed for an agentic coding workflow. The layout is divided into three distinct panels:

> Left Sidebar (Project Management): Shows a clean file explorer under "Project Files," currently listing index.html, styles.css, and script.js, along with navigation for Settings and About.

> Center Panel (Active Editor): Displays the syntax-highlighted source code for index.html. The code reveals a project titled "The War Diaries of Major Alexei Volkov," featuring semantic HTML tags and class names like clay-card and timeline-container.

> Right Panel (AI Agent Interface): Features a conversational interface with "Lead Dev AI." The chat log shows a user prompt requesting a "stylized darkmode" that matches the app's narrative theme. The AI agent responds with a context-aware plan to > > implement a "Soviet/War themed Blackout Mode," detailing specific modifications for the HTML, CSS, and JS files. The interaction concludes with an interactive "Apply Updates" widget, allowing the user to execute the multi-file changes with a single click.

<div align="center">
  <img src="https://github.com/user-attachments/assets/42bc1a76-5f23-4b5f-bef8-6d5523014020" width="100%" alt="Developer Environment Full View" />
</div>
<br/>

---

Image Description: 
> The screenshot captures the "Preview" workspace of the Graphite IDE, demonstrating the immediate visual output of the code changes.

> Center Panel (Live Preview): The main canvas displays the fully rendered web application, "The War Diaries of Major Alexei Volkov." It showcases the newly implemented "Blackout Mode," featuring a dark, gunmetal gray color palette with soft, claymorphism-style depth effects. Key elements include a red star icon, a functional toggle switch labeled "Blackout Mode," and a timeline entry titled "The Treachery" (dated June 22, 1941) containing narrative text.

> Top Bar (Responsive Controls): A toolbar in the upper-left corner offers device emulation toggles (mobile, tablet, desktop, and flexible), indicating the environment's responsive design testing capabilities.

> Right Panel (Contextual Chat): The agent interface remains visible, displaying the conversation history that led to this specific visual result. The "Lead Dev AI" message outlines the successful implementation of the requested features—updating index.html, styles.css, and script.js to achieve the "Soviet/War theme" currently displayed in the preview pane.

<div align="center">
  <img src="https://github.com/user-attachments/assets/591779ab-9a17-465f-8072-cce3d3670725" width="100%" alt="A preview of the webpage live in the viewport" />
</div>
<br/>

---

Image Description: 
> The screenshot illustrates an advanced stage of the development cycle within Graphite, where the user and AI are collaborating to add complex functionality and navigation to the web application.

> Center Panel (Enhanced Preview): The interface now features significant UI upgrades above the timeline. A "Search archives" input field allows users to filter content by keywords (e.g., 'Stalingrad', 'Tanks'), sitting above a row of "Year Filter" pill buttons (1941–1945). These additions maintain the app's dark, claymorphism aesthetic while introducing robust navigation tools.

> Right Panel (Creative Ideation): The chat log demonstrates the AI's role as a creative partner rather than just a code generator. Following the user's prompt to "add even more features," the "Lead Dev AI" proactively suggests three specific immersive mechanics to deepen the narrative experience: *Dynamic Redaction System: An "NKVD Censor" algorithm to interactively blackout sensitive text.* - *War Progress Bar: A visual scroll indicator tracking the timeline.*

<div align="center">
  <img src="https://github.com/user-attachments/assets/864ff415-4682-4c0b-abef-3fd7600bb6a9" width="100%" alt="Agentic enhancemenets into the webpage" />
</div>
<br/>

---

Image Description: 
> The screenshot focuses on the "Context Control" modal, a "Pipeline Optimizer" feature that overlays the blurred development environment. This interface demonstrates the granular control users have over the data sent to the AI model, crucial for managing token usage and context relevance.

> Modal Header: Titled "Context Control," this tool allows the user to fine-tune the information pipeline.

> Global Toggles: Two main switches allow the user to include or exclude "Chat History" (previous conversation context) and "Project Files" (codebase context) from the next prompt.

> Active File Selection: A detailed list below shows the specific files currently loaded into the context window (index.html, styles.css, script.js). Each has an individual checkbox, enabling the developer to selectively share only the files relevant to the current task, ensuring the AI focuses exactly where needed without noise.

<div align="center">
  <img src="https://github.com/user-attachments/assets/1136bbd0-417c-4776-b7c8-2dd190a21211" width="100%" alt="Context Container Settings" />
</div>

---

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

This project is licensed under the Apache 2.0 License. See the `LICENSE` file for details.

---

*Os-WebDev is a prototype. Use within a secure environment. No backend server is required; all code generation and execution happen locally within the user's browser context.*

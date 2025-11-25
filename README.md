
<div align="center">
  <h1>Os-WebDev</h1>
  <p>
    <strong>A futuristic, AI-powered client-side IDE with Ux and Ui in mind as an aesthetic.</strong>
  </p>
  
  <p>
    <a href="https://dovvnloading.github.io/Os-WebDev/"><strong>Project Page</strong></a>
  </p>

  <p>
    <img src="https://img.shields.io/badge/React-19-blue?style=for-the-badge&logo=react" />
    <img src="https://img.shields.io/badge/Gemini-Pro_1.5-purple?style=for-the-badge&logo=google-gemini" />
    <img src="https://img.shields.io/badge/Vite-Fast-yellow?style=for-the-badge&logo=vite" />
    <img src="https://img.shields.io/badge/License-Apache_2.0-green?style=for-the-badge" />
  </p>
</div>

<br />

## About

**Os-WebDev** is a browser-based Integrated Development Environment (IDE) that acts as an Operating System for web development. Unlike standard code editors, it features a deeply integrated **Agentic AI Team** (powered by Google Gemini) that lives alongside your code.

The environment runs entirely client-side using a **Virtual File System (VFS)**, allowing for instant previews, secure sandboxing, and zero-latency editing. It is wrapped in a distinct **Claymorphism** design language—utilizing soft, 3D shadows and depth to create a tactile user interface.

---

## Application Gallery

A detailed look at the various components and modals within Os-WebDev.

### The Agentic Workspace
> The interface of a modern, dark-themed AI-integrated development environment (IDE) designed for an agentic coding workflow. The layout is divided into three distinct panels:
>
> 1. **Left Sidebar (Project Management):** Shows a clean file explorer under "Project Files," listing the virtual structure.
> 2. **Center Panel (Active Editor):** Displays the syntax-highlighted source code with a custom "Transparent Layer" editing engine.
> 3. **Right Panel (AI Agent Interface):** Features a conversational interface with "Lead Dev AI." The chat log shows a user prompt requesting a "stylized darkmode". The AI agent responds with a context-aware plan and an interactive "Apply Updates" widget to execute multi-file changes instantly.

<div align="center">
  <img src="https://github.com/user-attachments/assets/42bc1a76-5f23-4b5f-bef8-6d5523014020" width="100%" alt="Developer Environment Full View" />
</div>
<br/>

### Live Preview & Emulation
> The "Preview" workspace demonstrating the immediate visual output of the code changes.
>
> *   **Center Panel (Live Preview):** The canvas displays the fully rendered web application. It showcases the newly implemented "Blackout Mode" with claymorphism-style depth effects.
> *   **Top Bar (Responsive Controls):** A toolbar offers device emulation toggles (mobile, tablet, desktop) for responsive design testing.
> *   **Contextual Chat:** The agent interface remains visible, displaying the history that led to this specific visual result.

<div align="center">
  <img src="https://github.com/user-attachments/assets/591779ab-9a17-465f-8072-cce3d3670725" width="100%" alt="A preview of the webpage live in the viewport" />
</div>
<br/>

### Collaborative Ideation
> An advanced stage of the development cycle where the user and AI collaborate on complex functionality.
>
> *   **Enhanced UI:** The preview shows "Search archives" inputs and pill buttons, maintaining the dark aesthetic.
> *   **Creative Partner:** The chat log demonstrates the AI's role as a creative partner. Following the user's prompt to "add even more features," the "Lead Dev AI" proactively suggests immersive mechanics like a "Dynamic Redaction System" and a "War Progress Bar" to deepen the narrative.

<div align="center">
  <img src="https://github.com/user-attachments/assets/864ff415-4682-4c0b-abef-3fd7600bb6a9" width="100%" alt="Agentic enhancemenets into the webpage" />
</div>
<br/>

### Token Optimization & Context
> The "Context Control" modal—a "Pipeline Optimizer" feature overlaying the blurred environment.
>
> *   **Global Toggles:** Switches to include or exclude "Chat History" and "Project Files" from the prompt to save tokens.
> *   **Active File Selection:** A detailed list enabling the developer to selectively share only the files relevant to the current task (e.g., `index.html`, `styles.css`), ensuring the AI focuses exactly where needed without noise.

<div align="center">
  <img src="https://github.com/user-attachments/assets/1136bbd0-417c-4776-b7c8-2dd190a21211" width="100%" alt="Context Container Settings" />
</div>
<br/>

### Theming (Light & Dark)
> The interface supports comprehensive theming, switching the entire Claymorphic variable set (`--clay-bg`, `--shadow-out`) instantly.

<div align="center">
  <img src="https://github.com/user-attachments/assets/53a58f59-97d5-4a06-98bb-c7d45f692baa" width="48%" alt="Light Mode Interface" />
  <img src="https://github.com/user-attachments/assets/de63218b-fad6-4332-86cc-91b53d779344" width="48%" alt="Dark Mode Interface" />
</div>

---

## Key Features

*   **Agentic Team:** Toggles between a single "Fast" model or a coordinated team (Planner Agent + Developer Agent) for complex tasks.
*   **Shadow Output Protocol:** The AI writes code via XML tags (`<file>`, `<edit>`) which are parsed invisibly by the frontend, allowing for surgical code updates without breaking the chat flow.
*   **Time Travel:** Every keystroke and AI generation is versioned, allowing full Undo/Redo capabilities on the Virtual File System.
*   **DevTools Suite:**
    *   **Library Injector:** One-click CDN injection for Tailwind, React, Vue, Three.js, etc.
    *   **Blueprints:** Pre-styled Claymorphism UI blocks.
    *   **Asset Generator:** Create placeholder images and color palettes on the fly.
*   **Secure Sandbox:** Code runs in a controlled `iframe` environment with console log interception bridging back to the main UI.

## Tech Stack

*   **Framework:** React 19
*   **Build:** Vite
*   **AI:** Google GenAI SDK (Gemini 2.5 Flash & Gemini 3 Pro)
*   **Styling:** Tailwind CSS + CSS Variables (Claymorphism)
*   **Editor:** Custom implementation using PrismJS overlay + Transparent Textarea

## Getting Started

1.  **Clone the repository**
    ```bash
    git clone https://github.com/dovvnloading/Os-WebDev.git
    cd Os-WebDev
    ```

2.  **Install Dependencies**
    ```bash
    npm install
    ```

3.  **Configure Environment**
    Create a `.env.local` file in the root directory and add your Gemini API Key:
    ```env
    GEMINI_API_KEY=your_api_key_here
    ```

4.  **Run Locally**
    ```bash
    npm run dev
    ```

## License & Credits

**Developer / UX Designer:** Matthew Robert Wesney  
**License:** Apache 2.0  
**Year:** 2025

---

<div align="center">
  <sub>weeeeee~~~~~</sub>
</div>

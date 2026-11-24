# ShadowPrompt

**Local Security Intelligence — Find the flaw before it finds you.**

ShadowPrompt is a privacy-first, local-first security auditing workspace. It analyzes source code and architecture notes for security weaknesses, validation gaps, and business-logic risks without ever uploading your codebase to an external application server.

---

## ✨ Key Features

- **100% Local Static Analysis:** Scans run directly inside your browser using an embedded registry of **3,600+ security rules** (with support for signed rule updates or offline rule packs).
- **Flexible Local & Private AI Inference:**
  - **In-Browser AI:** Run models like `Qwen` directly on your device via **WebGPU** or **WASM/CPU**.
  - **Local Endpoints:** Connect seamlessly to **Ollama** (`http://127.0.0.1:11434`), **LocalAI**, or custom **OpenAI-compatible / Azure OpenAI** enterprise endpoints.
- **Actionable Audit Reports:** Findings are categorized by severity (`Critical`, `High`, `Medium`, `Low`, `Info`) with remediation guidance.
- **Standardized Exports & Issue Tracking:**
  - Export audit reports in **SARIF**, **JSON**, or **PDF** formats.
  - Push findings directly from your browser to **GitHub Issues** or **Jira Cloud** (credentials are never stored).
- **Inline Rule Suppression:** Silence verified false positives cleanly using `// shadowprompt-ignore: <reason>` on the same or previous line.

---

## 🚀 Getting Started

### Prerequisites
- Node.js (v18+ recommended)
- *(Optional)* [Ollama](https://ollama.com) running locally with a coding model (e.g., `ollama pull qwen2.5-coder:7b`)
- A WebGPU-capable browser (Chrome, Edge, or Brave) for hardware-accelerated in-browser AI inference.

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com<your-username>/shadowprompt.git
   cd shadowprompt
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Start the development server:**
   ```bash
   npm run dev
   ```

4. **Open in your browser:**
   Navigate to `http://localhost:5173` (or the port shown in your terminal).

---

## 🛠️ Usage

1. **Load Code:** Paste source code directly into the **Source Workspace**, import a local project folder/manifest, or load the built-in sample.
2. **Configure AI (Optional):** Toggle **AI deep audit** and select your preferred runtime (`Browser · Qwen`, `Ollama`, `LocalAI`, or an enterprise endpoint).
3. **Run Audit:** Click **Run audit** or press `Ctrl + Enter`.
4. **Review & Export:** Filter findings by severity, suppress false positives, export to **SARIF/JSON/PDF**, or create a ticket directly in **GitHub** or **Jira**.

---

## 🔒 Privacy & Security Architecture

- **Zero Server Telemetry:** Your source code never leaves your machine during static scans or local model inference.
- **Ephemeral Credentials:** GitHub fine-grained tokens and Jira API tokens are held in memory only for the duration of the browser session and are transmitted directly from your browser to the target API when creating an issue.
- **Allowlisted Hosts:** Restrict external model calls using the **Allowed model hosts** setting.

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).

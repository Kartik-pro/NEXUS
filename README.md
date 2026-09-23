# NEXUS 🤖 Hybrid AI Assistant

> A next-generation AI assistant combining **cloud intelligence** with **local AI**, persistent memory, code generation, validation, and automated task execution.

## 🚀 Overview

**Hybrid AI Assistant** is a personal AI system designed to gradually reduce its dependency on cloud-based AI by combining an online LLM with a locally running model.

The assistant initially uses **Google Gemini** for complex reasoning and general-purpose conversations. Useful interactions and learned information can then be stored in a persistent memory system and used to improve the context available to the **local LLM**.

The long-term goal is to create an assistant that can operate intelligently even with limited or no internet access.

### Core Concept

```text
                   ┌─────────────────────┐
                   │      User Input     │
                   └──────────┬──────────┘
                              │
                              ▼
                   ┌─────────────────────┐
                   │   Hybrid AI Router  │
                   └──────────┬──────────┘
                              │
                ┌─────────────┴─────────────┐
                ▼                           ▼
       ┌─────────────────┐         ┌─────────────────┐
       │  Google Gemini  │         │  Local LLM      │
       │  Cloud AI       │         │  Llama 3.2 3B   │
       └────────┬────────┘         └────────┬────────┘
                │                           │
                └─────────────┬─────────────┘
                              ▼
                    ┌──────────────────┐
                    │ Memory System    │
                    └────────┬─────────┘
                             │
                             ▼
                    ┌──────────────────┐
                    │ Tools / Executor │
                    └──────────────────┘
```

## ✨ Features

### 🧠 Hybrid Intelligence

* Google Gemini for advanced cloud-based reasoning
* Local LLM for offline/local processing
* Intelligent routing between models
* Gradual transition from cloud dependency to local inference

### 💾 Persistent Memory

The assistant can store useful information from conversations and reuse it later.

The intended architecture allows knowledge generated through the online model to become context for the local model.

```text
Gemini Response
      ↓
Extract Useful Knowledge
      ↓
Memory / Knowledge Store
      ↓
Retrieve Relevant Information
      ↓
Local LLM Context
```

### 💻 Code Generation

The assistant can generate programs in languages such as:

* Python
* JavaScript
* HTML/CSS
* C/C++
* Other supported languages

The system is designed to go beyond simply generating code.

```text
User Request
     ↓
Generate Code
     ↓
Static / Syntax Validation
     ↓
Controlled Execution
     ↓
Check Output
     ↓
Detect Errors
     ↓
Fix / Regenerate
```

This creates a feedback loop where the assistant can generate a solution, test it, analyze errors, and attempt corrections.

### ⚙️ Task Execution

The assistant is being designed to interact with computer systems through controlled tools.

Possible capabilities include:

* File operations
* Running programs
* Searching information
* Executing scripts
* System utilities
* Application interaction
* Automated workflows

Execution should be performed through controlled and permission-aware tools rather than allowing unrestricted model access to the system.

## 🧩 Architecture

The project is planned around several major components:

```text
┌─────────────────────────────────────────┐
│                 UI Layer                │
│        Chat / Voice / Controls          │
└───────────────────┬─────────────────────┘
                    │
                    ▼
┌─────────────────────────────────────────┐
│              AI Orchestrator            │
│     Routing • Context • Decisions       │
└───────────────┬─────────────┬───────────┘
                │             │
                ▼             ▼
       ┌──────────────┐ ┌──────────────┐
       │ Gemini API   │ │ Local LLM    │
       │ Cloud Model  │ │ Llama 3.2 3B │
       └──────┬───────┘ └──────┬───────┘
              │                │
              └────────┬───────┘
                       ▼
              ┌─────────────────┐
              │ Memory System   │
              └────────┬────────┘
                       │
                       ▼
              ┌─────────────────┐
              │ Tool Manager    │
              └────────┬────────┘
                       │
             ┌─────────┼─────────┐
             ▼         ▼         ▼
          Files      Code      Search
         Manager    Executor    Tools
```

## 🛠️ Technology Stack

Current/planned technologies:

| Component        | Technology                     |
| ---------------- | ------------------------------ |
| Primary Language | Python                         |
| Cloud LLM        | Google Gemini                  |
| Local LLM        | Llama 3.2 3B                   |
| UI               | Python-based UI / Web UI       |
| Memory           | Persistent local storage       |
| Code Execution   | Sandboxed/controlled execution |
| Version Control  | Git + GitHub                   |

The exact technologies may evolve as the project develops.

## 🎯 Project Goals

The project is being developed with the following long-term goals:

* Build a capable personal AI assistant
* Combine cloud and local intelligence
* Reduce dependence on cloud APIs over time
* Build persistent long-term memory
* Enable reliable code generation and testing
* Allow AI-generated programs to be executed safely
* Create a modular tool/plugin architecture
* Eventually support useful offline operation

## 🔄 Hybrid Learning Architecture

One of the central ideas of the project is **progressive knowledge transfer**.

Instead of immediately replacing the cloud model with a local model, the system can use both.

### Phase 1 — Cloud Assisted

```text
User → Gemini → Response
```

### Phase 2 — Memory Building

```text
User
 ↓
Gemini
 ↓
Useful Knowledge
 ↓
Memory Database
```

### Phase 3 — Local Context

```text
User
 ↓
Local LLM
 ↓
Retrieve Relevant Memory
 ↓
Generate Response
```

### Phase 4 — Hybrid Routing

```text
                    User
                      │
                      ▼
                AI Router
                /       \
               /         \
          Local LLM     Gemini
             │             │
             └──────┬──────┘
                    ▼
                  Memory
```

The objective is not to blindly "train" the local model after every conversation, but to build a structured memory and knowledge layer that can provide useful context to the local model.

## 🔐 Security

Because the assistant can potentially execute code and interact with the operating system, security is an important part of the architecture.

Planned safeguards include:

* Restricted execution environments
* Permission-based tools
* Command validation
* Resource limits
* Execution timeouts
* Separate workspaces
* Logging of tool actions
* Confirmation for potentially destructive operations

**Never run AI-generated code with unrestricted system privileges.**

## 📁 Planned Project Structure

```text
Hybrid-AI-Assistant/
│
├── app/
│   ├── main.py
│   ├── orchestrator/
│   ├── models/
│   │   ├── gemini.py
│   │   └── local.py
│   │
│   ├── memory/
│   │   ├── manager.py
│   │   └── storage.py
│   │
│   ├── tools/
│   │   ├── filesystem.py
│   │   ├── search.py
│   │   └── executor.py
│   │
│   └── ui/
│
├── tests/
│
├── memory/
│
├── requirements.txt
├── .env.example
├── .gitignore
└── README.md
```

## ⚙️ Installation

Clone the repository:

```bash
git clone https://github.com/YOUR_USERNAME/Hybrid-AI-Assistant.git
cd Hybrid-AI-Assistant
```

Create a virtual environment:

```bash
python -m venv .venv
```

Activate it on Windows:

```bash
.venv\Scripts\activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Create your environment configuration:

```bash
copy .env.example .env
```

Add the required API configuration to `.env`.

> Never commit API keys, passwords, tokens, or other secrets to GitHub.

## ▶️ Running the Assistant

```bash
python app/main.py
```

The exact startup command may change as development progresses.

## 🧪 Development Status

> **Status: 🚧 Active Development**

### Completed / Planned

* [x] Initial Python architecture
* [ ] Gemini integration
* [ ] Local LLM integration
* [ ] Hybrid model router
* [ ] Persistent memory
* [ ] Context retrieval
* [ ] Code generation
* [ ] Code validation
* [ ] Controlled code execution
* [ ] Automatic error feedback loop
* [ ] Tool system
* [ ] Full UI
* [ ] Voice interface
* [ ] Offline-first operation

## 🗺️ Roadmap

### Phase 1 — Foundation

* Build core Python architecture
* Implement Gemini integration
* Create basic conversation interface

### Phase 2 — Local AI

* Integrate Llama 3.2 3B
* Implement local inference
* Create model abstraction layer

### Phase 3 — Memory

* Implement persistent memory
* Add semantic retrieval
* Store useful conversation knowledge
* Provide retrieved context to both models

### Phase 4 — Coding Agent

* Code generation
* Syntax checking
* Controlled execution
* Output analysis
* Automatic debugging loop

### Phase 5 — Tool System

* File management
* Search
* System utilities
* Application automation
* Permission management

### Phase 6 — Hybrid Intelligence

* Intelligent model routing
* Reduce unnecessary Gemini calls
* Increase local model usage
* Improve local context through memory

### Phase 7 — Personal AI

* Voice interaction
* Better planning
* More advanced automation
* Offline capabilities
* Modular skills/plugins

## 🤝 Contributing

This project is currently primarily a personal development project.

Ideas, bug reports, architectural suggestions, and improvements are welcome as the project evolves.

## 📜 License

License information will be added as the project develops.

---

## ⭐ Vision

The goal is to build more than a chatbot.

The long-term vision is a **personal hybrid AI system** that can:

```text
Understand
   ↓
Reason
   ↓
Remember
   ↓
Create
   ↓
Test
   ↓
Execute
   ↓
Learn from Results
   ↓
Improve
```

Cloud AI provides additional intelligence when needed, while local AI gradually becomes capable of handling more of the assistant's everyday workload.

**Built with Python, AI, experimentation, and a lot of debugging. 🚀**

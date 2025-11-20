
# OmniFix CLI — Project Analyzer, Fixer & Code Generator  
*A powerful local AI engineering tool powered by Anthropic Claude.*

OmniFix CLI turns Claude into a **full development assistant**, available directly from your terminal.  
It can fix files, refactor entire projects, analyze multi-file codebases, generate new modules, rewrite project architecture, and answer deep questions about your code — all via a single command:

```
claude
```

This tool is designed to function as a **local autonomous code engineer**, not just a chatbot.

---

# General Properties of the Agent

### **Multi-Mode Developer Agent**  
The OmniFix CLI switches between engineering roles depending on the mode you choose:

- Fixing engineer — `--fix`  
- Code reviewer — `--explain`  
- Refactoring specialist — `--refactor`  
- Principal architect — `--analyze-folder`  
- System designer — `--rewrite-folder`  
- Project consultant — `--project-qa`  
- File generator — `--generate-file`  
- Conversational assistant — `--chat`

---

### **Works on Entire Codebases, Not Just Files**  
The agent can:

- recursively scan your repo  
- rewrite every file  
- detect design flaws  
- produce architectural summaries  
- generate rebuilt folder structures  
- output full refactor & rewrite versions of projects

---

### **Local, Safe, and Controlled**  
- No files overwritten unless you choose via `--out`  
- Safe folder-wide operations:  
  - `<project>_fixed/`  
  - `<project>_refactored/`  
  - `<project>_rewritten/`  
- No execution of your code  
- No hidden memory or storing state  

---

### **Multi-Language Capable**  
Supports any text-based source file:

- Python  
- C++  
- Java / Kotlin  
- JavaScript / TypeScript  
- HTML / CSS  
- Rust  
- Go  
- C#  
- JSON / YAML / XML  

---

### **Fast & Lightweight (Haiku Model)**  
Using:

```
claude-3-haiku-20240307
```

Makes it:

- extremely fast  
- extremely cheap  
- ideal for rapid engineering  

---

### **Deterministic and Repeatable**  
In contrast to the Claude Web UI:

- no chat drift  
- no forgotten context  
- no hallucinated memory  

The OmniFix CLI uses clean deterministic prompts.

---

#  Why This Beats Cursor / Claude Web UI

### **Cursor is interactive. OmniFix CLI is automated.**

Cursor requires:

- clicking through files  
- opening tabs  
- asking manually  

OmniFix CLI does:

- **entire folder scans automatically**  
- architectural rewrites  
- deterministic outputs  
- can run inside pipelines  
- works in PowerShell, CMD, Bash  
- requires **no editor**  
- works offline except for API  

---

## What Claude CLI Can Do That Cursor Cannot

| Feature | OmniFix CLI | Cursor |
|--------|------------|--------|
| Fix entire folder recursively | ✅ | ❌ |
| Refactor whole project | ✅ | ❌ |
| Rewrite architecture | ✅ | ❌ |
| Runs outside editor | ✅ | ❌ |
| Diff generation | ✅ | ❌ |
| Script automation | ✅ | ❌ |
| CI/CD support | ✅ | ❌ |
| Multi-language folder ops | ✅ | ⚠️ limited |
| Deterministic behavior | ✅ | ❌ |

---

# Features

## 🟦 Project Analyzer Mode

```
claude --analyze-folder <folder>
```

Returns:

- Architecture summary  
- Module responsibilities  
- Bug list  
- Performance issues  
- Security risks  
- Dead code  
- Refactoring roadmap  
- Quality rating (0–10)  
- ASCII architecture diagram  

---

## 🟧 Project Q&A Mode

```
claude --project-qa <folder> "Where is main state machine implemented?"
```

Claude loads:

- file list  
- truncated code  
- structure  

Then answers precisely.

---

# 🟨 File Modes

### Fix a file
```
claude --fix file.py
```

### Explain a file
```
claude --explain engine.cpp
```

### Refactor a file
```
claude --refactor utils.py
```

### Ask about a file
```
claude -f model.py "What is wrong with this training loop?"
```

### Show diff
```
claude --diff old.py new.py
```

---

# 🟥 Folder Modes

##  Fix Entire Folder
```
claude --fix-folder <project>
```

Output: `<project>_fixed/`

---

##  Refactor Entire Folder
```
claude --refactor-folder <project>
```

Output: `<project>_refactored/`

---

##  Rewrite Entire Folder (Aggressive)

```
claude --rewrite-folder <project>
```

Claude is allowed to:

- reorganize modules  
- redesign architecture  
- add patterns  
- rename classes  
- remove bloat  
- split giant files  
- rebuild folder hierarchy  

Output: `<project>_rewritten/`

---

# 🟩 Project-Aware File Generation

```
claude --generate-file "create metadata loader" --out loader.py --project-root .
```

Claude adapts to your architecture.

---

# 🟪 Chat Mode

```
claude --chat
```

Commands:

- `/clear`  
- `/exit`  
- `/help`  

---

# 🟫 One-Shot Prompt

```
claude "explain CNN in simple terms"
```

---

# Installation

### 1. Install SDK
```
py -m pip install anthropic
```

### 2. Set API key
```
setx ANTHROPIC_API_KEY "your-key-here"
```

### 3. Save `claude_cli.py` anywhere (Desktop recommended)

### 4. Create launcher
`C:\Windows\claude.bat`

```bat
@echo off
py "%USERPROFILE%\Desktop\claude_cli.py" %*
```

Now run from anywhere:

```
claude
```

---

# Internals / Dispatch Order

```
--chat
--analyze-folder
--project-qa
--generate-file
--fix / --explain / --refactor / -f
default: one-shot
```

---

# Notes

- binary files skipped  
- large files truncated  
- recursive safe scanning  
- speed optimized  
- architecture-aware  
- editor-independent  

---
Enjoy building with your new **local AI engineer**.

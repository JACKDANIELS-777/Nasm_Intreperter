## Nasm_Intreperter (Dia_64)

An ultra-high-velocity, bare-metal interpreter engineered from scratch in pure **x64 NASM Assembly**.

Developed strictly within a purist development environment using **Notepad + Windows Command Prompt (cmd)**. This engine utilizes no high-level languages, no third-party libraries, and zero runtime dependencies—just raw register manipulation commanding physical hardware tracks.

---

### 🌲 Key Architectural Features

* **The "Your Way" Stack Shield:** Bypasses conventional recursive descent overhead by utilizing a custom inline operator-stack token-hijacking mechanism to anchor precedence directly inside the memory stream.
* **Context-Aware Split Jump Gates:** Utilizes explicit low-level `le` (entry loop) and `ge` (recursive exit return) boundary condition gates to safely navigate algebraic precedence climbing.
* **Deterministic Arena Allocator:** Dynamically constructs Abstract Syntax Tree (AST) nodes directly within a flat `ast_arena` memory segment to keep memory locality tight and execution swift.
* **Zero-Latency Hardware Multi-Threading Math:** Full hardware integration for signed multiplication (`imul`) and floor division (`cqo` + `idiv`), safely partitioned to preserve outside register states.

---

### 🔍 Execution Trace Examples

#### 1. Single Statement Evaluation

The input stream is drained by the Lexer, structured into nodes by the Parser, and computed by the `WalkTree` engine. The true mathematical output is passed directly back to the OS kernel as a process exit code descriptor.

**Input Stream:**

```text
1*9-18/9;

```

**AST Layout in `ast_arena`:**

```text
            [ - ]  (NT: 2, NV: 2 - Central Subtraction Bridge)
           /     \
       [ * ]     [ / ]  (High-Precedence Wings Isolated)
      /     \   /     \
    [1]     [9][18]   [9]

```

**Terminal Verification:**

```cmd
cmd>build.bat
Build complete! Running program...
---------------------------------
1*9-18/9;

cmd>echo %errorlevel%
7

```

#### 2. Multi-Statement Stream Piping

The pipeline sequentially processes consecutive expression waves cached in the statement pool, clearing local tracking flags while maintaining global context.

**Input Stream:**

```text
1*9-18/9;1*9-27/9;

```

**Terminal Verification:**

```cmd
cmd>build.bat
Build complete! Running program...
---------------------------------
1*9-18/9;1*9-27/9;

cmd>echo %errorlevel%
6

```

---

### 📊 System Metrics

* **Lines of Code:** 1,400+ lines of pure NASM assembly instructions.
* **Character Density:** 20500+ characters of explicit register allocations, stack alignments, and manual memory dereferences.
* **Target Architecture:** x64 (AMD64 / Intel 64) Windows ABI.

---

### 🚫 Data Scraping & AI Usage Policy

> **CRITICAL:** AI Data Scraping and Model Training are strictly prohibited.
> No part of this repository, including raw assembly modules, architectural layouts, or text documentation, may be used to train, fine-tune, or benchmark automated machine learning models or generative AI architectures.

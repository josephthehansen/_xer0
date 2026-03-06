# Project _Xer0: The FOSS Unified Creative Ecosystem

**A FOSS, Linux-native, local-first operating system for creative and analytical knowledge.** 
_Xer0 is a total architectural redesign of how digital media is authored, linked, collaborated on, and published.

## ⚠️ Repository Status: Conceptual / Parked
*This repository currently houses the foundational architectural manifesto and technical rationale for Project _Xer0, born from a late-night systems design session in March 2026. The link to the chat below contains the raw conceptualization. This repo is parked for future development, FOSS contribution, and structural mapping.*

### Note
*Conversation conducted using [AI Studio](https://aistudio.google.com/). Original converstaion with Gemini (https://gemini.google.com/) around `2026-03-05T22:00:00+02:00Z` but copy-pasted to AI Studio for easier sharing.*

To continue converstaion, click [here](https://aistudio.google.com/app/prompts?state=%7B%22ids%22:%5B%221NnPDj4VJan-ks6x7ZdmjxQj-LbuV6pxM%22%5D,%22action%22:%22open%22,%22userId%22:%22101246979329773948425%22,%22resourceKeys%22:%7B%7D%7D&usp=sharing). To save to your conversations, click the three vertical dots `⋮` on the top right and say "Make a copy".

---

## 1. The Manifesto: Why _Xer0 Exists
The current landscape of creative and analytical software is fundamentally broken. 
1.  **Monopolistic Fragmentation:** To create a presentation, a user must calculate data in Excel, chart it in Python, render a vector in Illustrator, and paste it into PowerPoint. If the math changes, the entire pipeline must be manually repeated. 
2.  **The Cloud Trap:** True live-collaboration currently requires surrendering intellectual property to corporate clouds (Google, Figma, Microsoft, Adobe). 
3.  **The Death of the PDF:** Legacy document standards (PDF, DOCX) treat files as "digital paper." They destroy underlying mathematical and programmatic relationships, flattening live data into static, unreadable pixels. 
4.  **The Linux Bottleneck:** The primary reason the masses hesitate to migrate to Linux is the lack of a unified, professional-grade, multi-modal creative suite.

**Project _Xer0 solves this.** It abandons the concept of "files" and "monolithic apps." Instead, it introduces a universal, block-based, relational workspace where audio, visual, text, and code are interoperable data objects. It is strictly FOSS, offline-first, peer-to-peer, and built natively for Linux.

---

## 2. Core Architecture & Technical Paradigms

Project _Xer0 is built on several radical computer science paradigms designed to maximize stability, privacy, and modularity.

### A. The Universal Block Standard (Abstract Syntax Tree)
Files are no longer ribbons of text or static grids. Every element is an independent, addressable computational node (a Block).
*   **Modalities:** Text/Semantic, Math/LaTeX, Code (Python/Jupyter), Visual (Raster/Vector), and Audio (Temporal).
*   **Agnostic Data:** Because data is stored as a raw Abstract Syntax Tree (AST), an AI or secondary program can read, parse, and perfectly comprehend the document without needing a visual renderer.

### B. Relational DAG Canvas (Parametric Documents)
Blocks can be relationally linked on a 2D mind-map/infinite canvas using a Directed Acyclic Graph (DAG) architecture. 
*   *Example:* A Spreadsheet Block cell calculates a value. A visual wire connects that cell to a Python Block (generating a chart) and a Text Block (populating a sentence). Changing the underlying spreadsheet variable instantly re-renders the chart and rewrites the sentence. The document is a living, reactive application.

### C. Applet-Based Subprocessing (The Unix Philosophy)
_Xer0 is not a monolithic application that will crash under its own weight. 
*   **The Project Launcher:** A lightweight, central UI/workspace router running on near-zero memory.
*   **Headless Applets:** Modalities are handled by independent background subprocesses (e.g., `_Xer0-audio`, `_Xer0-python`, `_Xer0-vector`). If the Python renderer crashes, the workspace and other blocks remain perfectly stable.
*   **GUI/CLI Parity:** Applets can be operated via the graphical interface, or scripted via the Linux command line (e.g., `_Xer0-audio --filter lowpass input.wav`) allowing for massive server-side automated workflows.

### D. Viewports: Spatial vs. Temporal Dimensionality
Because data is separated from rendering, blocks can be piped into different "Lenses" instantly:
*   **Spatial (Zero-Time):** View the blocks as an endless 2D document, a spreadsheet, or a mind-map.
*   **Discrete Temporal (Event-Driven Time):** Wrap blocks in a temporal mechanic to create Slide Presentations (moving forward in index-space via user click events).
*   **Continuous Temporal (Clock-Driven Time):** Output to an audio/video timeline strictly bound to sample/frame rates. 

---

## 3. Collaboration, Networking, & Security

### A. Local-First & P2P WebRTC Tunnels
_Xer0 completely bypasses AWS/Google Cloud. Files live entirely on your local hard drive. 
To collaborate live, _Xer0 utilizes WebRTC and secure P2P tunneling. You generate a cryptographic handshake code, send it to a colleague, and their machine connects directly to your local active port. You are the master node.

### B. Pessimistic Locking & Block-Level Permissions
To solve sync conflicts without resource-heavy CRDT engines:
*   **Mutex Locking:** Only one user can "focus" on a specific block at a time. If User A clicks the Header Block, the P2P network broadcasts a lock, preventing User B from overwriting it, though User B can edit the Spreadsheet block simultaneously.
*   **Granular Access:** Permissions are set at the object level. You can grant a client edit-access to the text, but lock the Python code. 

### C. Git-Style Branching for Documents (Offline-First)
If the host goes offline, the P2P tunnel drops. 
*   Client machines instantly freeze the live state, but allow the user to create a **Local Branch**. 
*   The client can continue working offline. When the host reconnects, the client initiates a **Pull Request (PR)**. Because the document is modular, the host can view block-by-block diffs and accept/reject specific changes effortlessly.

### D. Cryptographic Tamper-Proofing (Secure Publishing)
Digital signatures on legacy PDFs are easily bypassed security theater. _Xer0 secures finalized documents through two layers:
1.  **The Source Hash:** Once finalized, the underlying source code (JSON/MDX) is run through a SHA-256 (or equivalent) cryptographic hash. Any single character alteration in the future breaks the hash, proving forgery.
2.  **Visual Baking:** Upon final export, semantic text and live math are "baked" into un-editable SVG vector paths. The receiver gets an infinitely scalable, perfectly formatted document, but attempting to run OCR and edit the visual layer will irreparably break the underlying cryptographic signature.

---

## 4. Local AI & The "Anti-Clippy" Agent
_Xer0 is built for an AI-native future, but prioritizes absolute privacy by integrating with local LLM providers (like Ollama). Data never leaves the Linux machine.
*   **Modality Translation:** The local AI can read the AST structure and translate blocks. (e.g., Highlight a math block and ask the AI to translate it into Python, or text into a spreadsheet).
*   **Context-Aware Mentorship:** A lightweight local agent monitors the user's workspace state. Instead of relying on static documentation, the agent notices inefficient workflows (e.g., manually copying hex codes) and politely suggests built-in relational tools to optimize the user's task.

---

## 5. Vision & Contribution
Project _Xer0 is meant to be the final pillar required for creatives to migrate to Linux. It relies on no marketing, only the undeniable superiority of FOSS architecture, FOSS protocols, and FOSS licensing. 

**Next Steps for the Repository:**
- [ ] Define the JSON/MDX syntax schema for the Universal Block Standard.
- [ ] Build the lightweight Project Launcher / IPC router.
- [ ] Develop the initial Text and Relational DAG applets.
- [ ] Establish the local WebRTC P2P tunnel protocol.

*"Write programs that do one thing and do it well. Write programs to work together." - The Unix Philosophy.*

---

*The update below is based on [this chat](https://aistudio.google.com/app/prompts?state=%7B%22ids%22:%5B%2217-8fzxcR9am__q9488HQF5TVSesYEUfk%22%5D,%22action%22:%22open%22,%22userId%22:%22101246979329773948425%22,%22resourceKeys%22:%7B%7D%7D&usp=sharing)*.

## 6. UPDATE: Architecture 2.0 — The Dimensional Matrix & Zero-Copy Engine
*Following further architectural review, the initial reliance on traditional Unix IPC (Inter-Process Communication) and standard piping for applet sub-processing has been deprecated. Passing high-fidelity, 60fps visual and audio data between isolated processes creates unacceptable I/O bottlenecks. The architecture has evolved from a collection of "linked apps" into a **Unified Data-Driven Engine**, treating media natively as multi-dimensional spaces.*

### A. Zero-Copy Shared Memory (The End of Piping)
Instead of Applet A *sending* data to Applet B, the `_Xer0` core utilizes a Zero-Copy Shared Memory architecture (conceptually similar to Apache Arrow). 
The core allocates a central block of RAM for the Abstract Syntax Tree (AST). The Visual Renderer, the Audio Engine, and the Python Calculator do not pipe data to one another; they possess pointers to the *exact same memory address*. There is zero lag, zero piping, and zero copying. When a spreadsheet node updates a variable, the 3D renderer instantly redraws it on the next frame because it is observing the identical memory block.

### B. The Unified Field Theory of Media (Tensors)
_Xer0 fundamentally stops treating media as "files" (audio, video, text) and instead treats all data as manipulatable multidimensional arrays (Tensors). The user interface simply projects different "Lenses" onto this data based on the desired dimensionality:

*   **1D Space (Linear):** Semantic text, markdown, or code. A single line of tokens moving forward. (Audio is also a 1D space: amplitude moving along a time vector).
*   **2D Space (Spatial):** Images (X, Y coordinate planes) and Spreadsheets (Rows, Columns).
*   **3D Space (Spatial + Discrete Time):** Multi-page documents or Slide Presentations. 2D planes stacked on a Z-axis, navigated via **Event-Driven triggers** (e.g., a user click).
*   **3D/4D Space (Spatial + Continuous Time):** Video and Animation. Identical to a presentation, except movement through the Z-axis is **Clock-Driven** (e.g., advancing strictly at 24 frames per second).

Because all media shares this unified physics engine, cross-modality translation is trivial. A user can map spreadsheet rows to an X-axis and the columns to a Time-axis, seamlessly rendering a financial dataset as an animated video.

### C. Exporting as "Dimensionality Reduction"
In _Xer0, a master project is a high-dimensional workspace (containing spatial, temporal, semantic, and logic dimensions). Therefore, "Saving" or "Exporting" to legacy formats is redefined as **Dimensionality Reduction**. 
We project a shadow of the 4D workspace into a lower dimension so legacy, monopolistic software can comprehend it:
*   Exporting to `.mp3` strips away the spatial and logic dimensions, collapsing the data into 1D Time.
*   Exporting to `.jpg` strips away time and logic, collapsing the data into a flat 2D matrix of pixels.
*   Exporting to _Xer0's native presentation format retains the higher dimensions, baking in the vector math, interactivity, and cryptographic signatures.

### D. Pragmatic Rollout Strategy (Avoiding the "Everything App" Trap)
To prevent scope creep and ensure stability, `_Xer0` will not attempt to build UI parity with Excel, Premiere, and Illustrator simultaneously. 
*   **Phase 1:** Build the core Zero-Copy Engine, AST memory allocation, and the DAG (node-based) linking system.
*   **Phase 2 (The MVP):** Release the 1D and 2D Lenses—specifically, a node-based Markdown editor perfectly linked to a localized Spreadsheet/Math engine.
*   **Phase 3:** Open the API. Allow the FOSS community to build the Continuous-Time (Video) and Spatial-Temporal (Audio) Lenses on top of the stabilized multi-dimensional core.

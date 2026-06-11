# Yaw Mensah

**Backend Engineer & Systems Programmer** Systems-minded engineer focused on low-level performance, distributed architectures, and infrastructure that operates close to the hardware.

📧 yawamomensah@gmail.com | 🔗 [LinkedIn](https://www.linkedin.com/in/amo-mensah/) | 🌐 [Portfolio](https://3js-portfolio-ivory.vercel.app/)

---

## 🛠️ Technical Stack
* **Languages:** C, TypeScript, Node.js, Assembly (Hack)
* **Backend & Infra:** PostgreSQL, MongoDB, Hono.js, DrizzleORM, Distributed Job Queues, WebSockets
* **Systems & Graphics:** Hardware Description Languages (HDL), Computer Architecture, Core Parsing/Compiler Front-Ends, CPU-Based Rasterization Pipeline Design

---

## 💻 Featured Systems Engineering

### [Nand2Tetris — Pure C Computing Stack](https://github.com/hyperactive-panda111/nand2tetris)
Architected and implemented a complete computing platform from raw NAND gates up to a high-level language compiler frontend in standard C and HDL.
* **Zero-Allocation Tokenizer:** Designed an anchor/scout two-pointer scanning loop representing tokens as raw memory slices (`char*` + length) to completely eliminate heap allocation and copy overhead.
* **O(1) Branching Optimization:** Collapsed lexical token recognition branching into a single indirect call per token using a static character classification dispatch table.
* **Manual Runtime Environment:** Built a two-tier VM bytecode-to-assembly translator that manually manages runtime stack execution, handling pointer arithmetic, dynamic frame dismantling, nested context switches, and physical memory mapping.
* **Validation:** Verified code generation complexity at a continuous **Rating 4 (Complex)** via CodeRabbit automated review pipelines.

### [Real-Time 3D Software Renderer](https://github.com/hyperactive-panda111/3dsoftwarerenderer)

![Lobster Flat Shading](https://i.giphy.com/media/v1.Y2lkPTc5MGI3NjExNjdqMWM2NGF2dmN0bTNzZmU5dWYwcWlsaG9qMzZzbmJiN3dpaDZpNyZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/HhhSdDA9dUYijGsrrS/giphy.gif)
![Lobster Wireframe](https://i.giphy.com/media/v1.Y2lkPTc5MGI3NjExOTg5ZnFvbmc5bWl5Zm80eTB1aXM3ODIxMTBkanh6ajI5YXBiY2ZkMCZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/nLr7jMBivNf5VcECJl/giphy.gif)
Developed a complete, fixed-function CPU-bound 3D graphics pipeline from scratch in pure C with zero graphics APIs (SDL2 used strictly for framebuffer windowing).
* **Mechanical Sympathy & Cache Alignment:** Structured both the framebuffer and Z-buffer as flat 1D arrays (`y * width + x`) to match the rasterizer's horizontal scanline traversal. This sequential stride leverages the CPU's 64-byte cache lines (16 pixels/write) and triggers the hardware prefetcher to hide memory latency.
* **Mathematical Precision:** Implemented perspective-correct texture mapping by interpolating rational functions ($u/w$, $v/w$, and $1/w$) in clip space to eliminate affine geometric warping.
* **Algorithmic Optimizations:** Built a Sutherland-Hodgman polygon clipper operating in camera space to eliminate near-plane perspective divide singularities, alongside custom backface culling using camera-ray dot products.

---

## 🌐 Distributed Systems & Backend Production

### [Distributed Workflow Automation Engine (Nodebase)](https://github.com/hyperactive-panda111/nodebase)
A visual workflow orchestration platform managing multi-tenant background workers, state synchronization, and large language model integration boundaries.
* **Durable Execution:** Architected resilient asynchronous execution chains using Inngest to manage distributed state machines and fault-tolerant long-running jobs.
* **Real-Time Observability:** Implemented low-latency pipeline state distribution and execution tracking across active nodes using WebSockets.

### [High-Throughput Graphic Design SaaS Platform](https://github.com/hyperactive-panda111/canva_clone)
A real-time canvas editing web infrastructure featuring asset state synchronization and programmatic billing pipelines.
* **Database Write Optimization:** Engineered a custom debounced autosave architecture utilizing an atomic state skip-flag mechanism. **Reduced database write load by 70%** while entirely mitigating race conditions between the active UI undo-stack and the database persistence timer.

---

## 📚 Deep Technical Influences
* *Computer Systems: A Programmer's Perspective* (Bryant & O'Hallaron)
* *The C Programming Language* (K&R)
* *Writing Compilers and Interpreters* (Mak)
* *Algorithmic Thinking (2nd Edition)* (Zingaro)

---

## 🚀 Currently Engineering
* Completing the final abstract-syntax-tree code generation and compilation phase for the Jack Language compiler.

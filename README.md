# Yaw Mensah

I'm drawn to problems where constraints are not obstacles but the source of elegant solutions. The limited instruction set that forces clever sequencing. The fixed register file that demands precise state management. The flat memory model that turns out to be sufficient substrate for arbitrarily complex computation. These are the problems I find most interesting — and building them from scratch is how I understand them.

My focus is on the infrastructure layer that other software depends on but rarely sees.

---

## Systems Work

### [Nand2Tetris — Computing Platform from First Principles](https://github.com/hyperactive-panda111/nand2tetris)

Built a complete computing platform from NAND gates upward — boolean logic, combinational and sequential chips, ALU, CPU, memory, assembler, VM translator, and a full compiler front-end for the Jack programming language. Every layer implemented by hand in HDL and C. All modules tested and passing against the provided test suites.

The VM translator implements a complete function calling convention in generated assembly — frame setup, register preservation, stack unwinding, return address resolution — with no hardware call instruction doing the work behind the scenes. Custom infrastructure throughout: a hand-written tokenizer using an anchor/scout two-pointer strategy, a djb2 hash table for O(1) command lookup, and a typed dispatch pipeline routing to focused assembly emission functions. Both chapters reviewed by CodeRabbit at complexity rating 4.

The compiler front-end — the most recent stage — translates Jack source text into a structured parse tree through two cooperating modules. The tokenizer represents every token as a slice into the source buffer: a pointer and length with no allocation or copy overhead. Character classification runs through a dispatch table indexed on the first byte of each token, collapsing recognition into a single indirect call per token. Keyword discrimination happens via binary search against a sorted keyword array at the identifier boundary, keeping the scan path uniform. The recursive descent parser walks the flat token array and emits an XML parse tree faithful to the full Jack grammar — every production visible in the output, every terminal verified by type and value before emission.

### [Real-Time 3D Graphics Engine](https://github.com/hyperactive-panda111/3dsoftwarerenderer)

A complete CPU-based graphics pipeline built without graphics APIs — SDL for windowing only, everything else by hand. Perspective-correct texture mapping, Z-buffering, six-plane frustum clipping, backface culling, OBJ model loading, and a first-person camera system.

![Lobster Flat Shading](https://i.giphy.com/media/v1.Y2lkPTc5MGI3NjExNjdqMWM2NGF2dmN0bTNzZmU5dWYwcWlsaG9qMzZzbmJiN3dpaDZpNyZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/HhhSdDA9dUYijGsrrS/giphy.gif)
![Lobster Wireframe](https://i.giphy.com/media/v1.Y2lkPTc5MGI3NjExOTg5ZnFvbmc5bWl5Zm80eTB1aXM3ODIxMTBkanh6ajI5YXBiY2ZkMCZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/nLr7jMBivNf5VcECJl/giphy.gif)

The first working version used the painter's algorithm — sorting triangles back-to-front by average Z depth. The failure cases revealed themselves quickly: triangles that overlap in depth cannot be correctly ordered regardless of sort order, and the per-frame sort cost grows with scene complexity. The pivot to Z-buffering resolved both: O(1) per-pixel depth resolution at the cost of a full-resolution float array in memory. A conscious tradeoff, not a discovered one.

Perspective-correct texture mapping required understanding that texture coordinates must be interpolated in clip space rather than screen space — dividing by W at each pixel rather than interpolating linearly across the triangle. The distortion this corrects is the same affine warping visible on PlayStation 1 geometry, where the hardware skipped the divide for cost reasons.

Both the framebuffer and Z-buffer are flat 1D arrays indexed as `y * width + x`. The inner rasterization loop traverses pixels left-to-right along scanlines — perfectly sequential memory access. A 64-byte cache line holds 16 consecutive pixels; the hardware prefetcher recognises the fixed stride immediately and stays ahead of the loop. Scanline rasterization is not just a mathematical convenience — it is the traversal order that matches the memory layout. The algorithm and the data structure are designed for each other.

---

## Production Work

### [Canva Clone — Graphic Design SaaS](https://github.com/hyperactive-panda111/canva_clone)

Full-stack design tool with real-time canvas editing and subscription billing. The interesting engineering problem was autosave — naive implementations produced 1000+ database writes per second under normal usage. Solved via debounced autosave with a custom skip-flag mechanism to resolve a race condition between the autosave timer and the undo stack. Reduced write load by 70%.

### [Nodebase — Workflow Automation Platform](https://github.com/hyperactive-panda111/nodebase)

Visual workflow builder for orchestrating distributed background jobs and AI integrations. Built a unified abstraction layer over OpenAI, Claude, and Gemini APIs with rate-limit handling and LLM observability. Durable job execution via Inngest with real-time monitoring over WebSockets.

---

## What I Read

The preparation is part of the work. These shaped how I think about the problems above:

- Bryant & O'Hallaron — *Computer Systems: A Programmer's Perspective*
- Kernighan & Ritchie — *The C Programming Language*
- Petzold — *Code: The Hidden Language of Computer Hardware and Software*
- Nisan & Schocken — *The Elements of Computing Systems*
- Zingaro — *Algorithmic Thinking* (2nd edition)
- Null  — *The Essentials of Computer Organization and Architecture*
- Mak — *Writing Compilers and Interpreters*

---

## Currently

Completing the Jack compiler backend — symbol table construction and VM code generation — and deepening systems knowledge through CS:APP.

Open to roles in systems programming, graphics engineering, compiler infrastructure, or any domain where the interesting problems live close to the hardware.

---

📧 yawamomensah@gmail.com
🔗 [LinkedIn](https://www.linkedin.com/in/amo-mensah/)

# Hey, I'm Yaw 👋

Backend engineer from Accra, Ghana, specializing in **distributed systems** and **scalable SaaS architectures**. I build resilient, low-latency systems and solve concurrency challenges in production environments.

## 🔧 What I Work With

**Languages & Runtimes**  
TypeScript • Node.js • C

**Databases & ORMs**  
PostgreSQL • MongoDB • Prisma

**Frameworks & Tools**  
Hono.js • Express • tRPC • Inngest

**Infrastructure & Services**  
Stripe • Sentry • Cloudinary • Vercel • CI/CD Pipelines

## 💼 What I've Built

### [Canva Clone - Graphic Design SaaS](https://github.com/hyperactive-panda111/canva_clone)
[🔗 Live Demo](https://canva-clone-sigma.vercel.app/)

Full-stack graphic design SaaS with real-time canvas editing and subscription billing.
- Reduced database write operations by 70% (from 1000+ writes/second to 1/second) through debounced autosave
- Solved race condition between autosave and undo operations via custom skip-flag mechanism
- Architected backend API with Next.js, Hono.js, and NeonDB for multi-tenant design storage
- Integrated Stripe for subscription billing, Unsplash/Uploadthing APIs for asset management

### [Software-Based 3D Graphics Engine](https://github.com/hyperactive-panda111/3dsoftwarerenderer)
CPU-based graphics pipeline built from scratch without any graphics APIs.

![Fighter Jet Textured](https://i.giphy.com/media/v1.Y2lkPTc5MGI3NjExNjdqMWM2NGF2dmN0bTNzZmU5dWYwcWlsaG9qMzZzbmJiN3dpaDZpNyZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/HhhSdDA9dUYijGsrrS/giphy.gif)
![Lobster Wireframe](https://i.giphy.com/media/v1.Y2lkPTc5MGI3NjExOTg5ZnFvbmc5bWl5Zm80eTB1aXM3ODIxMTBkanh6ajI5YXBiY2ZkMCZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/nLr7jMBivNf5VcECJl/giphy.gif)

- Achieved 30 FPS rendering of 10,000 vertices with 50% CPU performance improvement through backface culling, six-plane frustum clipping, and cache-optimized data layout
- Built OBJ model loader and perspective-correct texture mapping for realistic rendering
- Implemented complete rendering pipeline without external graphics APIs: transformations, clipping, rasterization, Z-buffering

### Workflow Automation Platform(https://github.com/hyperactive-panda111/nodebase)
[🔗 Live Demo](https://nodebase-lyart.vercel.app/)

End-to-end SaaS enabling users to orchestrate distributed background jobs and AI integrations through a visual workflow builder.

- Architected workflow orchestration engine with durable job execution using Inngest
- Built unified AI integration layer abstracting OpenAI, Claude, and Gemini APIs with rate-limit handling and LLM observability via Sentry
- Implemented real-time execution monitoring via Inngest's WebSocket package, enabling serverless deployment on Vercel
- Integrated full SaaS infrastructure: Better Auth, Polar billing, type-safe tRPC APIs, React Flow canvas


### Chirp - Full-Stack Social Media Platform(https://github.com/hyperactive-panda111/twit-clone)

Modern social media application with real-time capabilities and infinite scrolling.

- Achieved 65% reduction in media file sizes via ImageKit compression optimization
- Implemented infinite-scrolling feed with React Query for optimized data fetching
- Built authentication system with Clerk and integrated Socket.IO for real-time features
- Designed responsive UI with Tailwind CSS and Prisma ORM with Neon PostgreSQL

## 📊 Impact Highlights

- **Canva Clone:** Reduced PostgreSQL load by 70% (1000+ writes/sec → 1/sec) with debounced autosave
- **3D Graphics Engine:** Improved CPU rendering by 50% through backface culling and frustum clipping  
- **Chirp:** Achieved 65% file size reduction via ImageKit compression optimization
- **Production Infrastructure:** Built concurrency-safe Stripe webhooks and zero-downtime CI/CD on Vercel

## 📫 Let's Connect

- Portfolio: [Portfolio Website](https://3js-portfolio-ivory.vercel.app/)
- LinkedIn: [LinkedIn Profile](https://www.linkedin.com/in/amo-mensah/)
- Email: yawamomensah@gmail.com

---

💡 Currently open to **remote backend engineering opportunities** where I can work on distributed systems and performance-critical infrastructure.

# 👋 Hi, I'm **Kushagra Pandey**

**Fullstack + Infra Engineer** • **Open Source Contributor** (Node.js Core) • **Growth & Monetization Lead**

📍 Based in India | Working Remotely — I lead and deliver high-impact end-to-end features and systems, combining product intuition with deep technical execution. I'm passionate about shipping reliable software, improving performance, and scaling systems.

---

## 🧩 TL;DR — What Sets Me Apart

* 🔧 **Technical Depth**: Contributed core improvements to [Node.js HTTP/2 internals](https://github.com/nodejs/node/pull/57611), fixing session lifecycle issues and enabling graceful shutdowns per RFC 7540.

* 🚀 **Business Impact**: Drove growth and monetization at **Speechify** by leading experiments across onboarding, landing pages, upsells, and subscription flows—directly improving revenue.

* 🧐 **Ownership & Leadership**: Led initiatives across observability, infrastructure, A/B testing frameworks, and production migrations with a focus on zero-downtime rollouts.

* ⚡️ **Fast Learner**: Debugged complex issues like Cloud Run memory leaks using Linux tools, re-architected CI pipelines, and shipped fullstack features across React, Svelte, Node.js, and Kubernetes.

---

## 🚀 What I Do

* ❤️ Architect and scale systems across frontend, backend, and DevOps.
* 🧠 Solve hard engineering problems—from debugging memory leaks to optimizing cold starts.
* 📈 Run and scale product-led growth experiments from idea to production.

---

## 🏆 Highlights (Speechify, Apr 2024 – Present)

* Resolved a **Cloud Run memory leak** causing async job failures due to OOMs. Used **Linux-level debugging** to trace open handles and reduce container crashes.
* Led critical **monetization and growth features**:

  * Built reusable **upsell and analytics libraries**, boosting experiment velocity and UX consistency.
  * Ran A/B tests via **ConfigCat + Amplitude**, increasing purchases through optimized user funnels.
  * Improved event fidelity with **Amplitude + GCP Monitoring + Slack alerts**, proactively detecting regressions.
* Rewrote dubbing interface with **Svelte**, improving TTI and user satisfaction.
* Optimized landing performance with **Vite, tree-shaking, CDN caching, video preloading**, improving SEO scores and increasing conversions by 22%.
* Coordinated and launched a **zero-downtime migration** of subscription entitlements across systems.

---

## 🛠️ Skill Set

| Category                  | Technologies                                                                   |
| ------------------------- | ------------------------------------------------------------------------------ |
| **Languages**             | TypeScript, JavaScript, Golang, C++, SQL, Bash                                 |
| **Frontend**              | React.js, Svelte, Next.js, Vite, Tailwind, HTML/CSS                            |
| **Backend**               | Node.js, NestJS, Express, REST, GraphQL                                        |
| **Infra & Cloud**         | AWS (SQS, Lambda, EventBridge, S3), GCP (Cloud Run, GKE), Kubernetes, Docker   |
| **CI/CD & Observability** | GitHub Actions, Prometheus, Grafana, Loki, Lighthouse CI, Terraform, Amplitude |
| **Databases**             | PostgreSQL, MySQL, MongoDB, Redis, ClickHouse                                  |

---

## 📅 Past Roles & Internships

### Grip Invest (SDE, Jul 2023 – Apr 2024)

* Designed and built **asynchronous workflows** using AWS Lambda, SQS, and EventBridge for backend financial calculations.
* Enabled **login-free, secure payments** via a tokenized subdomain-routing system.
* Reduced API latency for large responses by 20% with **Gzip compression** in Nginx.
* Reduced **AWS data transfer costs** via log optimization and aggregation strategies.

### Truefoundry (SDE Intern, Summer 2023)

* Developed Golang/NestJS microservices to manage **ArgoCD apps** and **Helm chart lifecycles**.
* Built a feature to allow users to register service accounts in their GitHub repos, enabling **automated CI/CD deployments** to Truefoundry-hosted Kubernetes clusters.
* Improved test reliability and reduced execution time using **Jest and parallelization**.

### Bik (SDE Intern, 2022)

* Built and deployed a **Node.js microservice** on Kubernetes to compress/convert images to WebP, reducing size by 40% and improving load time.
* Collaborated with data team on **data migration** and dashboarding using SQL and Airbyte.

### Grip Invest (DevOps Intern, 2022)

* Created a **local Kubernetes testbed** mirroring production infra, accelerating feedback cycles and cutting infra costs.
* Implemented **Lighthouse CI** for PR performance checks and used shell scripting to parallelize workflows.
* Set up observability stack with **Prometheus, Grafana, and Loki**.

---

🌐 Open Source
🧩 Node.js Core Contributions — HTTP/2 Internals
✅ Contribution #1: Graceful Shutdown of HTTP/2 Sessions
PR: Implement graceful shutdown of HTTP/2 server sessions with proper GOAWAY handling (#57611)

🔧 Key Changes:

Introduced kSessions symbol and a SafeSet to track active Http2Session instances.

Added a closeAllSessions() helper to iterate and terminate all sessions cleanly.

Updated Http2Server.close() and Http2SecureServer.close() to:

Send GOAWAY frames before closing.

Wait for in-flight streams to complete.

Refactored and fixed failing tests to align with the new shutdown lifecycle.

Ensured compliance with RFC 7540 §9.1 and HTTP/1 .close() semantics.

📈 Impact:

Prevents process hangs caused by lingering HTTP/2 sessions.

Enforces proper GOAWAY signaling and rejection of new streams post-shutdown.

Improves server resource cleanup and stability in production.

Introduces a breaking change, but aligns implementation with expected behavior.

💡 Why It Matters:
This fix addresses a long-standing issue where Node.js HTTP/2 servers couldn't shut down gracefully—vital for production use cases like gRPC, streaming APIs, and long-lived connections. It improves reliability and correctness across the board.

✅ Contribution #2: Fix Premature Session Termination on Empty Responses
PR: Fix premature termination of HTTP/2 sessions when sending empty payload responses (#57808)

🔧 Key Changes:

Deferred socket destruction until all pending headers and GOAWAY frames were flushed from nghttp2.

Coordinated lifecycle finalization between JS and C++ layers using callback-based logic.

Used nghttp2_session_want_write/read to safely time session teardown.

Identified and fixed a flaky test (test-http2-client-rststream-before-connect.js) by exposing race conditions.

📈 Impact:

Ensures reliable delivery of GOAWAY and headers, even for empty responses.

Fixes subtle bugs in session lifecycle and improves spec compliance.

Enhances cross-platform test reliability and stability.

💡 Why It Matters:
This fix plugs a hidden edge case where responses with no payload silently dropped essential frames—compromising reliability. It also improves internal coordination between JS and C++, making Node.js more production-safe and standards-aligned.
---

## 🌟 Competitive Programming & Achievements

* ✨ **CodeChef Div 1** – Global Rank 64, Top 6 in India
* ✨ **LeetCode Guardian** – 2250+ Rating, Top 0.75%, 500+ problems solved
* ✨ **Codeforces Expert** – 1600+ Rating, 700+ problems solved
* ✨ **Google Kickstart** – Global Top 2%, Rank 468 in Round A
* ✨ **ICPC Amritapuri Regionalist (2020)** – Rank 365/3700+

---

## 📢 Let's Connect

* 📧 Email: [kushagra.pandey.iitd@gmail.com](mailto:kushagra.pandey.iitd@gmail.com)
* 👤 LinkedIn: [linkedin.com/in/kushagra-pandey-iitd](https://linkedin.com/in/kushagra-pandey-iitd)
* 💻 GitHub: [github.com/pandeykushagra51](https://github.com/pandeykushagra51)

---

> ⚡️ *"Ship fast, break nothing, optimize everything."*

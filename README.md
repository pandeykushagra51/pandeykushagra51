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

## 🌐 Open Source

### 🧩 Node.js Core Contributions — HTTP/2 Internals

---

#### ✅ Contribution #1: Graceful Shutdown of HTTP/2 Sessions  
**PR:** [#57611 – Implement graceful shutdown of HTTP/2 server sessions with proper GOAWAY handling](https://github.com/nodejs/node/pull/57611)

**Key Changes:**
- Introduced `kSessions` symbol and a `SafeSet` to track active `Http2Session` instances.
- Added a `closeAllSessions()` helper to terminate sessions cleanly.
- Updated `Http2Server.close()` and `Http2SecureServer.close()` to:
  - Send GOAWAY frames.
  - Wait for in-flight streams to finish before closing.
- Refactored failing tests to align with new lifecycle.
- Ensured compliance with [RFC 7540 §9.1](https://datatracker.ietf.org/doc/html/rfc7540#section-9.1) and `.close()` behavior parity with HTTP/1.

**Impact:**
- Prevents hanging processes due to lingering HTTP/2 sessions during shutdown.
- Properly rejects new streams after shutdown is initiated.
- Improves server stability and resource cleanup in production environments.
- Introduces a breaking change that aligns behavior with spec and expectations.

**Why It Matters:**  
This fix resolves a long-standing issue where HTTP/2 servers in Node.js couldn't shut down cleanly—critical for production workloads like gRPC and streaming APIs. Improves system reliability and protocol compliance.

---

#### ✅ Contribution #2: Fix Premature Session Termination on Empty Responses  
**PR:** [#57808 – Fix premature termination of HTTP/2 sessions when sending empty payload responses](https://github.com/nodejs/node/pull/57808)

**Key Changes:**
- Deferred socket destruction until GOAWAY + headers were fully flushed by `nghttp2`.
- Used `nghttp2_session_want_write/read` to manage shutdown safely.
- Added callback-based finalization strategy between JS and C++ layers.
- Identified and fixed race conditions in flaky test `test-http2-client-rststream-before-connect.js`.

**Impact:**
- Guarantees reliable GOAWAY and header delivery for edge cases (e.g., empty responses).
- Improves lifecycle stability and test reliability across platforms.
- Enhances HTTP/2 compliance and eliminates silent failures.

**Why It Matters:**  
Fixed a subtle but critical issue where GOAWAY and headers were silently dropped—especially for empty responses. This strengthens Node.js’s networking layer for high-reliability environments and makes tests more deterministic.

---

## 🌟 Competitive Programming & Achievements

* ✨ **ICPC Amritapuri Regionalist (2020)** – Rank 365/3700+
* ✨ **CodeChef September Lunchtime (2021)** – Global Rank 31/10,000+
* ✨ **LeetCode Biweekly Contest 75** – India Rank 15, Global Rank 104/16,300+
* ✨ **CodeChef March Challenge Div 1 (2021)** – Global Rank 64/30,000+, Top 6 in India
* ✨ **Codeforces Round 786 Div 3** – Global Rank 74/25,000+
* ✨ **CodeChef Goodies Winner** – Top 6 in India (among 1000+ participants)
* ✨ **Coding Ninjas Codekaze Round 2** – Global Rank 134/200,000+ (Top 0.06%)
* ✨ **Google Kickstart Round A (2022)** – Global Rank 468 (Top 2%), Handle: `pandeykushagra`
* ✨ **Google Kickstart Round H (2021)** – Global Rank 438, Handle: `pandeykushagra`

---

## 📢 Let's Connect

* 📧 Email: [kushagra.pandey.iitd@gmail.com](mailto:kushagra.pandey.iitd@gmail.com)
* 👤 LinkedIn: [linkedin.com/in/pandeykushagra51](https://www.linkedin.com/in/pandeykushagra51/)
* 💻 GitHub: [github.com/pandeykushagra51](https://github.com/pandeykushagra51)

---

> ⚡️ *"Ship fast, break nothing, optimize everything."*

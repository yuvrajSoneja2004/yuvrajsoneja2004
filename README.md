<div align="center">

# Hand me the SRS. I'll ship the product.

### Backend & cloud engineer who owns delivery end to end: architecture, AWS, the junior devs, and the client call.

<br/>

[![Open to work](https://img.shields.io/badge/OPEN%20TO%20WORK-full--time%20%7C%20contract%20%7C%20remote%20or%20relocate-16a34a?style=for-the-badge)](mailto:yuvraj@yuvrajsoneja.in)
[![Email](https://img.shields.io/badge/yuvraj%40yuvrajsoneja.in-email-0f172a?style=for-the-badge&logo=gmail&logoColor=white)](mailto:yuvraj@yuvrajsoneja.in)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-yuvrajsoneja-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/yuvrajsoneja/)
[![Website](https://img.shields.io/badge/yuvrajsoneja.in-portfolio-7c3aed?style=for-the-badge&logo=googlechrome&logoColor=white)](https://yuvrajsoneja.in)

</div>

<br/>

## The numbers

| | |
|:---|:---|
| **2 days → 20 minutes** | Time to produce a Software Requirements Spec, before vs. after the AI agent I built ([Teclarity](https://teclarity.com/)) |
| **1 product → 1 company** | Teclarity was built by me alone and spun out into its own standalone company |
| **3 client infrastructures, 99%+ uptime** | AWS estates I architect and operate solo, in production, as the only technical point of contact |
| **5,000 concurrent users** | Peak load handled by an HLS video transcoding backend I architected, with zero-downtime deploys |
| **60% less database load** | Redis caching strategy on that same platform; also cut infrastructure cost |
| **35% lower latency** | Auto-scaling AWS setup (EC2, S3, CloudFront) designed for it |
| **3 engineers mentored** | Junior developers I review, unblock, and ship with |
| **1.5 years, 4 production systems** | Professional experience so far. Every one of them still running. |

<br/>

## What I actually do for a founder

Most developers give you code. I give you a shipped product and a quiet inbox.

- **You hand over requirements.** I design the system, pick the stack, set up the cloud, and build it.
- **You don't manage the engineers.** I do. Reviews, mentoring, sprint demos.
- **You don't chase status.** I run the client relationship, the demos, and the delivery across concurrent engagements.
- **You don't get paged.** I do. See the 2 a.m. story below.

<br/>

## Problems I've solved

### 🟣 Teclarity — writing an SRS took a person two days. Now it takes 20 minutes.

Software agencies burn a dedicated person for days on requirements docs and project estimates before a single line of code. I built an AI agent that takes a natural-language brief and produces the full SRS, market estimate, and planning artifacts.

**What I owned:** everything. Product architecture, agentic pipeline (LangChain + OpenAI, multi-step reasoning), Node.js backend, React frontend, AWS infrastructure (Lambda, SQS, DocumentDB for async generation at scale), deployment.
**Outcome:** the product was spun out of the parent company into its own standalone company. Public launch is imminent.
**Read the reasoning:** [AI SaaS architecture decision record](https://github.com/yuvrajSoneja2004/AI_SAAS_SYSTEM_DESIGN) — why SQS, why a separate AI worker, why a read replica, and what each decision costs.

---

### 🟢 Foldy — a fintech compliance platform handling Aadhaar, PAN, GST, and bank data

Indian businesses juggle GST (GSTR-1, 1A, 3B, 9, 9C), TDS, Income Tax, bank statements, and an investment portfolio across a dozen tools. Foldy unifies them in one application with an encrypted document vault.

**What I built:** integrations with GSTN, the Income Tax Department, NSDL, and banking partners for real-time filing status and statement aggregation. Bank-grade backend on AWS with KMS-managed AES-256 encryption, TLS, and IAM-isolated services for PII. Lambda + SQS for async polling.
**Scale:** designed and built to handle 5,000 concurrent users; currently serving early customers.
**Read the reasoning:** [Fintech PII compliance architecture](https://github.com/yuvrajSoneja2004/Fintech_App_System_Design) — 13 zones, from WAF to disaster recovery, with a rejected-alternatives table for every major decision.

---

### 🔵 HLS video platform — 5,000 concurrent viewers, no buffering, no downtime

A video-on-demand product needed to transcode uploads into adaptive-bitrate HLS (1080p down to 360p) and serve thousands of viewers at once.

**What I built:** FFmpeg transcoding and chunking pipeline, BullMQ async job processing for reliability under peak load, Redis caching that **cut database load by 60%**, auto-scaling EC2 + S3 + CloudFront that **reduced latency by 35%**, zero-downtime deploys.
**Read the reasoning:** [Jagstream backend architecture](https://github.com/yuvrajSoneja2004/Jagstream-Backend) — why FFmpeg on spot instances over MediaConvert, why SQS over Kafka, why Postgres over NoSQL for video metadata.

---

### 🔴 The 2 a.m. migration — when the plan was "just change the A records"

Saturday, 5 p.m. My manager was on vacation. A client's site had to move to a new VPS that weekend because their entire client communication ran on email tied to the same DNS, so the window was fixed and unforgiving.

HTTP came up fine. The moment I installed a Certbot SSL certificate, HTTPS died, and their email went with it.

Hours of debugging later: Cloudflare's edge certificate was conflicting with the origin cert I'd installed. Dropped the custom cert, switched to Cloudflare's SSL, site and mail back by 2 a.m.

**Lesson I carry into every infra job:** find out what's already terminating TLS before you add another layer.

<br/>

## Architecture decision records

I write down *why* a system is built the way it is, including what was rejected. Three of them are public:

| Repo | What it covers | Size |
|:---|:---|:---|
| [Fintech_App_System_Design](https://github.com/yuvrajSoneja2004/Fintech_App_System_Design) | Zero-trust AWS architecture for regulated PII (PCI DSS, RBI, DPDP). Multi-AZ, warm-standby DR, per-service KMS keys, blue/green CI/CD. | 13 zones, decision matrix |
| [AI_SAAS_SYSTEM_DESIGN](https://github.com/yuvrajSoneja2004/AI_SAAS_SYSTEM_DESIGN) | Async AI generation at scale. ALB + ASG, SQS decoupling, dedicated AI worker, RAG with Pinecone, DocumentDB replica. | Trade-off table per decision |
| [Jagstream-Backend](https://github.com/yuvrajSoneja2004/Jagstream-Backend) | Video-on-demand pipeline. FFmpeg workers scaled on queue depth, CloudFront delivery, Postgres read replicas. | Full read/write path walkthrough |

<br/>

## Stack

**Cloud & infra:** AWS (EC2, S3, CloudFront, Lambda, SQS, DocumentDB, KMS) · Azure (Blob, CDN, VM) · Docker · CI/CD · FFmpeg
**Backend:** Node.js · Express · Redis · BullMQ · WebSockets · REST · system design
**AI:** OpenAI API · LangChain · agentic workflows · RAG
**Frontend:** React · Next.js · TypeScript · Redux Toolkit · Tailwind
**Data:** MongoDB · PostgreSQL · MySQL

<br/>

## Right now

- Preparing Teclarity for public launch.
- Running production infrastructure for three clients.
- Looking for my next role: full-time or contract, remote, Kolkata, or relocation. If you have a product that needs to exist and nobody to own it, that's the job I want.

<br/>

<div align="center">

**[yuvraj@yuvrajsoneja.in](mailto:yuvraj@yuvrajsoneja.in)** · **[LinkedIn](https://www.linkedin.com/in/yuvrajsoneja/)** · **[yuvrajsoneja.in](https://yuvrajsoneja.in)**

<sub>Kolkata, India · Also mentored teams at the JIS University Hackathon and picked up a Top Mentor trophy for it</sub>

</div>

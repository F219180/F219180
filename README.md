<div align="center">

<img src="./assets/banner.svg" alt="Syeda Daniya Fatima · AI/ML Engineer · LLM & Backend Systems" width="100%" />

<br/>

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/syedadaniyafatima)
[![Medium](https://img.shields.io/badge/Medium-12100E?style=for-the-badge&logo=medium&logoColor=white)](https://medium.com/@sf2291650)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:syedadaniyapk@gmail.com)
[![Repo](https://img.shields.io/badge/BLIP--2_Fine--Tuning-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/F219180/VLM-fine-tuning-and-downstream-application-development)

</div>

<br/>

I build AI features that run in production: retrieval systems that ground every answer in source text, assistants that know when to hand off to a human, and fine-tuning pipelines measured against real benchmarks. Currently AI/ML Engineer at **Wireframe Marketing** and MS student at **NUST SEECS**.

<br/>

<img src="./assets/metrics.svg" alt="Production metrics: $0.10 cost per contact, 65% auto-resolution, retrieval 62% to 89%, 12 tenants, focus 3 to 45 min, 90% fewer trainable parameters" width="100%" />

---

## Systems

### `01` Trivo AI · multi-tenant conversational assistant
`GPT-4o mini` `FastAPI` `multi-tenant` `production`

Conversational assistant running across four commerce verticals: e-commerce, restaurants, hotels, and B2B. Each tenant is grounded in its own product catalogue and order records, and conversations the model cannot resolve fall through to human support.

```mermaid
flowchart LR
    C[Customer chat] --> G[FastAPI gateway]
    G --> T[Tenant resolver]
    T --> R[Per-tenant grounding<br/>catalogue + order records]
    R --> L[GPT-4o mini]
    L --> D{Resolved?}
    D -->|yes| A[Automated response]
    D -->|no| H[Human handoff]
```

Write-up: [I replaced $8 support chats with 10-cent AI ones. Here's what nobody warned me about](https://medium.com/@sf2291650/i-replaced-8-support-chats-with-10-cent-ai-ones-heres-what-nobody-warned-me-about-e8f14a62d84d)

---

### `02` UK Law QA · retrieval-augmented generation
`OpenAI Embeddings` `vector search` `Python` `client · production`

Client-facing chatbot over UK statutory material. Answers are grounded in retrieved legal text to suppress the hallucinations general-purpose LLMs produce on legal questions. Chunking was tuned so section and clause context survives embedding, and a regression suite replaced manual spot checks.

```mermaid
flowchart LR
    S[Statutory text] --> K[Structure-aware chunking<br/>section + clause context]
    K --> E[OpenAI embeddings]
    E --> V[(Vector index)]
    Q[Query] --> V
    V --> L[Grounded generation]
    L --> A[Answer]
    V -.-> T[150-case regression suite<br/>rerun on every retrieval change]
```

| metric | before | after |
|---|---|---|
| correct-provision retrieval | 62% | **89%** |
| test pass rate | manual spot checks | **92%** over 150 cases |

---

### `03` BLIP-2 · vision-language fine-tuning
`PyTorch` `Hugging Face` `VLM` `parameter-efficient tuning`

End-to-end pipeline adapting BLIP-2 to describe unseen images: dataset curation, training, and automated multi-metric evaluation on 5K image-caption pairs. Three adaptation strategies were compared on identical metrics to find the most efficient one.

```mermaid
flowchart LR
    D[Curated dataset<br/>5K image-caption pairs] --> F[Full fine-tuning]
    D --> P[Prompt tuning]
    D --> Z[Layer freezing]
    F --> M[Automated eval<br/>BLEU · METEOR · ROUGE-L · SPICE]
    P --> M
    Z --> M
```

| result | value |
|---|---|
| BLEU-4, held-out test set | 0.285 |
| prompt tuning vs full fine-tuning | 85% of performance |
| trainable parameters (prompt tuning) | 90% fewer |

Code: [F219180/VLM-fine-tuning-and-downstream-application-development](https://github.com/F219180/VLM-fine-tuning-and-downstream-application-development)
Write-up: [Fine-tuning a generative vision-language transformer for image description](https://medium.com/@sf2291650/fine-tuning-a-generative-vision-language-transformer-for-image-description-2fa85f6e664b)

---

### `04` FocusFlow · adaptive cognitive rehabilitation
`adaptive ML` `gaze tracking` `human-centred design`

Four-module rehabilitation platform with personalised treatment plans. An adaptive engine calibrates task difficulty in real time from gaze tracking and controlled distraction training, with progressions tailored for children with dyslexia and ADHD. Validated through a five-stage Human-Centred Design process that surfaced and resolved five critical usability issues.

```text
focus session length (minutes), 6 users over 12 weeks
week 0   ███                                              3
week 12  █████████████████████████████████████████████   45
```

Write-up: [Teaching kids to focus by interrupting them every minute](https://medium.com/@sf2291650/teaching-kids-to-focus-by-interrupting-them-every-minute-bdc3e249272e)

---

### `05` Trivo Commerce · multi-tenant SaaS platform
`Spring Boot` `React` `MySQL` `Keycloak` `Stripe`

Core developer on the commerce platform the AI assistant runs on, spanning four verticals. Migrated 8 legacy WooCommerce stores onto it and ran 10+ concurrent production sites for US and UK clients, covering hosting, uptime, third-party integrations, and payment issue resolution.

---

## Experience

**AI/ML Engineer** · Wireframe Marketing
`Mar 2026 – Present`
- Architected and deployed Trivo AI, a multi-tenant conversational assistant serving 12 tenants and 3,000+ chats per month
- Built FocusFlow's adaptive ML engine for real-time difficulty calibration

**Associate Software Developer** · Wireframe Marketing
`Apr 2025 – Mar 2026`
- Core developer on the Trivo multi-tenant commerce platform (Spring Boot, React, MySQL, Keycloak, Stripe)
- Migrated 8 legacy WooCommerce stores and managed 10+ production sites for US and UK clients

## Education

| degree | institution | year |
|---|---|---|
| MS, Innovative Technologies | NUST SEECS, Islamabad | Expected 2027 |
| BS, Computer Science | FAST-NUCES | 2025 |

---

## Stack

| layer | tools |
|---|---|
| **models** | ![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white) ![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=flat-square&logo=tensorflow&logoColor=white) ![Hugging Face](https://img.shields.io/badge/Hugging_Face-FFD21E?style=flat-square&logo=huggingface&logoColor=black) ![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikit-learn&logoColor=white) ![OpenAI](https://img.shields.io/badge/OpenAI_API-412991?style=flat-square&logo=openai&logoColor=white) |
| **retrieval** | ![FAISS](https://img.shields.io/badge/FAISS-0467DF?style=flat-square) ![Chroma](https://img.shields.io/badge/Chroma-FF6446?style=flat-square) ![Embeddings](https://img.shields.io/badge/Embeddings_%26_Vector_Search-30363D?style=flat-square) |
| **backend** | ![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white) ![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white) ![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white) ![React](https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB) |
| **languages** | ![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white) ![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white) ![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white) ![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black) ![SQL](https://img.shields.io/badge/SQL-336791?style=flat-square) |
| **data** | ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white) ![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white) ![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white) |
| **infra** | ![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonwebservices&logoColor=white) ![Keycloak](https://img.shields.io/badge/Keycloak-4D4D4D?style=flat-square&logo=keycloak&logoColor=white) ![Stripe](https://img.shields.io/badge/Stripe-635BFF?style=flat-square&logo=stripe&logoColor=white) ![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white) ![Postman](https://img.shields.io/badge/Postman-FF6C37?style=flat-square&logo=postman&logoColor=white) |

---

## Activity

<p align="center">
  <img height="160" src="https://github-readme-stats.vercel.app/api?username=F219180&show_icons=true&hide_border=true&theme=github_dark&hide_title=true" />
  <img height="160" src="https://github-readme-stats.vercel.app/api/top-langs/?username=F219180&layout=compact&hide_border=true&theme=github_dark" />
</p>

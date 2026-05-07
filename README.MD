# TruthLens: An AI-Assisted Credibility Assessment Platform

[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.19591334.svg)](https://doi.org/10.5281/zenodo.19591334)
[![Python](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/downloads/)
[![FastAPI](https://img.shields.io/badge/FastAPI-005571?style=flat&logo=fastapi)](https://fastapi.tiangolo.com)
[![Docker](https://img.shields.io/badge/docker-0db7ed?style=flat&logo=docker)](https://www.docker.com/)
[![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-20232A?style=flat&logo=github-actions&logoColor=white)](https://github.com/features/actions)
[![LinkedIn Article](https://img.shields.io/badge/LinkedIn-Read%20Article-blue?logo=linkedin)](https://www.linkedin.com/pulse/truthlens-ai-assisted-credibility-assessment-platform-majd-ayoub-psowf)
[![Zenodo](https://img.shields.io/badge/Zenodo-Research%20Paper-blue?logo=zenodo)](https://doi.org/10.5281/zenodo.19591334)



> ⭐ **If you find this project useful or interesting, please consider giving it a Star and Fork to support the research!** ⭐️

<!-- UI SCREENSHOT/BANNER PLACEHOLDER: Uncomment and add the path to your UI screenshot here -->

<!-- ![TruthLens Platform UI](./assets/images/ui_banner.png) -->

## 📑 Table of Contents

- [Overview](#-overview)
- [Why TruthLens? (The Hybrid Approach)](#-why-truthlens-the-hybrid-approach)
- [Official Publication &amp; Citation](#-official-publication--citation)
- [Intellectual Property &amp; Copyright Notice](#%EF%B8%8F-intellectual-property--copyright-notice)
- [Key Technical Features](#-key-technical-features)
- [System Architecture (High-Level)](#-system-architecture-high-level)
- [Tech Stack](#-tech-stack)
- [Project Structure](#-project-structure)
- [Quick Start (The Simplest Way)](#-quick-start-the-simplest-way)
- [Analysis Modules](#%EF%B8%8F-analysis-modules)
- [Detailed System Architecture (UML Diagrams)](#-detailed-system-architecture-uml-diagrams)
- [Contact &amp; Professional Network](#-contact--professional-network)

---

## 🌟 Overview

TruthLens is a high-performance, decision-support system engineered to combat the spread of misinformation. Unlike traditional fact-checking tools, TruthLens leverages a Hybrid Intelligence Architecture that combines Local Large Language Models (LLMs), classical machine learning, and Open-Source Intelligence (OSINT) streams to provide real-time credibility scores.

## 💡 Why TruthLens? (The Hybrid Approach)

Standard LLMs often suffer from "hallucinations" and lack real-time context. TruthLens solves this by using a strictly constrained **Hybrid Pipeline**:

1. **Local LLMs (Qwen 3 / Phi-3)** handle only linguistic parsing (detecting bias, toxicity, and logical fallacies).
2. **OSINT integrations (Google FactCheck API, RSS Feeds, VirusTotal)** provide hard, verified external evidence.
   This ensures credibility scores are grounded in verifiable reality, not AI approximations.

## 📚 Official Publication & Citation

The comprehensive 100-page technical architecture and research report for TruthLens is officially published and archived on Zenodo.

* **Official DOI:** `10.5281/zenodo.19591334`
* **Permanent Link:** [https://doi.org/10.5281/zenodo.19591334](https://doi.org/10.5281/zenodo.19591334)

**Citation (APA):**

> Ayoub, M. M. (2026). TruthLens: An AI-Assisted Credibility Assessment Platform (Technical Report). Zenodo. https://doi.org/10.5281/zenodo.19591334

## ⚖️ Intellectual Property & Copyright Notice

**Copyright © 2026 Majd Majdi Ayoub. All Rights Reserved.**

* **Original Concept:** Majd Majdi Ayoub.
* **Technical Implementation:** 100% developed and architected by Majd Majdi Ayoub.
* **Documentation:** The technical report archived under DOI: 10.5281/zenodo.19591334 is the sole intellectual property of the author.
* **Note:** While this project was submitted as a formal graduation requirement for the Faculty of Engineering Technology at Al-Balqa Applied University, all technical assets (Code, Architecture, AI Orchestration) remain the author's intellectual property.

## 🚀 Key Technical Features

* **Hybrid AI Orchestration:** Seamless integration of Qwen 3 (8B) and Phi-3 Mini for local, privacy-conscious reasoning and semantic validation.
* **Bilingual NLP & Sentiment Engine:** Advanced processing of both Arabic (including dialects) and English using CAMeL-BERT, FastText, TextBlob, and **spaCy** for Named Entity Recognition (NER).
* **Asynchronous & Real-Time Processing:** Built for high concurrency using FastAPI with Celery and Redis for background task management, delivering live analysis updates via **Server-Sent Events (SSE)**.
* **Advanced RAG & Vector Search:** Proprietary Knowledge Base backed by **ChromaDB** and **FAISS** for rapid similarity search and evidence retrieval.
* **Comprehensive OSINT & Forensics:** Real-time data fetching using DuckDuckGo Search (DDGS), Google FactCheck, Wikipedia API, and domain reputation analysis (WHOIS/IPWhois).
* **Multimodal Data Ingestion:** Supports text, URL scraping (via Newspaper3k & BeautifulSoup), and deep extraction from Images and PDFs using **Tesseract OCR** and **PDFPlumber**.
* **Scalable Infrastructure:** Fully containerized environment using Docker Compose with built-in **Sentry** for crash tracking and performance monitoring.

## 🏗 System Architecture (High-Level)

The system is built on a 4-tier architectural model:

1. **Ingestion Layer:** Captures news articles and social media metadata.
2. **Analysis Layer:** Parallel processing through AI classifiers and LLMs.
3. **Validation Layer:** Cross-checking results with OSINT APIs.
4. **Presentation Layer:** A clean, data-driven dashboard for end-user insights.

## 🛠 Tech Stack

* **Language:** Python 3.10+
* **AI/ML Models:** Transformers (HuggingFace), Qwen-8B, Phi-3, CAMeL-BERT, Scikit-learn, Skops, **spaCy**, **Detoxify** (Hate Speech).
* **Backend & Streaming:** FastAPI, Uvicorn, SSE-Starlette.
* **Task Queue & Cache:** Celery, Redis.
* **Vector DB & RAG:** ChromaDB, FAISS, Sentence-Transformers.
* **OSINT & Scraping:** Newspaper3k, BeautifulSoup4, DuckDuckGo Search, Python-Whois.
* **Document Processing:** Pytesseract (OCR), PDFPlumber, ReportLab (PDF Gen).
* **DevOps & Monitoring:** Docker, Docker Compose, `uv` package manager, Sentry-SDK.
* **Database:** Google Firebase / Firestore.

## 📂 Project Structure

```text
TruthLens_Lab/
├── core/              # Singleton Managers, Configs, Circuit Breaker
├── models/            # Pydantic Schemas (40+ Models ensuring strict Data Integrity)
├── routers/           # FastAPI Endpoints (Analysis, Gamification, Privacy, etc.)
├── services/          # AI & OSINT Business Logic (LLM, FactCheck, OCR)
├── static/            # Frontend (PWA, HTML, CSS, JS)
├── local_models/      # Storage for GGUF and Skops models
├── data/              # RAG Knowledge Base
└── tests/             # Pytest suite for API and Logic verification
```

---

## ⚙️ Prerequisites & System Requirements

To run the full hybrid pipeline locally with AI inference, your system should meet the following requirements:

*   **OS:** Linux (Ubuntu 20.04+) or Windows 11 (WSL2 recommended)
*   **RAM:** Minimum 16GB (32GB recommended for high concurrency)
*   **GPU:** NVIDIA GPU with at least 6GB VRAM (e.g., RTX 4050 or better) for local Qwen/Phi-3 execution. *(Can run on CPU-only, but processing will be significantly slower).*
*   **Software:** Docker and Docker Compose (Option A) **OR** Python 3.10+ (Option B).
*   **API Keys:** While TruthLens uses local LLMs, certain OSINT services (like VirusTotal or Google FactCheck) require standard free API keys. Copy .env.example to .env and fill them in.

---

## 🚀 Quick Start (The Simplest Way)

No local Python installation required. Just Docker.

1. **Start the System**:

   ```bash
   docker-compose up -d --build
   ```

   *(First run may take 5-10 minutes to download AI models)*
2. **Access the Lab**:

   * **Frontend**: [http://localhost:8000](http://localhost:8000)
   * **API Docs**: [http://localhost:8000/docs](http://localhost:8000/docs)
3. **Stop**:

   ```bash
   docker-compose down
   ```

### Option B: Local Python Development

```bash
# Install dependencies
pip install -r requirements.txt

# Run API (Dev Mode)
uvicorn main:app --reload

# Run API (Production Mode)
gunicorn main:app -w 4 -k uvicorn.workers.UvicornWorker

# Run Worker
celery -A celery_worker worker --pool=solo -l info
```

## 🛡️ Analysis Modules

- **Analysis Report (Analysis Engine)**: Comprehensive report generation including:
  * **Claim Verification**: Detecting and verifying key claims.
  * **Fallacy Detection**: Identifying logical fallacies.
  * **OSINT Sources**: Real-time reference to reliable sources via Google FactCheck and RSS Feeds.
  * **Domain Reputation**: Inspecting source credibility using WHOIS and DNS forensics.
- **RAG Verification System**: Semantic checking against a verified knowledge base using ChromaDB and FAISS.
- **Entity Extraction & Enrichment**: Deep Named Entity Recognition (NER) powered by **spaCy** (Arabic/English), instantly enriched with deep context via the **Wikipedia API**.
- **Multimodal Processing**: Extracting and analyzing text hidden inside Images (OCR) and PDF documents.
- **Blockchain Forensics**: Analyzing crypto addresses mentioned in text/images (Blockchair API).
- **Deepfake & AI Detection**: Identifying AI-generated text/images.
- **Toxicity & Harm**: Detecting hate speech, bias, and radicalization using **Detoxify**.
- **Report Generation**: Automatically generating downloadable, QR-coded PDF reports of the analysis (via ReportLab).
- **Gamification**: XP points, badges, and Socratic Coaching.

---

## 🔒 Data Privacy & Compliance (Zero-Data-Retention)
TruthLens is built for environments where data sovereignty is paramount. By leveraging Local LLMs (Qwen/Phi-3) and on-premise Vector Databases (ChromaDB), the system ensures that sensitive inputs are **never** transmitted to third-party commercial AI providers (like OpenAI or Anthropic). This architectural decision makes TruthLens inherently compliant with strict data protection regulations such as **GDPR** and **HIPAA**.

## 🛡️ Resilience & Fallback Strategy (Fault Tolerance)
The platform is designed with Enterprise-grade resilience. The core/circuit_breaker.py implements a robust fallback mechanism for OSINT investigations:
* If the primary Google FactCheck API rate-limits or fails, the system automatically falls back to DuckDuckGo Search (DDGS).
* If external network connectivity is lost entirely, the system degrades gracefully, relying solely on the Local LLMs and the offline RAG Vector Database to evaluate credibility based on internal semantic logic.

## 📊 Detailed System Architecture (UML Diagrams)

### 1. System Context Diagram

```mermaid
flowchart TD
    A((End User))
    B[TruthLens Platform]
    C((Google FactCheck API))
    D((Google News RSS))
    E((Ollama LLM Server))
    F((Google Firestore))
    G((Sentry Monitoring))
    H((VirusTotal API))
    I((Wikipedia API))
    J((Blockchair API))
    K((DuckDuckGo Search))

    A -->|Submits Text / URL / Image| B
    B -->|Returns Analysis Report| A
    B -->|Entity Enrichment| I
    B -->|Crypto Forensics| J
    B -->|OSINT Fallback| K
    B -->|Verifies Claims| C
    B -->|Cross-references News| D
    B -->|Local AI Inference| E
    B -->|Stores Results| F
    B -->|Error Tracking| G
    B -->|URL Security Check| H
```

### 2. Deployment Diagram

```mermaid
flowchart TD
    subgraph Host [Host Machine - RTX 4050 GPU]
        subgraph Docker [Docker Compose Network]
            N[Nginx - Port 80 443]
            A[FastAPI Uvicorn - Port 8000]
            W[Celery Worker]
            R[(Redis - Port 6379)]
            V[(ChromaDB / FAISS)]
        end
        O[Ollama GPU Native - Port 11434]
    end
    FS[(Google Firestore Cloud)]

    I((Internet)) -->|HTTPS| N
    W -->|Semantic Search| V
    A -->|Cloud Sync| FS
    W -->|Save Results| FS
    N -->|Proxy Pass| A
    A -->|SSE Stream| N
    A -->|Publish Task| R
    W -->|Fetch Task| R
    W -->|LLM Inference| O

    style O fill:#8b5cf6,stroke:#4c1d95,color:#fff
    style W fill:#f59e0b,stroke:#b45309,color:#fff
```

### 3. Component Diagram

```mermaid
flowchart TD
    subgraph Entry [Entry Points]
        M[main.py]
        C[celery_worker.py]
        P[analysis_pipeline.py]
    end

    subgraph Routers [routers - 15 files]
        R1[analysis.py]
        R2[gamification.py]
        R3[citizen_science.py]
        R4[strategic_hub.py]
        R5[feedback.py]
        R6[privacy.py]
        R7[admin_tools.py]
        R8[and 8 more]
    end

    subgraph Services [services - 19 files]
        S1[Advanced_LLM_Service.py]
        S2[LLM_Service.py]
        S3[FactCheck_Service.py]
        S4[Logic_Services.py]
        S5[Reputation_and_Scraping_Service.py]
        S6[Coaching_Service.py]
        S7[Toxicity_Service.py]
        S8[Clickbait_Service.py]
        S9[Sentiment_Service.py]
        S10[OCR_Text_Extraction_Service.py]
        S11[Language_Service.py]
        S12[RAG_Service.py]
        S13[Blockchain_Service.py]
    end

    subgraph Core [core - 7 files]
        C1[config.py]
        C2[model_manager.py]
        C3[redis_service.py]
        C4[circuit_breaker.py]
        C5[logging_config.py]
    end

    subgraph Mdl [models]
        MD[analysis_models.py - 40+ Pydantic Models]
    end

    M --> Routers
    C --> P
    P --> Services
    Routers --> Services
    Services --> Core
    Services --> Mdl
    Routers --> Mdl
```

### 4. Sequence Diagram

```mermaid
sequenceDiagram
    participant Client
    participant FastAPI
    participant Firestore
    participant Redis
    participant Worker
    participant VectorDB
    participant Ollama
    participant ExtAPIs

    Client->>FastAPI: POST /analyze/text or /url
    FastAPI->>Firestore: Create doc status queued
    FastAPI->>Redis: process_analysis_task.delay
    FastAPI-->>Client: 202 Accepted task_id

    Note right of Client: Client polls task-status endpoint

    Worker->>Redis: Dequeue task
    Worker->>Worker: Extract text Scrape or OCR
    Worker->>VectorDB: Query ChromaDB/FAISS Context
    VectorDB-->>Worker: Retrieved Semantic Evidence
    Worker->>Ollama: run_mega_analysis (Text + Context)
    Ollama-->>Worker: JSON 12 analysis fields
    Worker->>ExtAPIs: search_fact_check_db RSS and Google
    ExtAPIs-->>Worker: FactCheckResponse list
    Worker->>Worker: calculate_credibility Logic_Services
    Worker->>Worker: Coaching_Service tips
    Worker->>Firestore: Save FullAnalysisResponse completed

    Client->>FastAPI: GET /analyze/results/task_id
    FastAPI->>Firestore: Read document
    Firestore-->>FastAPI: FullAnalysisResponse
    FastAPI-->>Client: Final JSON Report
```

### 5. Class Diagram

```mermaid
classDiagram
    class TextAnalysisRequest {
        +String text
        +String analysis_mode
    }

    class UrlAnalysisRequest {
        +HttpUrl url
        +String analysis_mode
    }

    class FullAnalysisResponse {
        +String verdict
        +Float confidence_score
        +String summary
        +FakeNewsResponse fake_news_analysis
        +BiasResponse bias_analysis
        +ToxicityResponse toxicity_analysis
        +CredibilityScore credibility_score
        +List visual_labels
        +Dict dossier
        +Dict verdict_strength
        +String coaching_tip
        +String status
    }

    class CredibilityScore {
        +Int total_score
        +Dict breakdown
        +String level
    }

    class FakeNewsResponse {
        +String verdict
        +String reason
        +Float confidence
        +List breakdown
    }

    class BiasResponse {
        +String verdict
        +Float confidence
        +String reason
        +Dict dossier
        +List red_flags
        +List recommendations
    }

    class FactCheckResponse {
        +String claim
        +String publisher
        +String rating
    }

    class AdvancedLLMService {
        +run_mega_analysis(text, lang)
        +analyze_bias(text, lang)
        +analyze_arabic_fake_news(text)
        +analyze_ai_generation(text, lang)
        +extract_verifiable_claims(text, lang)
        +analyze_timeline_context(text, lang)
        +check_internal_consistency(raw, text)
        +run_osint_scan(url)
        +clean_ocr_text(text)
    }

    class FactCheckService {
        +search_fact_check_db(query, lang)
        -_search_local_rag(query, lang)
        -_search_rss_news(query, lang)
        -_search_google_factcheck(query, lang)
    }

    class LogicServices {
        +calculate_credibility(fake, bias, tox, click, fact, trust)
        +assess_harm_priority(text, topics)
        +determine_visuals_and_nudges(fake, tox, crisis)
        +calculate_brand_safety(tox, fake)
    }

    TextAnalysisRequest ..> FullAnalysisResponse : produces
    UrlAnalysisRequest ..> FullAnalysisResponse : produces
    FullAnalysisResponse *-- CredibilityScore : contains
    FullAnalysisResponse *-- FakeNewsResponse : contains
    FullAnalysisResponse *-- BiasResponse : contains
    FullAnalysisResponse o-- FactCheckResponse : contains list
    AdvancedLLMService --> LogicServices : feeds data
    FactCheckService --> LogicServices : feeds data
```

### 6. Activity Diagram - Scoring Algorithm

```mermaid
flowchart TD
    A([Start Scoring]) --> B[score = 50 + trust_boost]
    B --> C{Content Fake OR Toxic?}
    C -->|Yes| D[trust_boost = 0]
    C -->|No| E[Keep trust_boost]
    D --> F{Is verdict fake?}
    E --> F

    F -->|Yes| G[score minus 40]
    F -->|No| H{Is toxicity high?}
    G --> H

    H -->|Yes| I[score minus 20]
    H -->|No| J{Is verdict Biased?}
    I --> J

    J -->|Yes| K[score minus 10]
    J -->|No| L{Is clickbait high?}
    K --> L

    L -->|Yes| M[score minus 10]
    L -->|No| N{FactCheck debunked?}
    M --> N

    N -->|Yes| O[score minus 30]
    N -->|No| P[score plus 20 base boost]
    O --> P

    P --> Q[Clamp score 0 to 100]
    Q --> R{Determine Level}
    R -->|score above 90| S[Platinum]
    R -->|score above 75| T[Gold]
    R -->|score above 60| U[Silver]
    R -->|score 60 or below| V[Bronze]
    S --> W([End])
    T --> W
    U --> W
    V --> W
```

### 7. Use Case Diagram

```mermaid
flowchart LR
    U((User))
    AD((Admin))

    subgraph App [TruthLens Platform]
        UC1([Analyze Text])
        UC2([Analyze URL])
        UC3([Analyze Image or PDF via OCR])
        UC4([View Analysis Report])
        UC5([Stream Live Updates SSE])
        UC6([Play Gamified Quizzes])
        UC7([Submit Citizen Report])
        UC8([Search News])
        UC9([View Global Trends])
        UC10([Export Open Data])
        UC11([Privacy Dashboard])
        UC12([Admin Tools])
        UC13([Export PDF Report])
    end

    U --> UC1
    U --> UC13
    U --> UC2
    U --> UC3
    U --> UC4
    U --> UC5
    U --> UC6
    U --> UC7
    U --> UC8

    AD --> UC9
    AD --> UC10
    AD --> UC11
    AD --> UC12

    UC1 -.->|produces| UC4
    UC2 -.->|produces| UC4
    UC3 -.->|produces| UC4
```

### 8. State Machine - Task Lifecycle

```mermaid
stateDiagram-v2
    [*] --> queued : POST /analyze received

    queued --> processing : Celery Worker picks task

    state processing {
        [*] --> TextExtraction
        TextExtraction --> MegaAnalysis : Text cleaned
        MegaAnalysis --> FactChecking : LLM JSON returned
        FactChecking --> ScoreCalculation : OSINT data received
        ScoreCalculation --> CoachingTip : Score computed
        CoachingTip --> [*]
    }

    processing --> completed : Pipeline finished
    processing --> failed : Exception or Timeout
    completed --> [*]
    failed --> [*]
```

### 9. Data Flow Diagram

```mermaid
flowchart LR
    A[Raw Input] --> B{Input Type?}
    B -->|Text| C[Clean Text]
    B -->|URL| D[Scrape URL]
    B -->|Image| E[OCR Extraction]

    D --> C
    E --> C

    C --> F[FastText Language Detection]
    
    C --> NER[spaCy NER Extraction]
    NER --> WIKI[Wikipedia API Enrichment]
    WIKI --> G
    
    F --> G[run_mega_analysis 12 fields]

    C --> H[search_fact_check_db]
    H --> H1[Local RAG Search]
    H --> H2[Google News RSS]
    H --> H3[Google FactCheck API]

    G --> I[calculate_credibility]
    H1 --> I
    H2 --> I
    H3 --> I

    I --> J[Coaching_Service tips]
    J --> K[FullAnalysisResponse]
    K --> L[(Save to Firestore)]
```

### 10. Package Diagram - Repository Structure

```mermaid
flowchart TD
    subgraph Repo [TruthLens Repository]
        ROOT[Root Directory - 33 files]
        RT[routers - 15 modules]
        SV[services - 19 modules]
        CR[core - 7 modules]
        MD[models - 40+ Pydantic classes]
        ST[static - Frontend PWA]
        AS[assets/images - 101 files]

        ROOT --> RT
        ROOT --> SV
        ROOT --> CR
        ROOT --> MD
        ROOT --> ST
        ROOT --> AS

        RT -.->|imports| SV
        RT -.->|imports| MD
        SV -.->|imports| CR
        SV -.->|imports| MD
    end
```

---

## 📫 Contact & Professional Network

Developed by **Majd Majdi Ayoub** – Computer Engineer & AI Enthusiast based in San Bruno, California.

* **LinkedIn:** [linkedin.com/in/majd--ayoub/]**(https://www.linkedin.com/in/majd--ayoub/)**
* **Portfolio:** Available upon request.

## 📝 Featured Article

I have published a detailed article on LinkedIn Pulse that discusses the vision, challenges, and high-level strategy behind TruthLens.

👉 **[Read the Full Article on LinkedIn](https://www.linkedin.com/pulse/truthlens-ai-assisted-credibility-assessment-platform-majd-ayoub-psowf)**

> **Note:** The source code is currently kept in a private repository for intellectual property protection. The full technical architecture, system design, and implementation methodology are detailed in the officially published Zenodo report.

## 🤝 Commercial Inquiries & Collaboration

While this project is licensed under GPLv3, I am open to professional collaborations, commercial partnerships, and consulting opportunities. For inquiries regarding custom implementations or use cases beyond the scope of the current license, please contact me directly via LinkedIn.

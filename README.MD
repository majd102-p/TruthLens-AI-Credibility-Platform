# TruthLens: An AI-Assisted Credibility Assessment Platform

![DOI](https://img.shields.io/badge/DOI-10.5281%2Fzenodo.19591334-blue.svg)
![License](https://img.shields.io/badge/License-GPL--3.0-blue.svg)
![Python](https://img.shields.io/badge/Python-3.10%2B-green.svg)
![FastAPI](https://img.shields.io/badge/Framework-FastAPI-009688.svg)
[![LinkedIn Article](https://img.shields.io/badge/LinkedIn-Read%20Article-blue?logo=linkedin)](https://www.linkedin.com/pulse/truthlens-ai-assisted-credibility-assessment-platform-majd-ayoub-psowf)

## 🌟 Overview
**TruthLens** is a high-performance, decision-support system engineered to combat the spread of misinformation. Unlike traditional fact-checking tools, TruthLens leverages a **Hybrid Intelligence Architecture** that combines Local Large Language Models (LLMs), classical machine learning, and Open-Source Intelligence (OSINT) streams to provide real-time credibility scores.

---

## 📚 Official Publication & Citation
The comprehensive 100 -page technical architecture and research report for TruthLens is officially published and archived on **Zenodo**.

* **Official DOI:** [10.5281/zenodo.19591334](https://doi.org/10.5281/zenodo.19591334)
* **Permanent Link:** [https://doi.org/10.5281/zenodo.19591334](https://doi.org/10.5281/zenodo.19591334)

### Citation (APA)
> Ayoub, M. M. (2026). *TruthLens: An AI-Assisted Credibility Assessment Platform (Technical Report)*. Zenodo. https://doi.org/10.5281/zenodo.19591334

---

## ⚖️ Intellectual Property & Copyright Notice
**Copyright © 2026 Majd Majdi Ayoub. All Rights Reserved.**

* **Original Concept:** Majd Majdi Ayoub.
* **Technical Implementation:** 100% developed and architected by Majd Majdi Ayoub.
* **Documentation:** The technical report archived under DOI: 10.5281/zenodo.19591334 is the sole intellectual property of the author.

*Note: While this project was submitted as a formal graduation requirement for the Faculty of Engineering Technology at Al-Balqa Applied University, all technical assets (Code, Architecture, AI Orchestration) remain the author's intellectual property.*

---

## 🚀 Key Technical Features
* **Hybrid AI Orchestration:** Seamless integration of **Qwen 3 (8B)** and **Phi-3 Mini** for local, privacy-conscious reasoning and semantic validation.
* **Bilingual NLP Engine:** Advanced processing of both Arabic (including dialects) and English using **CAMeL-BERT** and **FastText**.
* **Asynchronous Processing:** Built for high concurrency using **FastAPI** with **Celery** and **Redis** for background task management.
* **OSINT Integration:** Real-time data fetching for cross-referencing claims against verified global databases.
* **Scalable Infrastructure:** Fully containerized environment using **Docker Compose**.

---

## 🏗 System Architecture
The system is built on a 4-tier architectural model:
1. **Ingestion Layer:** Captures news articles and social media metadata.
2. **Analysis Layer:** Parallel processing through AI classifiers and LLMs.
3. **Validation Layer:** Cross-checking results with OSINT APIs.
4. **Presentation Layer:** A clean, data-driven dashboard for end-user insights.

> **Note:** For a deep dive into the system's design patterns and UML diagrams, please refer to the [Full Technical Report (Zenodo)](https://doi.org/10.5281/zenodo.19591334).

---

## 🛠 Tech Stack
* **Language:** Python 3.10+
* **AI/ML:** Transformers (HuggingFace), Qwen-8B, Phi-3, CAMeL-BERT, Scikit-learn.
* **Backend:** FastAPI, Uvicorn.
* **Task Queue:** Celery, Redis.
* **DevOps:** Docker, Docker Compose.
* **Database:** PostgreSQL.

---

## 📫 Contact & Professional Network
Developed by **Majd Majdi Ayoub** – Computer Engineer & AI Enthusiast based in San Bruno, California.

* **LinkedIn:** [linkedin.com/in/majd--ayoub/](https://www.linkedin.com/in/majd--ayoub/)
* **Portfolio:** Available upon request.

---

## 📝 Featured Article
I have published a detailed article on LinkedIn Pulse that discusses the vision, challenges, and high-level strategy behind TruthLens. 

👉 **[Read the Full Article on LinkedIn](https://www.linkedin.com/pulse/truthlens-ai-assisted-credibility-assessment-platform-majd-ayoub-psowf)**

<sub>*Note: The source code is currently kept in a private repository for intellectual property protection. The full technical architecture, system design, and implementation methodology are detailed in the officially published Zenodo report.*</sub>

---

### 🤝 Commercial Inquiries & Collaboration
While this project is licensed under **GPLv3**, I am open to professional collaborations, commercial partnerships, and consulting opportunities. For inquiries regarding custom implementations or use cases beyond the scope of the current license, please contact me directly via [LinkedIn](https://www.linkedin.com/in/majd--ayoub/).

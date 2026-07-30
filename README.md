<div align="center">

# Hi, I'm Sai Kumar Reddy Anthireddy 👋

### AI/ML Engineer · RAG Pipelines · Agent Systems · MLOps

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/saireddy2110)
[![Email](https://img.shields.io/badge/Email-reddysaikumar614%40gmail.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:reddysaikumar614@gmail.com)
[![AWS Certified](https://img.shields.io/badge/AWS-Solutions_Architect_Associate-FF9900?style=for-the-badge&logo=amazonwebservices&logoColor=white)](https://www.credly.com/badges/0a980005-619e-405b-93ea-4c3e67b7bac6/linked_in_profile)
[![Resume](https://img.shields.io/badge/📄_Resume-View_%2F_Download-2ea44f?style=for-the-badge)](https://github.com/saianthireddy/saianthireddy/blob/main/Sai_Kumar_Reddy_Anthireddy_Resume.pdf)

</div>

---

## 🚀 About Me

- 🔭 AI/ML Engineer at **Teledyne Technologies**, building LLM-powered support automation with RAG
- 🎓 M.S. in Advanced Data Analytics — University of North Texas
- ⚡ 3 years shipping production ML: retrieval systems, agent orchestration, churn modeling, MLOps
- 🔬 I build evals that can actually fail — [here's how I found my own retrieval benchmark was reporting a meaningless 1.00](https://github.com/saianthireddy/rag-support-automation/pull/1)
- ☁️ [AWS Certified Solutions Architect – Associate](https://www.credly.com/badges/0a980005-619e-405b-93ea-4c3e67b7bac6/linked_in_profile) ✅ verified on Credly

## 🛠️ Tech Stack

**Shipping in the repos below** — every badge here has code behind it in this account

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![OpenAI](https://img.shields.io/badge/OpenAI_API-412991?style=flat-square&logo=openai&logoColor=white)
![Pinecone](https://img.shields.io/badge/Pinecone-000000?style=flat-square)
![FAISS](https://img.shields.io/badge/FAISS-0467DF?style=flat-square&logo=meta&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-150458?style=flat-square&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)
![DuckDB](https://img.shields.io/badge/DuckDB-FFF000?style=flat-square&logo=duckdb&logoColor=black)

![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white)
![Terraform](https://img.shields.io/badge/Terraform-7B42BC?style=flat-square&logo=terraform&logoColor=white)
![Airflow](https://img.shields.io/badge/Airflow-017CEE?style=flat-square&logo=apacheairflow&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)
![pytest](https://img.shields.io/badge/pytest-0A9EDC?style=flat-square&logo=pytest&logoColor=white)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)

**Implemented here but not benchmarked** — a fine-tuning pipeline for these exists in [intent-classification-lab](https://github.com/saianthireddy/intent-classification-lab) and is tested against a stub, but I have not published a score for it

`Hugging Face Transformers` · `BERT`

**Used professionally, not in these repos** — the projects here are deliberately dependency-light and run fully offline, so these don't appear in them

`LangChain` · `LangGraph` · `LlamaIndex` · `TensorFlow` · `ChromaDB` · `MLflow` · `AWS SageMaker` · `Azure` · `GCP` · `spaCy`

## 📌 Featured Projects

### [Enterprise AI Platform](https://github.com/saianthireddy/enterprise-ai-platform)

**Full-stack AI copilot for enterprises** — RAG chat, six specialist task handlers behind a routing layer, hybrid search, admin analytics, and the infrastructure to run it.

`FastAPI` `Next.js 14` `TypeScript` `Terraform` `Kubernetes` `Airflow` `Docker` `GitHub Actions CI`

- 🧭 Router node classifies intent and dispatches to one of six task handlers — a dependency-free state graph, with `langgraph.StateGraph` as the documented swap point
- 🔍 Hybrid search (lexical + dense) with a swappable vector-store factory
- 🔐 Read-only SQL agent with SELECT-only parsing and table whitelisting enforced **in code**, not in the prompt — the guard runs even if an LLM generated the query
- 📊 Admin dashboard: request volume, token usage, estimated cost, latency, all from live request data
- 🏗️ 7 Terraform modules (ALB, IAM, security, logs), K8s manifests, Airflow reindex/retrain DAG
- 🧪 50 tests · CI runs backend lint + tests, frontend build, and both Docker images

### [Intent Classification Lab](https://github.com/saianthireddy/intent-classification-lab)

**Three approaches to one task on identical splits** — TF-IDF baseline, a Transformer encoder written from scratch, and a fine-tuning pipeline. The headline result is a loss, reported as such.

`PyTorch` `scikit-learn` `Hugging Face` `GitHub Actions CI`

- ⚖️ **The baseline wins**: macro-F1 0.463 vs 0.436, and ECE 0.137 vs 0.406. 34% of test tokens are unseen words and 73k params over 176 examples is a losing ratio — that gap *is* the argument for transfer learning
- 🔬 Attention, multi-head projection, pre-norm blocks and masked pooling written by hand, not `nn.TransformerEncoder`
- 🎯 Dataset built so the benchmark can fail: shared vocabulary across intents, confusable pairs, phrasing families held out *before* rendering
- 🐛 A test caught a real NaN bug — an all-padding row masks every key, so softmax over all `-inf` poisons the forward pass
- 📐 CI caught a claim of mine that was architecture-specific: float64 mask exactness held on aarch64, failed on x86_64

### [RAG Support Automation](https://github.com/saianthireddy/rag-support-automation)

**Retrieval-Augmented Generation platform** answering technical support questions from manuals and SOPs with citation-grounded responses. Clean-room reimplementation of a system I built at Teledyne.

`OpenAI` `FAISS` `Pinecone` `FastAPI` `Docker` `GitHub Actions CI`

- 📄 Paragraph-aware chunking with sliding-window overlap
- 🔍 Swappable vector backends (FAISS / Pinecone / in-memory) behind one interface
- 🚫 Out-of-corpus questions are escalated, not hallucinated
- 📉 **Honest retrieval eval** — rebuilt the benchmark after finding the original couldn't fail: Precision@1 0.61, Recall@4 0.94, MRR 0.74 on an 18-query set with adversarial distractors
- 🧪 14 offline deterministic tests · runs with **zero API keys**

### [Enterprise MLOps Platform](https://github.com/saianthireddy/enterprise-mlops-platform)

**The full model lifecycle**, commit to monitored endpoint.

`MLflow-style registry` `Kubernetes` `SageMaker adapter` `GitHub Actions` `Slack alerts`

- 🔁 Automated retraining with champion/challenger promotion — weekly cron, drift-gated, currently running
- 🗂️ Versioned registry with promotion-safe staging → production → archived transitions
- 📉 PSI + Kolmogorov–Smirnov drift detection with Slack alerting
- ☸️ K8s Deployment/Service/HPA with health probes, plus an S3-backed SageMaker deploy adapter
- 🧪 17 tests

### [webdocs-mcp](https://github.com/saianthireddy/webdocs-mcp)

**Documentation search served to LLM agents as an MCP server** — crawl, chunk, index, and hybrid-search any docs site.

`MCP` `FastAPI` `DuckDB` `BM25 + embeddings` `Docker`

- 🕷️ Sitemap-aware crawler with HTML extraction and content-aware chunking
- 🔎 Hybrid retrieval: BM25 lexical scoring fused with dense embeddings, over DuckDB
- 🔌 Exposed as an MCP server so agents can query docs directly as a tool
- 🧪 23 tests, fully offline-testable

### [Customer Churn Prediction](https://github.com/saianthireddy/customer-churn-prediction)

**Retention intelligence** — at-risk customer identification with real-time scoring. Clean-room reimplementation of a platform I worked on at Colt.

`scikit-learn` `pandas` `FastAPI` `joblib` `Docker`

- 🧹 Schema validation, deduplication, median imputation, negative clipping
- 🛠️ Logistic Regression + Gradient Boosting behind one `Pipeline` with scaling
- 📈 Cross-validated: precision, recall, F1, ROC-AUC, confusion matrix
- 📋 [Model card](https://github.com/saianthireddy/customer-churn-prediction/blob/main/MODEL_CARD.md) documenting training data, per-model metrics, feature importance, and limitations
- ⚡ `/predict` returns churn probability + low/medium/high risk band

## 🎓 Education & Certification

- **M.S. Advanced Data Analytics** — University of North Texas, Denton TX
- **B.S. Computer Science** — Osmania University, Hyderabad
- **[AWS Certified Solutions Architect – Associate](https://www.credly.com/badges/0a980005-619e-405b-93ea-4c3e67b7bac6/linked_in_profile)** — verified on Credly

---

<div align="center">

💬 Open to collaborating on **RAG, agent systems, and MLOps** — let's connect!

</div>

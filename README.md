<!-- kenzychew/kenzychew - this README renders on the GitHub profile page. -->

<div align="center">

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=500&size=24&duration=2800&pause=1000&color=70A5FD&center=true&vCenter=true&width=600&height=50&lines=Applied+AI+Engineer" alt="Applied AI Engineer" />

# Kenneth Chew

### Applied AI Engineer

[![Portfolio](https://img.shields.io/badge/Portfolio-000000?style=for-the-badge&logo=vercel&logoColor=white)](https://kenzychew.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/kenzychew)
[![Email](https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:kenzychew@gmail.com)

</div>

---

## About

An AI Engineer based in Singapore. I work mostly on the deployment side - building the infrastructure and pipelines that put machine learning and GenAI systems into production and keep them running. My background is full-stack web development, so the serving, APIs, and data plumbing around a model are the things I usually enjoy doing.

## What I work on

- Infrastructure and pipelines for ML and GenAI
- Model serving, APIs, and deployment
- Containerization and CI/CD as part of the development process
- MLOps - automation, monitoring, and keeping things running

## Featured Projects

### Cineloops - still photo to cinemagraph, bring your own key

![Status](https://img.shields.io/badge/status-in%20progress-FACC15?style=flat-square)

Turn a still photo into a cinemagraph - a short looping clip where one part of the frame moves while the rest stays frozen. Upload a photo, mark the region you want to animate, and bring your own Replicate key to generate it. Each stage of the pipeline streams to the UI as it runs - captioning, prompt refinement, generation, and quality checks. Your key never leaves the browser. Work in progress.

`Next.js` `FastAPI` `Cloud Run` `Replicate` `Cloudflare R2` `SSE`

[Live](https://cineloops.vercel.app/)

### GotParking - forecasting carpark availability

Singapore's open data tells you how many lots are free right now, and that number is stale by the time you arrive.
GotParking predicts the count 20 minutes ahead for 268 carparks.
No public historical dataset exists, so the system builds its own: a Cloudflare Workers cron polls LTA DataMall every 5 minutes, feeding a weekly LightGBM retrain that pretrains on NTU's SINPA dataset and fine-tunes on live data.
A candidate only ships if it beats both the historical average and persistence on a live holdout - the first promoted model cut MAE to 16.6 lots against persistence's 21.4.
The model is deliberately the smallest part; the work is collecting the data and never showing a number the system cannot back.

`Python` `TypeScript` `LightGBM` `Cloudflare Workers` `Vercel` `Supabase` `GitHub Actions`

[Live](https://parking.kenzychew.com) | [View repo](https://github.com/kenzychew/GotParking)

### RocketML - experiment to deployment, the reusable parts

A self-service platform for serving NLP text classifiers as a containerised, monitored, Kubernetes-deployed inference API.
Bring a trained model and it gets a FastAPI endpoint, a slim non-root image, MLflow tracking and registration, Prometheus metrics, and a Helm chart onto a cluster - with CI running lint, tests, train, build, and push to GHCR on every merge to main.
The reusable machinery is the deliverable; the sentiment model it ships with is just there to show it working.

`Python` `FastAPI` `Docker` `Kubernetes` `Helm` `MLflow` `Prometheus` `Grafana` `GitHub Actions`

[Live](https://rocket.kenzychew.com) | [View repo](https://github.com/kenzychew/RocketML)

### DocExtract - LLM extraction that checks its own arithmetic

Drop invoices and receipts into a folder.
The agent extracts structured fields with an LLM, cross-checks the arithmetic, auto-accepts only what reconciles, and routes everything else to human review - running unattended, treating the model as fallible by design.
On a 261-document held-out SROIE slice, 94 documents (36%) were auto-accepted and 92 of those totals were correct - 97.9% precision on the accepted path. One miss was a one-cent rounding difference; the other was a 45-cent total that passed every validation rule with no signal in the pipeline distinguishing it from the accepts it shipped alongside - an open, unexplained anomaly, not a rounding difference. Everything else was routed to human review instead of being written unread.

`Python` `Gemini` `Gradio` `SQLite`

[Live](https://document.kenzychew.com) | [View repo](https://github.com/kenzychew/DocExtract)

### gofetch - RAG pipeline, built from scratch

A RAG pipeline with no orchestration framework.
Hybrid search (BM25 + dense vectors via pgvector), cross-encoder re-ranking, a knowledge graph, and streaming answers with inline citations, served over FastAPI.

`Python` `FastAPI` `pgvector` `BM25` `cross-encoder`

[Live](https://fetch.kenzychew.com) | [View repo](https://github.com/kenzychew/gofetch)

## Tech Stack

**Languages**

![Python](https://img.shields.io/badge/-Python-3776AB?style=flat-square&logo=python&logoColor=white)
![TypeScript](https://img.shields.io/badge/-TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![JavaScript](https://img.shields.io/badge/-JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![SQL](https://img.shields.io/badge/-SQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)

**AI / ML**

![PyTorch](https://img.shields.io/badge/-PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)
![scikit-learn](https://img.shields.io/badge/-scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white)
![LightGBM](https://img.shields.io/badge/-LightGBM-9ACD32?style=flat-square)
![Hugging Face](https://img.shields.io/badge/-Hugging%20Face-FFD21E?style=flat-square&logo=huggingface&logoColor=black)
![Gemini](https://img.shields.io/badge/-Gemini-8E75B2?style=flat-square&logo=googlegemini&logoColor=white)
![OpenCV](https://img.shields.io/badge/-OpenCV-5C3EE8?style=flat-square&logo=opencv&logoColor=white)
![pandas](https://img.shields.io/badge/-pandas-150458?style=flat-square&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/-NumPy-013243?style=flat-square&logo=numpy&logoColor=white)
![Jupyter](https://img.shields.io/badge/-Jupyter-F37626?style=flat-square&logo=jupyter&logoColor=white)
![Gradio](https://img.shields.io/badge/-Gradio-F97316?style=flat-square&logo=gradio&logoColor=white)
![ComfyUI](https://img.shields.io/badge/-ComfyUI-1A1A1A?style=flat-square)

**Backend and Data**

![FastAPI](https://img.shields.io/badge/-FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![Node.js](https://img.shields.io/badge/-Node.js-5FA04E?style=flat-square&logo=nodedotjs&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/-PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![pgvector](https://img.shields.io/badge/-pgvector-4169E1?style=flat-square)
![Supabase](https://img.shields.io/badge/-Supabase-3FCF8E?style=flat-square&logo=supabase&logoColor=white)
![MongoDB](https://img.shields.io/badge/-MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white)

**Cloud**

![Azure](https://img.shields.io/badge/-Azure-0078D4?style=flat-square&logo=microsoftazure&logoColor=white)
![Google Cloud](https://img.shields.io/badge/-Google%20Cloud-4285F4?style=flat-square&logo=googlecloud&logoColor=white)
![Vercel](https://img.shields.io/badge/-Vercel-000000?style=flat-square&logo=vercel&logoColor=white)
![Cloudflare Workers](https://img.shields.io/badge/-Cloudflare%20Workers-F38020?style=flat-square&logo=cloudflareworkers&logoColor=white)
![Cloudflare R2](https://img.shields.io/badge/-Cloudflare%20R2-F38020?style=flat-square&logo=cloudflare&logoColor=white)

**Tooling**

![Docker](https://img.shields.io/badge/-Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Kubernetes](https://img.shields.io/badge/-Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white)
![Helm](https://img.shields.io/badge/-Helm-0F1689?style=flat-square&logo=helm&logoColor=white)
![MLflow](https://img.shields.io/badge/-MLflow-0194E2?style=flat-square&logo=mlflow&logoColor=white)
![Prometheus](https://img.shields.io/badge/-Prometheus-E6522C?style=flat-square&logo=prometheus&logoColor=white)
![Grafana](https://img.shields.io/badge/-Grafana-F46800?style=flat-square&logo=grafana&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/-GitHub%20Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)
![GitLab CI](https://img.shields.io/badge/-GitLab%20CI-FC6D26?style=flat-square&logo=gitlab&logoColor=white)
![Git](https://img.shields.io/badge/-Git-F05032?style=flat-square&logo=git&logoColor=white)
![VS Code](https://img.shields.io/badge/-VS%20Code-007ACC?style=flat-square&logo=visual-studio-code&logoColor=white)

**Frontend**

![Next.js](https://img.shields.io/badge/-Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white)
![React](https://img.shields.io/badge/-React-61DAFB?style=flat-square&logo=react&logoColor=black)
![Tailwind CSS](https://img.shields.io/badge/-Tailwind%20CSS-38BDF8?style=flat-square&logo=tailwind-css&logoColor=white)

## GitHub Stats

<div align="center">

<img height="165" src="https://github-readme-stats.vercel.app/api?username=kenzychew&show_icons=true&theme=tokyonight&hide_border=true&count_private=true" alt="Kenzy's GitHub stats" />
<img height="165" src="https://github-readme-stats.vercel.app/api/top-langs/?username=kenzychew&layout=compact&theme=tokyonight&hide_border=true&langs_count=8" alt="Top languages" />

<img src="https://streak-stats.demolab.com?user=kenzychew&theme=tokyonight&hide_border=true" alt="GitHub streak" />

</div>
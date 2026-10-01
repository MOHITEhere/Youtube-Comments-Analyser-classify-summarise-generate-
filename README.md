# LLM-Based YouTube Comment Analysis System

A modular AI engineering system for large-scale YouTube comment analysis using LLM workflows, retrieval-augmented generation (RAG), experimentation pipelines, and asynchronous inference processing.

---

## Overview

This project focuses on building scalable workflows for analyzing YouTube comments using modern LLM engineering practices. The system supports asynchronous inference processing, prompt experimentation, automated model evaluation, retrieval-augmented response generation, and deployment-oriented pipelines.

The project is designed with modular components for experimentation, inference, evaluation, deployment, and reproducibility.

---

## Key Features

- Asynchronous inference workflows for large-scale YouTube comment processing
- Retrieval-Augmented Generation (RAG) using LangChain and FAISS
- MLflow-based experimentation and model evaluation workflows
- Automated best-model selection pipelines
- Chunk-based parallel processing and progressive aggregation
- Dockerized deployment workflows
- CI/CD automation using GitHub Actions
- Modular pipeline-oriented architecture
- DVC-based pipeline reproducibility and experiment tracking

---

## Tech Stack

### Backend & APIs
- FastAPI
- Python

### LLM & AI Frameworks
- LangChain
- FAISS
- Sentence Transformers
- OpenAI / LLM APIs

### Experimentation & MLOps
- MLflow
- DVC
- GitHub Actions

### Deployment
- Docker

### Data Processing
- Pandas
- NumPy

---

## System Architecture

### Inference Layer
Handles asynchronous LLM inference workflows, chunk-based processing, progressive aggregation, and retrieval-augmented generation.

### Experimentation Pipeline
Supports prompt versioning, deterministic evaluation, automated comparison workflows, and best-model selection using MLflow tracking.

### Data Pipeline
Responsible for data fetching, preprocessing, pipeline orchestration, and evaluation workflows.

### Deployment Layer
Dockerized services with CI/CD workflows for reproducible deployment environments.

---

## Project Structure

```bash
.
├── .github/workflows/       # CI/CD workflows
├── app/
│   ├── templates/           # Frontend templates
│   └── api.py               # FastAPI API routes
├── configs/                 # Model and pipeline configurations
├── data/
│   ├── raw/                 # Raw comment datasets
│   └── processed/           # Processed datasets
├── src/
│   ├── inference/           # Async inference and RAG workflows
│   ├── pipeline/            # Data preprocessing and evaluation pipelines
│   └── services/            # LLM and YouTube service integrations
├── tests/                   # API and workflow tests
├── Dockerfile               # Containerization setup
├── dvc.yaml                 # DVC pipeline configuration
├── params.yaml              # Experiment parameters
├── requirements.txt         # Project dependencies
└── main.py                  # Application entry point


---

## Workflow Pipeline

### 1. Video Input & Task Initialization
- Extracts and validates YouTube video IDs
- Initializes asynchronous background inference tasks
- Creates task states for real-time progress tracking

### 2. Comment Retrieval Pipeline
- Fetches YouTube comments incrementally using the YouTube Data API
- Supports pagination-based large-scale retrieval
- Processes comments progressively for improved responsiveness

### 3. Chunking & Parallel Processing
- Splits comments into smaller chunks for efficient LLM processing
- Uses multithreaded workflows for concurrent inference execution
- Improves scalability, latency, and token efficiency

### 4. Chunk-Level LLM Analysis
Each chunk independently performs:
- Sentiment classification
- Question detection
- Insight extraction
- Semantic similarity analysis
- Reply candidate extraction

Outputs are maintained as structured JSON responses for deterministic aggregation.

### 5. Aggregation Layer
Chunk-level outputs are progressively combined into:
- Global sentiment statistics
- Extracted user questions
- Semantic engagement insights
- AI-generated reply queues
- Final video-level summaries

### 6. Context-Aware Reply Generation
- Uses retrieval-augmented workflows with LangChain and FAISS
- Generates context-aware AI replies using semantically relevant transcript retrieval

### 7. Experimentation & Evaluation
- MLflow-based experiment tracking
- Prompt versioning workflows
- Automated best-model selection
- Deterministic evaluation pipelines

### 8. Real-Time Progress Tracking
Frontend polling APIs continuously track:
- Processing progress
- Sentiment counters
- Generated replies
- Inference task states

This enables non-blocking execution and progressive UI rendering.

---

## Setup Instructions

### Clone Repository

```bash
git clone https://github.com/your-username/youtube-comment-analyzer.git
cd youtube-comment-analyzer
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

### Run Application

```bash
python main.py
```

### Run Docker

```bash
docker build -t youtube-comment-analyzer .
docker run -p 8000:8000 youtube-comment-analyzer
```

---

## Future Improvements

- Streaming-based real-time inference pipelines
- Advanced hybrid retrieval and reranking workflows
- GPU-optimized inference deployment
- Distributed task orchestration for large-scale processing
- Real-time analytics dashboard and monitoring

---

## Author

Juned Shaikh

- LinkedIn: https://linkedin.com/in/junedshaikh04
- GitHub: https://github.com/Junedshaikh703

## Contributors

| Name | GitHub | Role |
|------|--------|------|
| Atharva Mohite | [@MOHITEhere](https://github.com/MOHITEhere) | Project Lead & System Design. Defined the architecture and pipeline, planned the features |
| Juned Shaikh | [@Junedshaikh703](https://github.com/Junedshaikh703) | Implementation and original commits |

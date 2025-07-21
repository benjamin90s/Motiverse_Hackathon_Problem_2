# Video-Text Semantic Search System with Claude 3 Sonnet

## Overview

This project implements a **Vision-Language Model (VLM) powered video search system** using **Claude 3 Sonnet** (via AWS Bedrock) for multimodal captioning. It enables semantic search over a dataset of driving scene videos by generating natural language summaries of video content and building a text-based search index. Users can perform natural language queries to retrieve the most relevant videos, regardless of specific keywords.

- **Input:** Set of categorized dashcam/driving videos (collisions, tailgating, traffic violations, etc.)
- **Output:** Ranked list of relevant videos for a given text query, with AI-generated descriptions powered by Claude 3 Sonnet.

---

## Features

- **Automated Video Captioning:** Extracts frames from each video and uses Claude 3 Sonnet (via AWS Bedrock) to generate descriptive natural language summaries.
- **Semantic Video Search:** Converts summaries into embeddings using Sentence Transformers, enabling semantic (not just keyword-based) search.
- **Interactive Query Interface:** Search videos using natural language; results are ranked by meaning similarity.
- **Cloud-Ready:** Processes video files directly from AWS S3 and leverages Bedrock API for high-performance multimodal captioning.

---

## Architecture 

S3 Videos --> Frame Extraction --> Claude 3 Sonnet Captioning --> Summary Embeddings --> Semantic Search
| |
(AWS Bedrock) (Sentence Transformers)



---

## Getting Started

### Prerequisites

- Python 3.8+
- AWS account with access to S3 and Bedrock API (Claude 3 Sonnet)
- Packages: `boto3`, `pandas`, `opencv-python`, `sentence-transformers`, `ipywidgets`, etc.

### Installation

```bash
pip install boto3 pandas opencv-python sentence-transformers ipywidgets

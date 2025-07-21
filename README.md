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
```
### Setup
- **AWS Credentials:**
Export or configure your AWS credentials in your environment. Ensure your Bedrock region has access to Claude 3 Sonnet.

- **Clone the repo:**
```bash
git clone https://github.com/your-username/video-text-index.git
cd video-text-index
```

- **Run the Jupyter notebook following the provided instructions.**

### Usage

- **Process Videos:**
Extract frames from each video in your S3 bucket.
Use Claude 3 Sonnet (via Bedrock) to generate a summary for each video.
Save summaries and metadata to a CSV file.

- **Build Search Index:**
Embed all summaries using Sentence Transformers (e.g., all-MiniLM-L6-v2).
Store embeddings for fast semantic search.

- **Semantic Search:**
Enter a natural language query in the provided interface.
The system returns the most relevant videos (video path + summary), ranked by semantic similarity.

- **Example Query:**
```bash
"car hits a deer at night"
```
Returns videos where a deer collision is detected, regardless of keywords.

### Example

| video\_key            | summary                                                  |
| --------------------- | -------------------------------------------------------- |
| videos/3078122527.mp4 | "A car collides with a deer at night, coming to a stop." |
| videos/3084823540.mp4 | "Bird hits car on a rural road, driver brakes suddenly." |
| ...                   | ...                                                      |

  

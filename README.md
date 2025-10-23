# Automated Semantic Segmentation and Chapter Generation for Video Transcripts

A Natural Language Processing (NLP) solution that automatically generates precise chapter markers and descriptive titles for video content by analyzing transcript data and detecting semantic shifts using Topic Modeling.

---

## Project Title & Short Description

**Title:** Automated Semantic Segmentation and Chapter Generation for Video Transcripts

**Description:** This system processes video transcripts to identify structural changes in content using **Latent Dirichlet Allocation (LDA)**. It leverages topic shifts as break points and **TF-IDF** to generate descriptive, time-stamped chapters, suitable for platforms like YouTube.
 
---

## Problem Statement / Goal

The primary goal is to **automate the creation of video chapters** from raw transcript text. Manually creating chapters is tedious, especially for long-form content. This project provides a scalable, data-driven method to:
1.  Use **Topic Modeling (LDA)** to segment the video based on thematic coherence.
2.  Generate accurate **time-stamped markers** wherever the core topic of discussion changes.
3.  Derive concise, descriptive **chapter titles** using **TF-IDF** analysis on the segment text.

---

## Tech Stack / Tools Used

The project is implemented in Python and utilizes key libraries for text processing, dimensionality reduction, and topic modeling:

| Category | Tool / Library | Purpose |
| :--- | :--- | :--- |
| **Data Handling** | Pandas NumPy | Data loading cleaning and numerical operations |
| **Topic Modeling**| Scikit-learn (LDA NMF) | Identifying latent topics and thematic shifts in the transcript |
| **Feature Extraction**| TfidfVectorizer CountVectorizer | Converting raw text into a numerical matrix (TF-IDF, Bag-of-Words) |
| **Visualization**| Matplotlib | Basic plotting and analysis (e.g., topic distribution visualization) |

---

## Approach / Methodology

1.  **Data Loading and Preprocessing**: Loaded the video transcript from `transcript.csv`, which contains `start` (time in seconds) and `text` columns.
2.  **Topic Modeling (LDA)**: Applied **Latent Dirichlet Allocation (LDA)** to the vectorized transcript text to discover a predefined number of underlying topics (e.g., 5 topics).
3.  **Chapter Break Identification**: Determined the **dominant topic** for each transcript segment and identified **chapter break points** as the exact time (`start` column) where the dominant topic transitions to a new one.
4.  **Chapter Naming**: For each new chapter segment, a separate **TF-IDF Vectorizer** was used to extract the **Top 3 keywords/key phrases** that best represent the semantic content of that segment, which are then used as the chapter name.
5.  **Final Output**: Converted the time-in-seconds to the standard **HH:MM:SS** format and printed the final list of chapter points with their generated names.

---

## Results / Key Findings

* The pipeline successfully translates temporal data (`start` time) and semantic data (transcript text) into an actionable list of chapter markers.
* The combination of **LDA** for segmentation and **TF-IDF** for naming provides a robust, multi-stage approach to content structure generation.
* The output directly produces the formatted chapter text required for platforms like YouTube, significantly reducing content production time.

---

## Topic Tags

VideoChaptering TopicModeling NLP LatentDirichletAllocation LDA Tfidf VideoContent DataScience Python Scikit-learn

---

## How to Run the Project

### 1. Install Requirements

Install all necessary packages using the provided `requirements.txt` file:

```bash
pip install -r requirements.txt
